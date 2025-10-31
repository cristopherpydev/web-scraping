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

* Automatización de informes que integran datos actualizados desde la web.

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


# Preparando el entorno de trabajo

## Instalación de librerías utilizadas en el proyecto

Primero utilizaremos la librería Beautifulsoup4, que la podemos instalar en nuestra terminal utilizando el comando: 
```
pip install beautifulsoup4
```

Una vez descargada, deberíamos descargar también pandas, una librería para dar reorganizar nuestros datos y limpiarlos. Nuevamente:
```
pip install pandas
```

También utilizaremos la librería matplotlib, pero normalmente ya viene instalada por defecto. Esta librería la usaremos para crear gráficos de nuestros datos.

## Estructura de proyecto

La idea es crearnos un directorio que se llame de alguna manera simbólica, como "proyecto" o "scraping". Esto no importa mucho, pero a partir de aquí si importa el orden de nuestros archivos y subdirectorios contenidos. 

1. Nos crearemos primero un script de python llamado scraping.py. Este programa será el encargado de realizar la petición HTTP a la página target, recopilar y parsear la información deseada. La información "en sucio" la dumpearemos en un archivo .json.
2. Luego necesitamos crear otro script de python llamado limpiar_datos.py. Este programa utilizará la librería de pandas para limpiar y formatear caracteres especiales y otras consideraciones del archivo .json anterior a otros formatos más legibles (numéricos,...). Al acabar, dumpeará la información a otro archivo .json definitivo con la información ya limpia.
3. Por último necesitamos crear otro script de python llamado analiticas.py. Este programa utilizará la librería de matplotlib para generar un informe a varias cuestiones que se plantean a lo largo de este proyecto. Para generar el informe empleará el archivo .json definitivo.

Podemos utilizar una estructura de subdirectorios si se desea. ¡Queda mucho más limpio, y eso en el mundo de la programación es un diez! 

# ¿Cómo planteé el desarrollo del proyecto?

## Enunciado

Nuestra empresa FICTICIA S.A. nos ha pedido que analicemos su ecommerce de libros. Como se está acercando Halloween nos ha pedido que hagamos un análisis de datos sobre los libros de la categoría Horror en su página web. Para ello debemos trabajar de manera eficiente en busca de respuestas claras a las siguientes preguntas:

* ¿Cuál es el libro más caro de todos?
* ¿Cuál de ellos es el menos popular por diferencia?
* ¿Cuál de ellos es el más barato?
* ¿Qué libros están agotados?
  
