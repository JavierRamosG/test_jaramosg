# Aspectos generales

La presente prueba ha sido diseñada para evaluar sus conocimientos para el cargo de científico/a de datos. La prueba tendrá una duración máxima de **90 minutos**. El tiempo comenzará a correr desde el momento en que terminemos de revisar las instrucciones. Las respuestas deben entregarse en un archivo con extensión **.R, .ipynb o .py**. El nombre del archivo seguir la siguiente estructura *nombre_apellido.extension*.      

**Importante**: El archivo debe ser entregado como un *pull request* dentro de [este](https://github.com/inesscc/prueba-tecnica) repositorio. En caso de que tenga dificultades para trabajar con el repositorio, podrá entregarlo vía correo en formato .zip, asumiendo un descuento.     

**El uso de herramientas de inteligencia artificial no está prohibido. Si decides trabajar con IA, hazlo de manera reflexiva. Las respuestas de la IA contienen patrones que son fácilmente detectables y que no siempre se adecúan a las especificidades de la tarea que se está desarrollando. Nos interesa conocer tu razonamiento sobre los problemas propuestos, de modo que tus comentarios recibirán mucha atención al momento de la evaluación.En varias secciones de la prueba el código valdrá tanto como las justificaciones de tus decisiones**      



## Problemas

### Paso 0

Clona el siguiente repositorio.

https://github.com/inesscc/prueba-tecnica.git

git@github.com:inesscc/prueba-tecnica.git

En él encontrás las instrucciones para la prueba y algunos archivos que tendrás que utilizar para responder las preguntas. 


### Clasificando texto

Usted cuenta con un conjunto de datos sobre características del empleo de las personas. Cada uno de estos empleos está asociado a un código de actividad económica. A continuación, se muestra un ejemplo de algunos datos:     

| id | actividad | oficio | tareas | cod_final |
|---|---|---|---|---|
| 0 | producción uva exportación | temporera agrícola | mantenimiento de parronales | 01 |
| 1 | corporación municipal | profesor mecánico industrial | preparar clases, enseñar | 84 |
| 4 | contratista de rrhh para obras de construcción | trabajador de construcción | veredas | 41 |
| 5 | municipalidad de puerto natales | técnico paramedico | toma de signos vitales, entrega de horas a pacientes, tratamientos inyectables etc. | 84 |
| 7 | guardias seguridad y proteccion | administrador de contrato | administrar dirigir contratar personal | 80 |


**El objetivo es construir un clasificador de texto para aprender a predecir la variables *cod_final*.**

Para ello usted cuenta con una partición *train* y otra *test*. Los datos ya han sido preparados y se encuentran en las tablas **train** y **test** en una base de datos mysql. Los datos de la conexión son los siguientes:

- host="sql.freedb.tech"
- port=3306
- user="u_y8tlWZ"
- password="wSkxw3xbhsQg"
- database="freedb_N4nnid0a"


Realiza las siguientes tareas:

1) Descarga la información de la tabla train
2) Entrena un clasificador de texto.    
3) Descarga la información de la tabla test
4) Haz predicciones sobre el set de testeo
5) Analiza los resultados, indicando tanto las fortalezas como los espacios de mejora del modelo. 
6) Proponga (sin ejecutarlo) un plan para mejorar el desempeño de su modelo.   

### Modelo en producción

Tu modelo ha sido puesto en producción. Cuentas con muestras de 100 registros cada una, que han sido etiquetadas manualmente para algunos meses posteriores a la puesta en producción. Eso te permite obtener algunas métricas. A continuación, se muestran los resultados del desempeño del modelo a lo largo del tiempo. 

- **Testing**: 
    * Acc: 0.938 
    * Macro F1: 0.823 

- **Mes 3**:  
    * Acc: 0.923 
    * Macro F1: 0.812 
 
- **Mes 6** 
    * Acc: 0.913 
    * Macro F1: 0.796 
 
- **Mes 10** 
    * Acc: 0.85 
    * Macro F1: 0.74 

**Sugiera alguna hipótesis para explicar el comportamiento de los datos y elabore una estrategia (sin implementarla) para mitigar el problema. Justique cada uno de sus argumentos**  

### Procesando texto

Usted tiene que procesar datos de texto provenientes de noticias en medios de prensa. Para cada noticia, usted debe generar un resumen que no supere las 50 palabras. Los datos se encuentran en la tabla *noticias* de la base de datos.    

Usted cuenta con una API key para utilizar un servicio llamado OpenRouter, que permite hacer inferencias de grandes modelos de lenguaje. El siguiente link contiene un ejemplo de la documentación oficial que muestra cómo usar el servicio.  

Realice las siguientes tareas:

1) Descargue la tabla noticias de la base de datos
2) Procese los textos para generar el resultado solicitado. Utilice la estructura de datos que le parezca más adecuada.    



**¡Mucho éxito!**