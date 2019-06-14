# TRABAJO FINAL

## Cuál es el problema a tratar?

Conocer la disponibilidad de los datos de la red hidrometeorológica para poder realizar análisis espaciales.

## Por qué una experiencia interactiva ayuda a resolverlo?

Los mapas interactivos brindan una interfaz gráfica para conocer de forma ágil la ubicación de estaciones hidrometeorológicas y poder generar análisis espacio-temporales de las series históricas que registra cada estación. Adicionalmente con esta experiencia interactiva se pueden visualizar datos de forma oportuna, que por sus valores, podrían señalar algún inconveniente con el instrumento que esta tomando las mediciones de cada parámetro.

## Descripción de los datos (tipos de geometrías, atributos, sistemas de referencia, urls para descarga de la información, etc)

Los datos son de tipo punto, con proyección de coordenadas MAGNA-COLOMBIA-BOGOTÁ
Atributos: Código Estación, Nombre Estación, Coordenada X, Coordenada Y, Año, Mes, Valor de cada parámetro (Precipitación, Temperatura, Brillo Solar, Humedad, Caudales)

Datos de descarga (https://datos.gov.co/browse?q=CAR&sortBy=relevance&utf8=%E2%9C%93&page=2)


## Descripción del procesamiento realizado a los datos (ejm: transformaciones, filtros, geoprocesamiento, etc)

Los datos se descargaron en formato CSV, pero por problemas en la proyección de los datos no fué posible cargarlos directamente en CARTO, adicionalmente se requería un registro para cada lugar en cada momento en el tiempo, debido a que en la tabla original se tenía un registro por lugar con múltiples columnas de las cuales cada una era un momento en el tiempo.

Se cargaron los datos inicialmente en el paquete estadístico de Rstudio, con el fin de organizar los datos, como se indica en el párrafo anterior. Una vez se organizaron los datos estos en un software de SIG se conviritieron en formato shapefile, para subirlos a carto y generar los mapas interactivos respectivos.

Adicionalmente, se quería mostrar la distribrución espacial de la lluvia, para esto uno de los métodos más usados es la interpolación, este método permite por medio de cálculos estadísticos obtener los datos de precipitación de lugares donde no hay estaciones meteorológicas, calculando una superficie estadística a través de los valores conocidos. Para realizar este proceso se utilizó el software ArcGis, la caja de herramientas Spatial Analyst, la opción Interpolation.

## Descripción de las diferentes técnicas y métodos utilizados para la visualización de datos.
## Descripción breve de las diferentes herramientas y procedimientos utilizadas para publicar el contenido en la web.
## Ventajas / desventajas / dificultades de la publicación de mapas utilizando herramientas en la nube respecto al software desktop.
