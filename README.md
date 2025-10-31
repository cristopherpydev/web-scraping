# web-scraping utilizando data science

## Descripción del proyecto
Utilizando técnicas de web scraping con el lenguaje python se pretende extraer datos de una página web de libros con el fin de preparar analíticas que pueden simular tomas de decisiones clave en contextos empresariales. Para ello tomaremos como target la siguiente página: [https://books.toscrape.com/](https://books.toscrape.com/). Esta página ofrece vía libre a desarrolladores para que puedan practicar el web scraping sin ningún tipo de restricciones y problemas legales. La idea es que crearemos una petición a una página web y mediante un script preparado en python descargaremos diferentes páginas dentro de la web, obteniendo así el bruto de la información. Luego lo que haremos será emplear de alguna manera ciertos filtros para generar los datos que luego volcaremos sobre un archivo .json. Luego, mediante otro script, lo que haremos será procesar los datos generados, "limpiarlos" y presentarlos en un formato estadístico respondiendo a cuestiones de análisis. 


## Teoría acerca del web scraping
Lo primero de todo es entender qué es lo que estamos haciendo, y es que el término básicamente intenta dar una pequeña pista de lo que vamos a hacer: cacharrear en una web. "Despiezar", "desguazar", "cortar" o "extraer" de alguna manera información contenida en las etiquetas de una página web. 

Para ello utilizaremos la librería beautifulsoup4 [documentación](https://pypi.org/project/beautifulsoup4/)


