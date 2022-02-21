# DataCademy2022

DataCademy2022 es un reto de Platzi para comienzar tu carrera en data science e inteligencia artificial con este reto.  
Durante 5 semanas aprende los fundamentos de esta industria y conoce qué rol escoger y cómo hacerlo.  
Conoce cómo inscribirte en la primera clase abierta.

![image](https://user-images.githubusercontent.com/47682546/154909855-93dc5320-1e2e-439b-9b19-f502ee4711d0.png)
 
Índice:

## Contexto: tu trabajo como analista de datos en retail

Imagina que acabas de iniciar tu primer trabajo como Data Analyst para una nueva empresa de retail en Estados Unidos.  
Managers de ventas quieren conocer ciertos aspectos de otras empresas y te piden analizar datos de otras 25 compañías  
muy exitosas en el país.

> ***retail*** es el sector económico de empresas que se especializan en la comercialización masiva de productos o servicios  
> uniformes a grandes cantidades de clientes. Por ejemplo: Walmart, Amazon, Target, Home Depot, Best Buy, etc.

### Descarga los datos

Trabajaremos con un pequeño dataset que justamente tiene los datos de esas 25 compañías.  
Este dataset es una versión simplificada del dataset [Largest US Retailers](https://www.kaggle.com/yamqwe/largest-us-retailers-2015e) de 
[Gary Hoover](https://data.world/garyhoov). 
                                                                                                                                
Para descargar esta versión simplificada del dataset en CSV
➡️ [haz clic aquí](https://static.platzi.com/media/public/uploads/largest_us_retailers_9b00dc73-a938-46cd-af17-fcb2bd67301f.csv). ⬅️

> ‼️ Importante: utiliza esa versión simplificada del dataset.

Dentro de este dataset encontrarás las siguientes variables/columnas:

- ***Company*** (compañía)
- ***Sales*** (ventas en millones de dólares)
- ***Stores*** (cantidad de tiendas físicas)
- ***Sales/Avg. Store*** (promedio de venta por tienda física)
- ***Category*** (categoría)

### Notebook en Deepnote

Para crear tu proyecto es necesario utilizar Deepnote, ya que nos facilitará compartirlo con el mundo y entregarlo.

1. Ve a [Deepnote](https://deepnote.com/) y crea un nuevo proyecto dentro de tu espacio de trabajo personal.  Llámalo Proyecto Datacademy.
2. Dentro del proyecto sube [este notebook](https://deepnote.com/project/Tutoriales-Datacademy-7caL-o30R6SGIoYOu5Mf6Q/%2Ftemplate_proyecto_datacademy.ipynb) que incluye este template para resolver el proyecto.  
Descarga el ➡️ [template de notebook aquí](https://deepnote.com/project/Tutoriales-Datacademy-7caL-o30R6SGIoYOu5Mf6Q/%2Ftemplate_proyecto_datacademy.ipynb)  ⬅️
3. Dentro de la notebook que subiste a tu proyecto carga el CSV de los retailers que descargaste en el paso 1.
4. Importa estas librerías en tu notebook: 
- import pandas as pd
- import numpy as np
- import matplotlib.pyplot as plt
- import seaborn as sns
5. Carga tus datos del CSV con Pandas y pon manos a la obra.

### Responde preguntas del negocio

Imagina que los managers te hacen ciertas preguntas clave. Tu labor será responderlas buscando esos insights analizando los datos.

Para ello usa las cuatro librerías que acabas de importar que has conocido a lo largo de las clases del reto.

No existe una única sola forma de llegar al resultado, siéntete libre de explorar los datos como mejor te parezca con estas herramientas.  
Lo que importa al final es llegar a un resultado que sea de valor para el negocio.

La estructura que seguirás dentro del notebook será la siguiente. Para verla plantemos una pregunta sencilla que es ¿cuál empresa vendió más?

**a) Escribe tu código dentro de celdas de código**
Ejecuta el código que necesites para llegar al resultado que necesitas.

Por ejemplo, para esta información podemos utilizar el método df.sort_values('x', ascending=0).  
Servirá para poner hasta arriba del DataFrame la compañía que más ventas tuvo.

```python
df_sorted = df.sort_values('Sales', ascending=0)
df_sorted
```

Esto nos entregará el DataFrame de esta manera:

df_venta_mayor.PNG

Claramente, podemos ver que Walmart US es el que más ventas ha tenido con $658,119 millones de dólares.

Parece que con esto será suficiente, pero una visualización será de mayor valor y será más fácil de interpretar. Vamos a ello.

**b) Comparte insights con visualizaciones**  

Con ayuda de Matplotlib o Seaborn crea las gráficas que necesites para dar a conocer tu resultado e incluso enriquecerlo.

Para este caso vamos a enriquecerlo mostrando los datos de ventas de las cinco compañías que más vendieron. Lo haremos de la siguiente manera:

```python
x = df_sorted['Company'][0:5] #Aplicamos slicing como en una lista de Python.  
y = df_sorted['Sales'][0:5]
```

```python
plt.bar(x, y)
plt.title('Top 5 retailers')
plt.xlabel('Company')
plt.ylabel('Sales')
plt.xticks(rotation='vertical') #Método que se usa para rotar el texto de los puntos en X para que no se amontonen.
plt.show()
```
Obtendremos la siguiente gráfica:

top_5_retailers.PNG

Esta gráfica, además de mostrarnos que Walmart US es el que más ventas ha generado, también nos muestra que está dominando el mercado de retail  
superando al segundo lugar por cinco veces más. Esto es un insight interesante y justo escribiremos nuestras conclusiones en el siguiente paso.

**c) Conclusiones**

Debajo de tus resultados escribe conclusiones de lo que necesites resaltar de acuerdo a lo que observes. Utiliza esa intuición de los datos y dominio del negocio.  
Hazlo en una celda de texto en tu notebook.

conclusiones.PNG

Esto lo tendrás que hacer para cada una de las siguientes preguntas:

1. ¿Cuál es el promedio de ventas sin contar a la compañía dominante?
Pista: slicing.

2. ¿Cuánto dinero en ventas generó la mayoría de las compañías?
Pista: hist.

3. ¿Cuántas tiendas tiene la mayoría de las compañías?
Pista: hist.

4. ¿La cantidad de tiendas está relacionada con la cantidad de ventas? Es decir, ¿si una empresa tiene más tiendas tendrá más dinero de ventas?
Pista: scatter.

5. ¿Cuál es el rango que existe entre las ventas?
Pista: max y min

6. ¿Cuáles son las 5 empresas que más tiendas físicas tienen? ¿Cuáles de ellas están dentro de las 5 empresas que más ventas tuvieron?
Pista: pregunta de ejemplo

Nota: puede que en algunos casos una visualización no sea necesaria, pero siempre puedes buscar como enriquecer tu resultado con ella.

Responde estas preguntas dentro de la primera sección de tu notebook.

### Preguntas opcionales

Para elevar la dificultad del proyecto tenemos preguntas opcionales. Para resolverlas es probable que tengas que investigar más métodos de Pandas, NumPy y Matplotlib.

Si decides aceptarlas recuerda que tenemos dos tutoriales que podrán ayudarte:

[Guía definitiva para dominar Pandas 🐼](https://platzi.com/blog/pandas/)  
[Guía definitiva para dominar NumPy ➕](https://platzi.com/blog/numpy/)  
[Guía definitiva para dominar Matplotlib 📊](https://platzi.com/blog/matplotlib/)

Preguntas:

7. ¿Qué categoría de compañía generó más ventas?

8. ¿Cuál es la compañía que en relación con su cantidad de tiendas físicas genera más ventas?

9. ¿Cuáles compañías venden de forma exclusivamente online? ¿Sus ventas destacan sobre las que también tienen tiendas físicas?

De estas tres preguntas responde las que decidas aceptar dentro de la segunda sección de tu notebook con el mismo formato que las primeras.  
¡Espero puedas resolverlas todas! 💪

### Tus propias preguntas

De la misma manera como has resuelto las preguntas anteriores, es momento de hacerle tus propias preguntas a los datos.

Comparte en la última sección de tu notebook de 1 a 3 preguntas de aspectos que te parezcan interesantes y relevantes de los datos.

Mentoría para los mejores 10 proyectos
Las personas que entreguen los 10 mejores proyectos participarán en una mentoría con personas expertas en data science del team Platzi.

Aspectos a evaluar:

- Responder la mayor cantidad de preguntas.
- Valor y veracidad de la información encontrada con las preguntas.
- Valor y veracidad de la información que entregues con los resultados de tus propias preguntas.
- Storytelling: visualizaciones fáciles de entender que muestren información valiosa, claridad y valor de tus conclusiones para cada hallazgo.

### Bibliografía

- [Datacademy](https://platzi.com/cursos/datacademy/)
- [Bitacora Datacademy Semana 1](https://platzi.com/tutoriales/2681-datacademy/12788-bitacora-reto-dataacademy-semana1/)
- [Bitacora Datacademy Semana 2](https://platzi.com/tutoriales/2681-datacademy/12855-bitacora-datacademy-semana-2/)
- [Atajos VSCODE](https://platzi.com/tutoriales/2681-datacademy/12870-atajos-vscode/)
- [Crea tu proyecto del reto](https://platzi.com/clases/2681-datacademy/45530-crea-tu-proyecto-del-reto/)


---
@ferjml97
