# web-scraping utilizando data science
# DISCLAIMER
¡Este repo se ha subido como un repositorio dedicado único y exclusivamente para **FINES ÉTICOS**! Queda bajo responsabilidad del usuario lo que puede hacer con las técnicas que aquí se describen. 
## Descripción del proyecto
Utilizando técnicas de web scraping con el lenguaje python se pretende extraer datos de una página web de libros con el fin de preparar analíticas que pueden simular tomas de decisiones clave en contextos empresariales. Para ello tomaremos como target la siguiente página: [https://books.toscrape.com/](https://books.toscrape.com/). Esta página ofrece vía libre a desarrolladores para que puedan practicar el web scraping sin ningún tipo de restricciones y problemas legales. La idea es que crearemos una petición a una página web y mediante un script preparado en python descargaremos diferentes páginas dentro de la web, obteniendo así el bruto de la información. Luego lo que haremos será emplear de alguna manera ciertos filtros para generar los datos que luego volcaremos sobre un archivo .json. Luego, mediante otro script, lo que haremos será procesar los datos generados, "limpiarlos" y presentarlos en un formato estadístico respondiendo a cuestiones de análisis. 


## Teoría acerca del web scraping
Lo primero de todo es entender qué es lo que estamos haciendo, y es que el término básicamente intenta dar una pequeña pista de lo que vamos a hacer: cacharrear en una web. “Despiezar”, “desguazar”, “cortar” o “extraer” son solo algunos sinónimos que de alguna manera pretenden hacer alusión a lo mismo: coger información contenida en las etiquetas de una página web.

Cuando un navegador accede a una página, lo que realmente recibe es un conjunto de etiquetas HTML que estructuran el contenido (títulos, párrafos, precios, imágenes, etc.). El web scraping consiste precisamente en automatizar la lectura y extracción de esa información, simulando lo que haría una persona al navegar, pero de forma mucho más rápida y sistemática.

Para ello utilizaremos la librería BeautifulSoup4 (haz clic para ver la [documentación](https://pypi.org/project/beautifulsoup4/)), que es una de las más populares para este tipo de tareas en Python.
Esta herramienta permite analizar (o parsear) el HTML y navegar por sus elementos usando selectores muy similares a los de CSS.
Si nunca la has usado o no la tienes instalada, te recomiendo que le eches un vistazo a la sección de **Preparando el entorno de trabajo**.

## ¿Por qué web scraping?

El valor del web scraping no radica únicamente en obtener datos, sino en transformar esos datos en información útil. En el contexto de Data Science, el scraping se utiliza como una primera fase de adquisición de datos, especialmente cuando las fuentes no ofrecen una API pública.

Algunos usos comunes incluyen:

* Análisis de precios y competencia en comercio electrónico.
  
* Recolección de datos de reseñas o calificaciones para análisis de sentimiento.

* Seguimiento de tendencias (por ejemplo, libros más vendidos o productos con mayor demanda).


## Fases que implican al proceso de web scraping

El proceso general se compone de varias etapas:

1. Petición (Request):
Se realiza una solicitud HTTP a una URL mediante librerías como requests. El servidor responde con el código HTML de la página.

2. Parseo (Parsing):
El HTML se interpreta con BeautifulSoup, lo que permite buscar elementos específicos (por ejemplo, el título de cada libro o su precio) utilizando métodos como .find(), .find_all() o .select().

3. Extracción:
Se recorren los elementos encontrados y se almacenan los datos en estructuras de Python (listas, diccionarios, etc.).

4. Almacenamiento:
Los datos se guardan en un formato estructurado, por ejemplo .csv, .json o directamente en una base de datos.

5. Procesamiento y análisis:
Una vez obtenidos los datos, se pueden aplicar técnicas de limpieza, transformación y visualización para extraer conclusiones relevantes.

* Automatización de informes que integran datos actualizados desde la web.

