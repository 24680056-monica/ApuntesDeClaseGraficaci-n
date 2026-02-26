# ApuntesDeClaseGraficación

## Unidad I. Introducción a la graficación por computadora.  <br>
La graficación por computadora es el área de la informática encargada de crear, manipular y representar imágenes y modelos visuales mediante el uso de algoritmos y software especializado. Combina principios de matemáticas, programación y diseño para generar gráficos en 2D y 3D que pueden visualizarse en pantallas, dispositivos móviles o entornos de realidad virtual.<br>

Esta disciplina es fundamental en campos como los videojuegos, la animación, el diseño asistido por computadora (CAD), la simulación científica y el cine digital. A través de técnicas como el modelado, el renderizado y la animación, la graficación por computadora permite transformar datos y conceptos abstractos en representaciones visuales claras e interactivas.
## 1.1. Historia y evolución de la graficación por computadora.
Se presenta como fue evolucionando la graficación, es decir, como los humanos aprendieron a ver y manipular datos a través de una interfaz visual. <br>
**1. La Era de la Supervivencia y el Osciloscopio (1950 - 1959)** <br>
En los inicios, las computadoras no tenían monitores; tenían tubos de rayos catódicos (CRT) rudimentarios.
- Proyecto Whirlwind (1951): El primer sistema capaz de mostrar texto y gráficas en tiempo real. Fue el precursor de los sistemas de defensa aérea (SAGE).
- Tennis for Two (1958): William Higinbotham crea uno de los primeros videojuegos usando un osciloscopio, demostrando que las gráficas podían servir para el entretenimiento.

**2. El Nacimiento de la Interactividad (1960 - 1969)** <br>
Esta década definió las bases de la Interacción Humano-Computadora (HCI).
- Sketchpad (1963): Ivan Sutherland (el "padre de la graficación") desarrolló este sistema que permitía dibujar objetos directamente en la pantalla con un lápiz óptico. Introdujo conceptos clave como la jerarquía de objetos y las restricciones geométricas.
- Douglas Engelbart (1968): Presentó "La madre de todas las demostraciones", donde introdujo el ratón, el hipertexto y la interfaz gráfica de usuario (GUI) temprana.

**3. El Surgimiento del Realismo y los Algoritmos (1970 - 1979)** <br>
Aquí la graficación pasó de ser "líneas blancas sobre fondo negro" a buscar la tridimensionalidad.
- La Tetera de Utah (1975): Martin Newell crea este modelo icónico para probar algoritmos de renderizado. <br>
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c8913ebc-7cd0-4f04-871d-e0fe274a942c" /> <br>
- Algoritmos de Sombreado: Aparecen técnicas fundamentales como el Sombreado de Gouraud (transiciones suaves de color) y el Sombreado de Phong (especularidad y reflejos), elementos que aparecen en tu infografía como "Técnicas de Iluminación".
- Nacimiento de Atari: Con Pong, la graficación se convierte en una industria comercial masiva.
**4. La Revolución del PC y el CGI en el Cine (1980 - 1989)** <br>
La potencia de cómputo llega a los escritorios y a Hollywood.
- Software Profesional: El lanzamiento de AutoCAD (1982) revoluciona la ingeniería y arquitectura, pasando del restirador al diseño asistido por computadora (CAD).
- La era de Pixar: Se funda Pixar (tras separarse de Lucasfilm). Cortometrajes como Luxo Jr. demuestran que el 3D puede transmitir emociones mediante la aplicación de principios de animación tradicional (squash and stretch) a modelos matemáticos.
- Interfaces Gráficas (GUI): Apple lanza la Macintosh (1984), popularizando las ventanas e íconos para el usuario común.
**5. La Era de la Aceleración por Hardware (1990 - 1999)** <br>
La transición del software al hardware especializado.
- GPUs y Estándares: Aparece OpenGL (1992) y DirectX, permitiendo que los desarrolladores hablen un "idioma común" con el hardware.
- Hito Cinematográfico: Toy Story (1995) se convierte en el primer largometraje renderizado íntegramente por computadora.
- NVIDIA GeForce 256 (1999): Comercializada como la "primera GPU del mundo", moviendo el procesamiento geométrico de la CPU a una tarjeta dedicada.

**6. El Siglo XXI: Realismo en Tiempo Real y VR** <br>
La frontera entre lo real y lo generado por computadora se vuelve difusa.
- Shaders Programables: Permiten efectos complejos como piel real, agua dinámica y fuego.
- Ray Tracing (Trazado de Rayos): El "santo grial" de la graficación, que simula el comportamiento físico de la luz, ahora es posible en tiempo real gracias a núcleos especializados (RT Cores).
- Inmersión Total: La evolución hacia la Realidad Virtual (VR) y Aumentada (AR) integra sensores de movimiento y visión computacional para crear entornos donde el usuario es el centro.

## 1.2. Áreas de aplicación.
La graficación por computadora se aplica en el diseño asistido (CAD/CAM), entretenimiento (cine y videojuegos), visualización científica, medicina, simulación y diseño gráfico. Permite crear, manipular y representar datos, modelos 3D y entornos virtuales, siendo esencial para el modelado industrial, realidad virtual, simulaciones de vuelo y visualización de datos complejos. Pero sus principales lugares donde se aplica son: <br>
<img width="819" height="460" alt="image" src="https://github.com/user-attachments/assets/51d4dfc3-576d-4fbc-813d-e79bf1e79f1d" /> <br>

**1. Ciencia y Bioinformática (Más allá de la Medicina)** <br>
- Visualización Molecular: Renderizado de estructuras de ADN y proteínas para entender cómo interactúan los fármacos a nivel atómico.
- Simulaciones Atmosféricas: Modelado de huracanes, corrientes oceánicas y el cambio climático mediante mapas de calor y flujos vectoriales en 3D.

**2. Industria 4.0 y Gemelos Digitales (Digital Twins)** <br>
- Gemelos Digitales: Se crean réplicas exactas en 3D de fábricas o ciudades enteras. Estos modelos reciben datos en tiempo real de sensores para predecir fallos antes de que ocurran en el mundo físico.
- Fabricación Aditiva (Impresión 3D): La graficación no solo sirve para ver el objeto, sino para generar las mallas geométricas necesarias para que una impresora deposite material capa por capa.

**3. Cartografía y Sistemas de Información Geográfica (SIG)** <br>
La visualización de datos se extiende a la superficie terrestre:
- Mapas Fotogramétricos: Uso de drones para capturar imágenes y convertirlas en modelos de elevación digital (DEM) con texturas realistas.
- Navegación en Tiempo Real: Los sistemas como Google Earth combinan graficación 3D con bases de datos espaciales para la logística global.

**4. Educación** <br>
Expandiendo el área de Simulaciones:
- Museografía Virtual: Reconstrucción de sitios arqueológicos o monumentos históricos que ya no existen, permitiendo recorridos virtuales interactivos.
- Laboratorios Virtuales: Permiten a estudiantes de química o física realizar experimentos peligrosos en un entorno controlado y visualmente preciso. <br>

## 1.3. Aspectos matemáticos de la graficación.
Se trata de aplicar conceptos matemáticos para generar y manipular imágenes de manera digital. Desde la creación de simples gráficos hasta la construcción de complejos modelos 3D, las matemáticas son la base fundamental de todo lo que vemos en una pantalla. <br>
**Áreas de las matemáticas involucradas :** 
- Geometría : Es la base de la graficación. Nos permite definir formas, calcular distancias, ángulos y volúmenes. La geometría euclidiana, la geometría proyectiva y la geometría fractal son algunas de las ramas más utilizadas en este campo.
- Algebra : Es esencial para realizar transformaciones en las imágenes, como rotaciones, escalamientos y traslaciones. También se utiliza para definir curvas y superficies.
- Cálculo : SE emplea para calcular la iluminación, las sombras y los efectos de textura en las imágenes.
- Estadística: Se utiliza para analizar datos y generar visualizaciones informativas.

**¿Para que sirve la graficación matemática?**
- Diseño gráfico: En la creación de logotipos, ilustraciones, animaciones y efectos visuales.
- Videojuegos: Para modelar personajes, escenarios y efectos especiales.
- Simulaciones: En campos como la ingeniería, la arquitectura y la medicina para visualizar y analizar sistemas complejos.
- Visualización de datos: Para representar información de manera clara y concisa.
- Realidad virtual y aumentada: Para crear experiencias inmersivas.

## 1.4. Modelos del color: RBG, CMY, HSV y HSL.
Entender los modelos de color tiene su sentido pues al saber reconocer cuando utilizar que modelo de color utilizar muestra la diferencia entre las imágenes creadas donde se ven profesional o parecen un accidente de saturación. <br>
**1. RGB (Red, Green, Blue):** Representa cuánta luz de cada color primario emite un píxel y es un modelo aditivo. Se basa en la suma de longitudes de onda de luz. Si sumas los tres colores al máximo, obtienes blanco (1.0, 1.0, 1.0). 
- Es el estándar nativo de casi todo el hardware (monitores, proyectores, cámaras). Los motores de renderizado (Cycles, Unreal Engine, Unity) realizan sus cálculos de iluminación en este espacio.
- Cuándo usarlo:
   - Para programación de shaders de bajo nivel.
   - Cuando trabajas directamente con el hardware de visualización.
   - Para definir luces físicas en una escena 3D. <br>
<img width="200" height="200" alt="image" src="https://github.com/user-attachments/assets/9168eb29-2d05-404a-ab2e-f648982a08ee" /> <br>

**2. CMY / CMYK (Cyan, Magenta, Yellow):** Es un modelo sustractivo. Aquí, el color se crea "restando" luz blanca mediante pigmentos o filtros, este funciona de forma inversa al RGB. El Cian absorbe el Rojo, el Magenta absorbe el Verde y el Amarillo absorbe el Azul.
- Matemáticamente: $C = 1 - R$, $M = 1 - G$, $Y = 1 - B$.
- Es el lenguaje de la impresión física. El "K" (Key/Negro) se añade porque la mezcla de CMY real no da un negro perfecto, sino un café oscuro.
- Cuándo usarlo:
   - Exclusivamente para salida a impresión.
   - En software de diseño editorial o pre-prensa.
   - Evítalo en graficación en tiempo real o renderizado 3D, ya que consume recursos innecesarios convertir de RGB a CMY. <br>
<img width="300" height="200" alt="image" src="https://github.com/user-attachments/assets/205d9eb7-81ae-465e-9a54-00213df680d3" /> <br>

**3. HSV y HSL:** Ambos son transformaciones cilíndricas del modelo RGB. Fueron creados para hacerlo más cómodo a la percepción de la vista humana.
- **HSV (Hue, Saturation, Value):** Define el color por su tinte (Hue), su pureza (Saturation) y su brillo (Value). El "Value" es simplemente el valor del componente RGB más alto.
    - Cuándo usarlo: Es el mejor para interfaces de usuario (UI) y selectores de color. Si quieres que un objeto mantenga su "color" pero cambie su intensidad, solo tocas el Value.
- **HSL (Hue, Saturation, Lightness):** Similar al HSV, pero el componente Lightness llega al blanco puro en el valor máximo.
    - Cuándo usarlo: Muy popular en desarrollo web (CSS) y retoque fotográfico, ya que es más intuitivo para controlar la exposición y el contraste de una imagen sin alterar los tonos de piel o el color base. <br>
<img width="300" height="280" alt="image" src="https://github.com/user-attachments/assets/44139166-37f7-49ea-8153-a03e292ec0e1" /> <br>
### En resumen se utiliza: 
<img width="550" height="430" alt="image" src="https://github.com/user-attachments/assets/fbcda790-df9a-4fd9-8eda-b666db41e121" />

## 1.5. Representación y trazo de líneas y polígonos.
En el área de graficación por computadora, el paso de una entidad matemática ideal (una línea infinita o un polígono perfecto) a una rejilla de píxeles se llama Rasterización. Este es el proceso fundamental detrás de todo lo que se ve en una pantalla. <br>

**El Trazo de Líneas: De la Ecuación al Píxel:** <br>
Una línea en geometría se define por y = mx + b. Sin embargo, una pantalla no tiene "puntos infinitos", tiene píxeles discretos. El reto es decidir qué píxeles encender para que la línea se vea lo más recta y suave posible.
 - **Algoritmo DDA (Digital Differential Analyzer):** Es el método más simple. Se basa en calcular el diferencial de x y y.
   - Lógica: Si se conoce la pendiente (m), por cada paso en x, se aumenta y en m unidades. 
   - Limitación: Usa aritmética de punto flotante (decimales), lo que lo hace lento en procesadores antiguos o sistemas de alto rendimiento.<br>
 - **Algoritmo de Bresenham (El estándar de la industria):** Es el algoritmo más eficiente porque utiliza únicamente aritmética de números enteros.
     - Lógica: En lugar de calcular decimales, usa una "variable de decisión" P que determina si el siguiente píxel debe estar en la misma fila o subir a la siguiente.
     - Matemática: Si tenemos un punto (xk, yk), el algoritmo decide si el siguiente es (xk + 1, yk) o (xk + 1, yk + 1) basándose en el signo de: `Pk = 2Δy - Δx`.<br>

**Representación de Polígonos:**
En graficación, un polígono no es solo un dibujo; es una estructura de datos. Se representan principalmente de dos formas:
 - Lista de Vértices: Una secuencia ordenada de puntos V = {P1, P2, ..., Pn}. Es eficiente en memoria pero difícil para calcular colisiones rápidas.
 - Lista de Aristas (Edge List): Define al polígono por sus bordes. Cada arista conecta dos índices de la lista de vértices. Es la forma en que los motores 3D como Blender o Unreal gestionan la "malla" (mesh).<br>

**Clasificación Crítica:**
 - Convexos: Cualquier línea que una dos puntos internos queda dentro del polígono (fáciles de procesar).
 - Cóncavos: Pueden causar errores en algoritmos simples de llenado. La mayoría de los motores de graficación "triangulan" los polígonos cóncavos (los dividen en triángulos) para procesarlos sin errores.

**Pasos de implementación**
1. Definir los vértices: Establecer los puntos del polígono en el sistema de coordenadas.
2. Generar el lienzo (Frame): Crear el panel gráfico.
3. Conectar puntos: Dibujar los segmentos entre vértices consecutivos.
4. Cerrar el polígono: Conectar el último vértice con el primero.

## 1.5.1 Formatos de imagen.
1. Mapas de Bits (Raster)
   - Almacenan la imagen como una cuadrícula de píxeles.
   - Cada píxel tiene un valor de color.
   - Dependientes de la resolución.
   - Ideales para fotografías y degradados suaves.
**Formatos Raster:**
- JPEG (JPG):
  - Compresión con pérdida (lossy).
  - Reduce mucho el tamaño del archivo.
  - Puede generar artefactos.
  - No soporta transparencia.
  - Ideal para fotografías en web.

- PNG:
  - Compresión sin pérdida (lossless).
  - Soporta transparencia (canal alfa).
  - Mayor calidad que JPEG.
  - Ideal para logotipos, gráficos e interfaces.

- GIF:
  - Limitado a 256 colores.
  - Compresión sin pérdida (LZW).
  - Soporta animaciones simples.
  - Ideal para gráficos simples y animaciones cortas.

- BMP:
  - Generalmente sin compresión.
  - Archivos muy grandes.
  - Formato antiguo de Windows.
  - Usado en aplicaciones básicas.

2. Gráficos Vectoriales
   - Almacenan la imagen como fórmulas matemáticas.
   - Usan líneas, curvas (Bézier) y formas.
   - Independientes de la resolución.
   - Se pueden escalar sin perder calidad.
   - Ideales para logotipos, diagramas y diseño gráfico.
**Formatos Vectoriales:**
- SVG
  - Basado en XML.
  - Estándar para la web.
  - Escalable sin pérdida de calidad.
- AI
  - Formato nativo de Adobe Illustrator.
  - Uso profesional en diseño gráfico.
- CDR
  - Formato nativo de CorelDRAW.
  - Usado en diseño editorial e impresión.
---
Para analizar mejor como se implementan los trazos, implementaremos dos ejercicios rápidos: <br>
Consulte el siguiente repositorio que contiene los ejercicios:
- Flor de vida.
- Dibujo de polígono.

[Ejercicios Blender](https://github.com/24680056-monica/EjerciciosBlender.git)

## 1.6 Procesamiento de mapas de bits.
<img width="500" height="330" alt="image" src="https://github.com/user-attachments/assets/df7faebd-43c6-4f5e-9361-9d8183600fb3" />

El procesamiento de mapas de bits (imágenes raster) es una disciplina central en la gráficación por computadora, visión artificial y renderizado digital. A diferencia de los gráficos vectoriales (basados en ecuaciones), una imagen raster está compuesta por una matriz bidimensional de píxeles, donde cada píxel almacena información numérica de color. <br>
Se conoce como mapa de bits a un formato que sirve para representar imágenes de forma digital, en el que las dimensiones están determinadas por la cantidad de píxeles horizontales y verticales que componen a cada imagen, y en el que cada pixel tiene asociado un rango de valores de color, es decir, es una trama compuesta por una estructura rectangular formada por píxeles o puntos de color que forman una imagen. <br>
Los mapas de bits pueden ser conocidos de varias formas. Algunas de ellas son:
- Bitmap.
- Raster image.
- Imagen matricial.
### Función
Son las representaciones de fotografías en un mapa de bits son las fotografías. Generalmente, esta es la forma en la que se traspasa la información del mundo analógico al digital. Cuando se toma una foto con un smartphone o una cámara profesional, la imagen se registra en datos de píxel y al cargarse en línea se leen como imágenes en formato raster.<br>

### Operaciones comunes de procesamiento
Son los algoritmos de procesamiento y estos se dividen principalmente en:
- Operaciones de punto (Píxel a Píxel): Se modifica cada píxel de forma independiente basándose solo en su valor original.
  - Brillo y Contraste: Sumar o multiplicar valores a los canales de color.
  - Inversión: Convertir un color en su opuesto.
  - Umbralización (Thresholding): Convertir la imagen a blanco y negro puro basándose en un límite de luminosidad.

- Filtros de vecindad (Convolución): Aquí el nuevo valor de un píxel depende de sus vecinos. Se utiliza una "matriz de convolución" (kernel) que se desliza sobre la imagen.
  - Desenfoque (Blur): Promediar los colores de los píxeles cercanos.
  - Enfoque (Sharpen): Resaltar las diferencias de color entre píxeles adyacentes.
  - Detección de bordes: Algoritmos como Sobel o Canny que identifican cambios bruscos de intensidad.

- Transformaciones geométricas: Es el cambio de disposición espacial de los píxeles.
  - Escalado: Agrandar o achicar. Aquí entra la interpolación (decidir qué color poner en los huecos nuevos).
  - Rotación: Girar la malla de píxeles.

### Formatos de archivo
Se debe de definir los distintos formatos de archivos para los mapas de bits:
1. .JPG: 
Manipular mapas de bits en formato JPG es lo más utilizado en el diseño web, ya que mantiene mejor la calidad de imagen y permite su comprensión para ser almacenada y compartida a través de  Internet.
  - Es recomendable para las imágenes de tono continuo.
  - No admite transparencia.
  - En caso de que no sea para una página web y estés usando un formato para imprimir, también es una buena opción.
  - No suele usarse en la fotografía profesional.

2. .TIFF:
Estos archivos son preservados de esta forma porque las imágenes no llevan compresión, lo que es ideal si quieres fotografías de mapas de bits para archivos que imprimirás.
  - Ser archivos pesados.
  - Son admitidos por la gran mayoría de programas.
  - Suelen ser la opción de mejor calidad para las impresiones.
  - Permite transparencia.

3. .PSD: 
En cuanto a trabajos de puro diseño gráfico, .PSD es un formato de trama de Photoshop que admite todos los atributos de un archivo de este programa, como capas, objetos inteligentes, efectos y tipografía.
  - Pueden ser importados desde otros programas de Adobe.
  - Permite canales alfa (lo que vendría a ser la transparencia).
  - Mantiene las capas, las selecciones o los trazados.

4. .GIF: 
Uno de los formatos de mapas de bits más conocidos son los .GIF (Graphic Interchange Format), que ya forma parte del mundo de cualquier usuario de internet, gracias a sus archivos con poco peso y su uso en las animaciones. 
  - Disminuye el número de colores.
  - Permite transparencia, aunque de muy baja calidad.
  - Es recomendable para imágenes de colores planos.
  - Son archivos con poco peso.
  - Modo de color indexado.

5. .PNG: 
Los archivos de mapas de bits que utilizan esta extensión por lo general son utilizados en composiciones digitales o páginas web.
  - Son archivos con una buena relación de compresión.
  - Perfectas para las transparencias (8 y 24 bits).
  - Tienen muy poco peso.
  - Son ideales para imágenes con un tono continuo.

## Bibliografía
- Cardona, A. A. (s. f.). Historia y evolución de la graficación por computadora. Scribd. https://es.scribd.com/document/393263572/Historia-y-Evolucion-de-La-Graficacion-Por-Computadora
- González, J. C. (s. f.). Aspectos matemáticos de la graficación. Scribd. https://es.scribd.com/document/706271386/Aspectos-matematicos-de-la-graficacion
- HISTORIA Y EVOLUCIÓN DE LA GRAFICACIÓN POR COMPUTADORA BERNARDO GERHAR. (s. f.). Genially. https://view.genially.com/65bc786c9fa689001318901a/interactive-content-historia-y-evolucion-de-la-graficacion-por-computadora-bernardo-gerhar
- Machuca, F. (2022, 1 de abril). Aprende qué es un mapa de bits y haz que tus trabajos resalten por su calidad. Crehana. https://www.crehana.com/blog/estilo-vida/que-es-mapa-bits/
- 1.3 Aspectos matemáticos de la graficación. (s. f.). SlideShare. https://es.slideshare.net/slideshow/1-3-aspectos-matematicos-de-la-graficacion-pdf/282295700
- 1.6 Procesamiento de mapas de bits en graficación. (s. f.). SlideShare. https://es.slideshare.net/slideshow/1-6-procesamiento-de-mapas-de-bits-en-graficacion/282295902
- Valdés, A. S. (2013, 14 de septiembre). 1.4 Aspectos matemáticos de la graficación (Geometría fractal). Graficacionito. https://graficacionito.blogspot.com/2013/09/14-aspectos-matematicos-de-la.html
- Valdés, A. S. (2013, 22 de septiembre). 2.2 Representación y trazo de polígonos. Graficacionito. https://graficacionito.blogspot.com/2013/09/22-representacion-y-trazo-de-poligonos.html
 


