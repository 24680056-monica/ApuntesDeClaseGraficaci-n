# Unidad 2: Graficación 2D 

La graficación 2D no solo trata de "dibujar", sino de la manipulación algorítmica de datos vectoriales. En Blender, aunque es una herramienta 3D, el motor de Grease Pencil y el manejo de Curvas y Nodos de Geometría convierten al software en una potencia para el diseño 2D procedural y tradicional.

## 2.1 Transformación bidimensional
Las transformaciones son aplicaciones lineales que mapean un vector (posición original) a uno nuevo. En computación gráfica, esto se entiende como cambiar el espacio de objeto al espacio de la escena.
### 2.1.1 Traslación.
Es una transformación rígida que añade un vector de desplazamiento $\vec{d} = (t_x, t_y)$ a cada punto del objeto.

- **Teoría**: No altera la forma ni el tamaño, solo la posición. Es una suma vectorial:
  $\vec{P}' = \vec{P} + \vec{T}$

- **En Blender**: Al presionar G, Blender activa un estado modal. Si presionas X o Y después de G, estás restringiendo la suma vectorial a un solo componente del eje.

Se puede implementar por igual mediante un codigo para hacer la traslación, el cual por ejemplo es así:
``` python
import bpy

# Obtener el objeto activo
obj = bpy.context.active_object

# OPCIÓN A: Operador (Simula presionar 'G')
# Mueve el objeto 2 unidades en X y 3 en Y
bpy.ops.transform.translate(value=(2.0, 3.0, 0.0))

# OPCIÓN B: Propiedad directa (Más rápido)
obj.location.x += 2.0
obj.location.y += 3.0
```
### 2.1.2 Escalamiento
Altera la distancia de los puntos respecto a un punto de origen (frecuentemente el origen del objeto o el Cursor 3D).
- **Teoría**: Se define por factores de escala $s_x$ y $s_y$.Si $|s| > 1$, hay expansión.Si $|s| < 1$, hay contracción.Si el factor es negativo, se produce una reflexión (espejo).
- **En Blender**: El escalamiento depende críticamente del Pivot Point (Punto de Pivote). Cambiarlo a "3D Cursor" permite escalar respecto a cualquier punto arbitrario del plano.

Se puede implementar por igual mediante un codigo para hacer el escalamiento, el cual por ejemplo es así:
``` python
import bpy

obj = bpy.context.active_object

# OPCIÓN A: Operador (Simula presionar 'S')
# Escala al doble en X y a la mitad en Y
bpy.ops.transform.resize(value=(2.0, 0.5, 1.0))

# OPCIÓN B: Propiedad directa
obj.scale.x = 2.0
obj.scale.y = 0.5
```
### 2.1.3 Rotación
Gira el objeto un ángulo $\theta$ sobre un eje perpendicular al plano (el eje Z en el espacio 2D de Blender).
- **Teoría**: Las coordenadas se calculan mediante funciones trigonométricas.Sentido antihorario = Ángulo positivo.Sentido horario = Ángulo negativo.
- **En Blender**: Al rotar con R, puedes escribir el ángulo exacto (ej. R + 45). Internamente, Blender convierte estos grados a Radianes para sus cálculos matriciales.

Se puede implementar por igual mediante un codigo para hacer la rotacion, el cual por ejemplo es así:
``` python
import bpy
import math

obj = bpy.context.active_object

# Definir ángulo en grados y convertir a radianes
angulo_grados = 45
angulo_rad = math.radians(angulo_grados)

# OPCIÓN A: Operador (Simula presionar 'R')
bpy.ops.transform.rotate(value=angulo_rad, orient_axis='Z')

# OPCIÓN B: Propiedad directa (Rotación de Euler)
obj.rotation_euler.z += angulo_rad
```
### 2.1.4 Sesgado (Shear)
Es una transformación no rígida donde los puntos se desplazan en una dirección proporcional a su distancia de un eje fijo.
- **Teoría**: Un cuadrado se convierte en un paralelogramo. El área se conserva, pero los ángulos internos cambian.
- **En Blender**: Aunque no tiene una tecla simple como G, S o R, se accede en Edit Mode con Ctrl + Alt + Shift + S. Es vital para dar perspectiva manual a objetos planos.

Se puede implementar por igual mediante un codigo para hacer el sesgado, el cual por ejemplo es así:
``` python
import bpy
import mathutils

obj = bpy.context.active_object

# Crear una matriz de identidad (4x4)
shear_matrix = mathutils.Matrix.Identity(4)

# Definir el factor de sesgado (inclinación)
factor = 0.5 

# En una matriz 4x4, el sesgado X respecto a Y es la posición [0, 1]
shear_matrix[0][1] = factor 

# Multiplicar la matriz actual del objeto por la de sesgado
obj.matrix_world = obj.matrix_world @ shear_matrix
```

## 2.2 Representación Matricial de Transformaciones
Para evitar cálculos redundantes, la computación gráfica utiliza Coordenadas Homogéneas. Esto permite que la traslación (que es una suma) se trate como una multiplicación, igual que la rotación y la escala.
El uso de Coordenadas Homogéneas ($3 \times 3$)Para representar un punto $(x, y)$ en una matriz que permita traslación, añadimos una tercera dimensión ficticia $w=1$. Así, el punto es $(x, y, 1)$.
- Matriz de Traslación:

  <img width="120" height="90" alt="image" src="https://github.com/user-attachments/assets/a842476d-6663-4c53-8094-469f7783220c" />


- Matriz de Rotación:


<img width="120" height="90" alt="image" src="https://github.com/user-attachments/assets/ca80d93b-1c49-4944-94c0-70094972c328" />

- Composición de Transformaciones: En Blender, cuando mueves, rotas y escalas un objeto, el software no realiza tres cálculos separados. Multiplica las matrices correspondientes para crear una Matriz de Transformación Única ($M_{final} = M_t \cdot M_r \cdot M_s$). Esto es mucho más eficiente para la GPU.

En el desarrollo de este subtema  se desarrollo un codigo para el movimiento del dibujo al presionar las flechas en la direccion que segun se requeria mover.
``` python
import bpy

class ModalMoveOperator2D(bpy.types.Operator):
    """Movimiento 2D real: Flechas para X y Z"""
    bl_idname = "object.modal_move_operator_2d"
    bl_label = "Modal Move Operator 2D"

    def modal(self, context, event):
        obj = bpy.data.objects.get("MiDibujo")
        
        if obj is None:
            return {'FINISHED'}

        if event.value == 'PRESS':
            # --- MOVIMIENTO HORIZONTAL ---
            if event.type == 'LEFT_ARROW':
                obj.location.x -= 0.5
            elif event.type == 'RIGHT_ARROW':
                obj.location.x += 0.5
            
            # --- MOVIMIENTO VERTICAL (CORREGIDO) ---
            # Usamos 'z' para que suba/baje en la pantalla 
            # y no se acerque/aleje (que es lo que hace el eje 'y')
            elif event.type == 'UP_ARROW':
                obj.location.z += 0.5
            elif event.type == 'DOWN_ARROW':
                obj.location.z -= 0.5

            # Salida del modo
            elif event.type == 'ESC':
                print("Control 2D finalizado.")
                return {'FINISHED'}

        return {'RUNNING_MODAL'}

    def invoke(self, context, event):
        context.window_manager.modal_handler_add(self)
        print("Control 2D Activo: Flechas para mover, ESC para salir.")
        return {'RUNNING_MODAL'}

# Registro del operador
if hasattr(bpy.types, "ModalMoveOperator2D"):
    bpy.utils.unregister_class(ModalMoveOperator2D)
    
bpy.utils.register_class(ModalMoveOperator2D)
bpy.ops.object.modal_move_operator_2d('INVOKE_DEFAULT')
```
## 2.3. Trazo de líneas curvas.
A diferencia de las mallas (meshes), las curvas son definiciones matemáticas infinitamente suaves.

### 2.3.1 Curvas de Bézier
Se basan en los Polinomios de Bernstein. Una curva de Bézier de grado $n$ tiene $n+1$ puntos de control.
- Funcionamiento: El punto $P_0$ y $P_n$ son los extremos (la curva pasa por ellos). Los puntos intermedios actúan como "imanes" que atraen la curva pero no necesariamente la tocan.
- En Blender: Existen tipos de "Handles" (manejadores):
  - Automatic: Curvatura suave calculada por Blender.
  - Vector: Crea esquinas afiladas (líneas rectas).Aligned: Mantiene la tangencia para que la curva sea suave.

### 2.3.2 NURBS (Non-Uniform Rational B-Splines)
Son una generalización de las curvas B-Spline.
- Teoría: * Non-Uniform: Los puntos de control pueden tener diferentes "pesos" o influencias.
  - Rational: Permite representar secciones cónicas exactas (círculos, elipses) que Bézier solo puede aproximar.
- Uso: Ideales para modelado industrial o superficies orgánicas que requieren alta precisión matemática.
- <img width="284" height="213" alt="image" src="https://github.com/user-attachments/assets/4dc8d9d8-df0d-43e6-bf27-c15d439c6a00" />

Ejemplo del desarrollo en blender:
<img width="1882" height="958" alt="image" src="https://github.com/user-attachments/assets/fabd2b30-572a-4cb6-877b-8289ec5cc097" />

## 2.4. Fractales
Los fractales en la animación 2D se utilizan principalmente para generar complejidad visual, texturas orgánicas y paisajes naturales de manera algorítmica. Al basarse en la autosimilitud (patrones que se repiten a distintas escalas), permiten crear formas detalladas y realistas sin necesidad de dibujarlas a mano, lo que ahorra tiempo y recursos. 

- Geometry Nodes (Recomendado): Permite crear fractales procedurales repitiendo geometrías (como una icosphere o plano) sobre vértices, utilizando nodos Instance on Points para generar iteraciones complejas. Se pueden animar los valores de escala y rotación para crear bucles.
- Nodos de Shader (2D): Puedes crear fractales 2D generativos dentro del editor de materiales, lo que permite efectos visuales complejos sin geometría pesada.
- Add-ons y Scripts: Herramientas como Fractal Family facilitan la creación de curvas fractales basadas en redes complejas. También existen generadores basados en nodos de animación.
- Técnicas de Animación:
  - Interpolación: Usa keyframes para suavizar el cambio de forma y escala de los fractales, creando animaciones fluidas sin dibujar cuadro a cuadro.
  - Modificadores: El modificador Tessellate (Tisu) sirve para repetir patrones geométricos 2D.
<img width="828" height="416" alt="image" src="https://github.com/user-attachments/assets/a4d5e543-4de9-49d9-b9c9-c8e53836cd2a" />

## 2.5 Uso y creación de fuentes de texto.
El texto en gráficos 2D se trata como vectores definidos por curvas.
- **De Fuente a Malla**:
  - Tipografía: Archivos .ttf o .otf que contienen las fórmulas matemáticas de cada letra.
  - Rasterización vs Vectorización: Blender lee el vector de la fuente. Para manipularlo como objeto 3D, primero lo convierte internamente en una Curva de Bézier y, opcionalmente, el usuario puede convertirlo en una Malla de polígonos (Right Click -> Convert to Mesh).
- **Propiedades Avanzadas**: * Kerning: Ajuste de espacio entre letras.
  - Extrusión: Dar profundidad (paso de 2D a 3D).

# Referencias bibliograficas
- Blender Foundation. (n.d.). Fractal family. Blender Extensions. https://extensions.blender.org/add-ons/fractal-family/
- Garcia, O. (n.d.). Unidad II.- Graficacion 2D: Curvas. https://garciaoscar10110795.blogspot.com/p/curvas.html
- Gomez, R. (n.d.). Reporte Uso y Creación de Fuentes de Texto. Scribd. https://es.scribd.com/document/598144009/Reporte-Uso-y-Creacion-de-Fuentes-de-Texto
- Transformación - Blender 5.1 Manual. (n.d.). https://docs.blender.org/manual/es/latest/scene_layout/object/properties/transforms.html
