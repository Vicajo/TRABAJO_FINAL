# TRABAJO FINAL

## Cuál es el problema a tratar?

Conocer la disponibilidad de los datos de la red hidrometeorológica para poder realizar análisis espaciales.

## Por qué una experiencia interactiva ayuda a resolverlo?

Los mapas interactivos brindan una interfaz gráfica para conocer de forma ágil la ubicación de estaciones hidrometeorológicas y poder generar análisis espacio-temporales de las series históricas que registra cada estación. Adicionalmente con esta experiencia interactiva se pueden visualizar datos de forma oportuna, que por sus valores, podrían señalar algún inconveniente con el instrumento que esta tomando las mediciones de cada parámetro.

## Descripción de los datos (tipos de geometrías, atributos, sistemas de referencia, urls para descarga de la información, etc)

Los datos son de tipo punto, con proyección de coordenadas MAGNA-COLOMBIA-BOGOTÁ
Atributos: Código Estación, Nombre Estación, Coordenada X, Coordenada Y, Año, Mes, Valor de cada parámetro (Precipitación, Temperatura, Brillo Solar, Humedad, Caudales)

Datos de descarga (https://datos.gov.co/browse?q=CAR&sortBy=relevance&utf8=%E2%9C%93&page=2)

Adicionalmente para generar los mapas producto de análiis espacial, se cargaron en formato shapefile tipo polígono, con proyección de coordenadas MAGNA-COLOMBIA-BOGOTÁ, los datos de las subcuencas del Río Bogotá y las Isoyetas


## Descripción del procesamiento realizado a los datos (ejm: transformaciones, filtros, geoprocesamiento, etc)

Los datos se descargaron en formato CSV, pero por problemas en la proyección de los datos no fué posible cargarlos directamente en CARTO, adicionalmente se requería un registro para cada lugar en cada momento en el tiempo, debido a que en la tabla original se tenía un registro por lugar con múltiples columnas de las cuales cada una era un momento en el tiempo.

Se cargaron los datos inicialmente en el paquete estadístico de Rstudio, con el fin de organizar los datos, como se indica en el párrafo anterior. Una vez se organizaron los datos estos en un software de SIG se conviritieron en formato shapefile, para subirlos a carto y generar los mapas interactivos respectivos.

Adicionalmente, se quería mostrar la distribrución espacial de la lluvia, para esto uno de los métodos más usados es la interpolación, este método permite por medio de cálculos estadísticos obtener los datos de precipitación de lugares donde no hay estaciones meteorológicas, calculando una superficie estadística a través de los valores conocidos. Para realizar este proceso se utilizó el software ArcGis, la caja de herramientas Spatial Analyst, la opción Interpolation.

## Descripción de las diferentes técnicas y métodos utilizados para la visualización de datos.

La visualización de los datos se realizó en puntos por categorías, donde se asigna una rampa de colores, de acuerdo al valor de cada parámetro. 
Adicionalmente se agregaron gráficos de barras, fórmulas con los valores medios, máximos y mínimos, y la linea de tiempo.
Se genera un mapa para cada parámetro registrado en las estaciones hidrometeorológicas (Precipitación, Temperatura, Brillo Solar, Humedad y Caudales.

## Descripción breve de las diferentes herramientas y procedimientos utilizadas para publicar el contenido en la web.

1. Se ingresa a la página web: carto.com
2. Se inicia sesión con la cuenta previamente creada
3. Se ingresa a Create dataset, new dataset, arrastra el shapefile de cada parámetro.
4. posteriormente click en la pestaña Map para visualizar nuestra capa en el mapa, y establecemos el BaseMap deseado. 
5. En el menú generamos una simbología establecieendo una rampa de colores de acuerdo a la clasificación del dato del valor.
6. Se adicionan los Widgets deseados, en este caso se adicionó el que permite graficar los datos en un diagrama de barras, otro que permite conocer los valores medios, máximos y mínimos que se registran según el extent del mapa y otro para visualizar el tiempo de los datos
7. Se publicó cada mapa en la opción PUBLISH. 
8. Adicionalmente se generaron dos mapas producto del análisis espacial de los datos. Para el primero se adicionó un análisis en CARTO, el cual consiste en cruzar los polígonos de las subcuencas del Río Bogotá, con los datos de precipitación, para así conocer cuales estaciones se encuentran dentro de la cuenca del río Bogotá y cuál es su valor medio. Para el segundo se siguió el mismo procedimiento indicado en los pasos 1 - 6. Finalmente se publicaron estos mapas con la opción PUBLISH.

## Ventajas / desventajas / dificultades de la publicación de mapas utilizando herramientas en la nube respecto al software desktop.

Es una herramienta que cuenta con un buen nivel de usabilidad, por lo tanto es muy amigable y rápida para la creación del mapa, pero es posible que se quede corta en cuanto a los Widgets pues opciones como filtros para el usuario final no estan disponibles, por otra parte al generar un análisis esto desaparece la capa original y se pierden las configuraciones realizadas sobre este, como también no permite generar esos análisis en capas temporales.
Otra desventaja es que no permite realizar reproyecciones a diferentes sistemas de coordenadas.

# PRESENTACIÓN 

[DATOS DE LA RED HIDROMETEOROLÓGICA DE LA CAR CUNDINAMARCA ](https://slides.com/vivianacarolinadiazgarnica/estado-red-hidrometeorologica-car)


