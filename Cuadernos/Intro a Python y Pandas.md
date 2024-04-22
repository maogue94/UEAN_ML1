# Introducción a Python y Pandas

## Introducción

En este capítulo se aborda el análisis de datos con pandas, una librería de Python que nos permite trabajar con tablas de datos de forma eficiente. `pandas` nos ofrece estructuras de datos flexibles y potentes para manipular y analizar datos, así como herramientas para importar y exportar datos desde diferentes fuentes. En este capítulo, veremos cómo cargar un dataset en un DataFrame de pandas, explorar los datos, limpiarlos, transformarlos y visualizarlos.

## Los datasets

Si bien hay muchas fuentes de datos disponibles en la web, para este curso usaremos datasets del repositorio de datos de la Universidad de California, Irvine (UCI). Este repositorio contiene una amplia variedad de datasets de diferentes dominios, como ciencia de datos, aprendizaje automático, inteligencia artificial, entre otros. Los datasets de UCI son ampliamente utilizados en la comunidad de aprendizaje automático para probar algoritmos y modelos en diferentes problemas.

El enlace al repositorio de datos de UCI es el siguiente: [UCI Machine Learning Repository](https://archive.ics.uci.edu/ml/index.php). Varios de los datasets que se encuentran en este repositorio son utilizados en la literatura científica y en competencias de aprendizaje automático. En este capítulo, usaremos el dataset **Adult** de UCI para realizar un análisis de datos con pandas.



## Google Colab

Google Colab es una herramienta online que nos permite ejecutar código de Python en la nube, sin necesidad de instalar nada en nuestro ordenador. Además, podemos acceder a recursos de computación avanzados, como GPUs o TPUs, para procesar grandes cantidades de datos o entrenar modelos de aprendizaje automático. Google Colab también nos permite compartir nuestros notebooks con otros usuarios y colaborar en tiempo real.

Para usar Google Colab, solo necesitamos una cuenta de Google y un navegador web. Podemos acceder a la página principal de Google Colab en <https://colab.research.google.com/> y seguir estos pasos para crear o abrir un notebook:

- Para crear un nuevo notebook, hacemos clic en el botón "Nuevo notebook" en la esquina superior izquierda, o seleccionamos "Archivo" y luego "Nuevo notebook" en el menú superior.
- Para abrir un notebook existente desde Google Drive o Github, usamos las opciones que aparecen en la página principal.

Un notebook es un documento que combina celdas de texto y de código, que se pueden ejecutar de forma interactiva. Las celdas de texto nos permiten explicar lo que hacemos con el código, usando el formato Markdown. Las celdas de código nos permiten escribir y ejecutar instrucciones de Python, usando el entorno de ejecución de Google Colab, que tiene instaladas muchas librerías útiles para el análisis de datos y el aprendizaje automático. Para ejecutar una celda de código, podemos usar el botón de play que aparece al lado de la celda, o presionar las teclas Ctrl+Enter. El resultado de la ejecución se mostrará debajo de la celda.

Las **celdas de texto** son espacios donde podemos escribir texto enriquecido, usando el formato Markdown. El formato Markdown nos permite usar diferentes estilos de letra, como negrita o cursiva, insertar enlaces, imágenes, ecuaciones matemáticas o listas. Para editar una celda de texto, hacemos doble clic sobre ella y usamos la barra de herramientas que aparece encima. Para ver el resultado final, presionamos Shift+Enter o hacemos clic fuera de la celda.

**Un tutorial elemental de cómo funciona Markdown**

Para complementar el texto con formato Markdown, podemos usar celdas de texto en nuestro notebook. El formato Markdown es un lenguaje de marcado ligero que nos permite crear documentos con un aspecto profesional, usando una sintaxis sencilla y fácil de aprender. Algunas de las ventajas de usar Markdown son:

\- Es compatible con HTML, por lo que podemos insertar etiquetas HTML en nuestro texto si queremos usar alguna función que no esté disponible en Markdown.

\- Se puede convertir a otros formatos, como PDF, Word o LaTeX, usando herramientas externas.

\- Es ampliamente usado en plataformas de desarrollo y colaboración, como Github, Stack Overflow o Medium.

A continuación, vamos a ver algunos ejemplos de cómo usar Markdown para dar formato a nuestro texto.

**Encabezados**

Para crear encabezados de diferentes niveles, usamos el símbolo # al principio de la línea, seguido de un espacio y el texto del encabezado. El número de # indica el nivel del encabezado, desde 1 (el más grande) hasta 6 (el más pequeño). Por ejemplo:

\# Este es un encabezado de nivel 1

\## Este es un encabezado de nivel 2

\### Este es un encabezado de nivel 3

\#### Este es un encabezado de nivel 4

\##### Este es un encabezado de nivel 5

\###### Este es un encabezado de nivel 6

**Estilos de letra**

Para aplicar estilos de letra como negrita, cursiva o tachado, usamos los símbolos \*, \*\* o ~~ alrededor del texto que queremos modificar. Por ejemplo:

\- Para escribir en \*\*negrita\*\* usamos dos asteriscos: `\*\*negrita\*\*`.

\- Para escribir en \*cursiva\* usamos un asterisco: `\*cursiva\*`.

\- Para escribir con ~~tachado~~ usamos dos virgulillas: `~~tachado~~`.

\- Podemos combinar estos estilos usando más de un símbolo: `\*\*\*negrita y cursiva\*\*\*`, `\*\*~negrita y tachado~\*\*` o `\*~cursiva y tachado~\*`.

**Listas e imágenes**

Para escribir una lista con viñetas, usamos el signo menos al comienzo de cada línea: `- elemento 1`, `- elemento 2`, etc. Por ejemplo:

- Esta es una lista
- Con tres elementos
- Muy sencillos

Para escribir una lista numerada, usamos un número seguido de un punto al comienzo de cada línea: `1. elemento 1`, `2. elemento 2`, etc. Por ejemplo:

1. Este es el primer elemento
1. Este es el segundo elemento
1. Este es el tercer elemento

Usamos la etiqueta <img> con el atributo `src` para insertar una imagen, indicando la dirección web donde se encuentra la imagen. También podemos modificar el tamaño de la imagen con los atributos `width` y `height`. Por ejemplo:

![logo](https://izainea.github.io/mercadeia/_static/logo.png)

Las **celdas de código** son espacios donde podemos escribir y ejecutar instrucciones de Python. Estas instrucciones pueden definir variables, funciones, clases, importar librerías, manipular datos, crear gráficos o aplicar algoritmos de aprendizaje automático. Para editar una celda de código, hacemos clic sobre ella y escribimos el código que queremos. Para ejecutarlo, usamos el botón de play o las teclas Ctrl+Enter. El resultado de la ejecución se mostrará debajo de la celda, junto con cualquier mensaje de error o advertencia que se produzca. Podemos usar la opción "Reiniciar entorno de ejecución" del menú "Entorno de ejecución" para borrar todas las variables y reiniciar el notebook.

Python es un lenguaje de programación de alto nivel, que se caracteriza por su simplicidad y flexibilidad. Python tiene una sintaxis clara y consistente, que facilita la lectura y escritura del código. Además, Python es un lenguaje interpretado, lo que significa que no necesita ser compilado antes de ejecutarse, sino que el código se traduce a lenguaje máquina en tiempo real.

Para escribir código en Python, debemos seguir algunas reglas básicas, como:

- Usar indentación para delimitar los bloques de código. La indentación consiste en agregar espacios o tabulaciones al inicio de cada línea de un bloque. Todos los bloques que pertenecen al mismo nivel deben tener la misma indentación.

- Usar dos puntos (:) para indicar el inicio de un bloque. Por ejemplo, después de una declaración if, for o def, se debe colocar dos puntos y luego indentar el bloque correspondiente.

- Usar comillas simples (' ') o dobles (" ") para crear cadenas de texto. Por ejemplo: 'Hola', "Python".

- Usar el símbolo # para crear comentarios. Los comentarios son líneas de texto que no se ejecutan y sirven para explicar el código o dejar notas. Por ejemplo: # Esto es un comentario

- Usar mayúsculas y minúsculas de forma consistente. Python distingue entre mayúsculas y minúsculas, lo que significa que las variables, funciones o clases con nombres diferentes según el uso de mayúsculas y minúsculas son tratadas como entidades distintas. Por ejemplo: nombre, Nombre y NOMBRE son tres variables diferentes.

Estas son algunas de las reglas elementales de programación en Python. Para aprender más sobre este lenguaje, podemos consultar la documentación oficial o algún tutorial en línea. Google Colab nos ofrece un entorno interactivo para practicar y experimentar con Python sin necesidad de instalar nada en nuestro ordenador.

Un ejemplo de cómo usar Google Colab para revisar nuestro dataset es el siguiente:

```python
# Importar las librerías necesarias para el análisis de datos
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
```

El anterior código importa las librerías necesarias para el análisis de datos. La librería pandas nos permite trabajar con tablas de datos, la librería numpy nos permite realizar operaciones matemáticas y la librería matplotlib nos permite crear gráficos. Estas librerías son muy útiles para el análisis de datos y la visualización de resultados.

En el caso de los datasets de UCI, podemos cargarlos directamente con la herramienta de UCI, aprovechemos para repasar conceptos básicos de Python:

```python
### Instalación de librería ucimlrepo
pip install ucimlrepo
```

Ahora cargamos los datasets de UCI con la librería ucimlrepo:

```python
# Cargar el dataset Adult de UCI

from ucimlrepo import fetch_ucirepo 
  
# fetch dataset (cuando decimos fetch, estamos diciendo que vamos a traer algo)
adult = fetch_ucirepo(id=2) 
  
# Datos (como dataframes de pandas) 
X = adult.data.features 
y = adult.data.targets 
  
# metadata 
print(adult.metadata) 
  
# variable information 
print(adult.variables) 
```

El código anterior carga el dataset Adult de UCI y muestra información sobre los datos y las variables. El dataset Adult contiene información sobre personas, como su edad, educación, ocupación, estado civil, etc. Este dataset es ampliamente utilizado en la comunidad de aprendizaje automático para probar algoritmos de clasificación y regresión.






## Copilotos LLM
Los copilotos LLM son asistentes de escritura inteligentes que nos ayudan a programar en diferentes lenguajes usando el lenguaje natural. En esta clase usaremos el copiloto LLM para Python, que nos permite escribir código en Python usando frases en español. Para usar el copiloto LLM para Python, debemos seguir las siguientes instrucciones:

- Escribir la frase en español que describe lo que queremos hacer con el código, precedida por el símbolo #.
- Presionar la tecla Tab para que el copiloto LLM genere el código en Python correspondiente a la frase.
- Revisar el código generado y modificarlo si es necesario.
- Repetir el proceso hasta completar el análisis de datos.

## Análisis de datos
Para realizar el análisis de datos de la tabla, seguiremos los siguientes pasos:

1. Importar las librerías necesarias para el análisis de datos.
1. Cargar el dataset desde el archivo csv.
1. Explorar el dataset y realizar un análisis exploratorio de datos (EDA).
1. Visualizar el dataset y crear gráficos que muestren la distribución de las variables y las relaciones entre ellas.