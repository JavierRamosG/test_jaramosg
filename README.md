# Aspectos generales

Esta prueba ha sido diseñada con el objetivo de evaluar sus conocimientos para el cargo de científico/a de datos. La prueba tendrá una duración máxima de **90 minutos**. El tiempo comenzará a correr desde el momento en que terminemos de revisar las instrucciones. Las respuestas deben entregarse en un archivo con extensión **.R, .ipynb o .py**. El nombre del archivo debe seguir la siguiente estructura *nombre_apellido.extension*.      

**Importante**: El archivo debe ser entregado como un *pull request* dentro de [este](https://github.com/inesscc/prueba-tecnica) repositorio. Para ello, genere una rama con su nombre y apellido, de la siguiente manera **nombre_apellido**. En caso de que trabaje en python, agregue un archivo **requirements.txt**, con las dependencias. En caso de que tenga dificultades para trabajar con el repositorio, podrá entregarlo vía correo en formato .zip, asumiendo un descuento.     

**El uso de herramientas de inteligencia artificial no está prohibido. Si decide trabajar con IA, hágalo de manera reflexiva. Las respuestas de la IA contienen patrones que son fácilmente detectables y que no siempre se adecúan a las especificidades de la tarea que se está desarrollando. Nos interesa conocer su razonamiento sobre los problemas propuestos, de modo que sus comentarios recibirán mucha atención al momento de la evaluación. En varias secciones de la prueba el código valdrá tanto como las justificaciones de sus decisiones**      



## Problemas

### Paso 0

Clone el siguiente repositorio.

https://github.com/inesscc/prueba-tecnica.git

git@github.com:inesscc/prueba-tecnica.git

En él encontrará las instrucciones para la prueba y algunos archivos que tendrá que utilizar para responder las preguntas. 


### Clasificando texto

Usted cuenta con un conjunto de datos sobre características del empleo de las personas. Cada uno de estos empleos está asociado a un código. A continuación, se muestra un ejemplo de algunos datos:     

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


Realice las siguientes tareas:

1) Descargue la información de la tabla train desde la base de datos
2) Entrene un clasificador de texto. Incorpore el procesamiento de datos y el algoritmo que le parezcan más idóneos para la tarea.     
3) Descargue la información de la tabla test desde la base de datos
4) Haga predicciones sobre el set de testeo
5) Analice los resultados, indicando tanto las fortalezas como los espacios de mejora del modelo.  
6) Proponga (sin ejecutarlo) un plan para mejorar el desempeño de su modelo.   

### Modelo en producción

Su modelo ha sido puesto en producción. Cuenta con muestras mensuales de 100 registros cada una, que han sido etiquetadas manualmente para algunos periodos posteriores a la puesta en producción. Eso le permite obtener algunas métricas. A continuación, se muestran los resultados del desempeño del modelo a lo largo del tiempo. 

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

**Sugiera alguna hipótesis para explicar el comportamiento de los datos y elabore una estrategia (sin implementarla) para mitigar el problema. Justique con sus propias palabras cada uno de sus argumentos**  

### Procesando texto

Usted tiene que procesar datos de texto provenientes de noticias en medios de prensa. Para cada noticia, usted debe generar un resumen que no supere las 50 palabras. Los datos se encuentran en la tabla *noticias* de la base de datos. Corresponde a un dataset con 10 filas.     

Usted cuenta con una API key para utilizar un servicio llamado OpenRouter, que permite hacer inferencias de grandes modelos de lenguaje. Este [link](https://openrouter.ai/docs/quickstart) contiene un ejemplo de la documentación oficial, en el cual se muestra cómo usar el endpoint *responses* a través de *python*. 

Considere las siguientes condiciones:
- Esta es la API key para usar el servicio AGREGAR API KEY 
- Debe utilizar el modelo **google/gemini-2.5-flash-lite** para resolver la tarea.
- Debe desactivar el razonamiento, para minimizar costos
- El resultado está contenido en el *text* de un elemento *output* 

```   
 response.json()["output"][0]["content"][0]["text"]
```
Realice las siguientes tareas:

1) Descargue la tabla noticias de la base de datos
2) Genere una columna *resumen* que contenga el resumen de cada texto.    


**¡Mucho éxito!**