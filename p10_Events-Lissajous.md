# Práctica 10. Programación Gráfica Orientada a Eventos. Curvas de Lissajous
### Factor de ponderación: 10

### Objetivos
Los objetivos de esta tarea son poner en práctica:
* Conceptos básicos de Programación orientada a eventos en TypeScript.
* Conceptos de Programación Gráfica en TypeScript usando la API Canvas.
* Metodologías y conceptos de Programación Orientada a Objetos en TypeScript.
* Principios y Buenas prácticas de programación Orientada a Objetos.
* El uso de elementos HTML básicos.

### Rúbrica de evaluacion del ejercicio
Se señalan a continuación los aspectos más relevantes (la lista no es exhaustiva)
que se tendrán en cuenta a la hora de evaluar esta práctica:
* Se valorará la realización de las diferentes tareas que se proponen
* El comportamiento del programa debe ajustarse a lo descrito en este documento
* Capacidad de la programadora de introducir cambios en el programa desarrollado
* Se acredita conocimiento y puesta en práctica de principios y buenas prácticas de programación orientada a objetos
* Saber corregir bugs en sus programas utilizando el depurador de Visual Studio Code
* Deben usarse estructuras de datos adecuadas para representar los diferentes elementos que intervienen en el problema
* Ser capaz de desarrollar programas simples en TypeScript en el entorno Linux de la VM de la asignatura usando
  `ts-node`
* Ser capaz de generar documentación para sus programas TS utilizando
  [TypeDoc](https://typedoc.org/)
  y de visualizar dicha documentación en un servidor web
* Acreditar que conoce las etiquetas de 
  [JSDoc](https://jsdoc.app/)
* El alumnado debe ser capaz de resolver problemas tanto en JS como en TS en la plataforma Exercism subiendo sus soluciones a la misma
* Ser capaz de desarrollar tests unitarios para sus programas utilizando
  [Jest](https://jestjs.io/)
* Acreditar su capacidad para configurar y utilizar 
  [ESLint](https://eslint.org/)
y que es capaz de trabajar con la misma en Visual Studio Code
* El alumnado ha de acreditar que es capaz de desarrollar programas de la plataforma Jutge
* Se comprobará que el código que el alumnado escribe se adhiere a las reglas de las Guías de Estilo de Google para 
[TypeScript](https://google.github.io/styleguide/tsguide.html)
y/o
[JavaScript](https://google.github.io/styleguide/jsguide.html)
* Todas las prácticas realizadas hasta la fecha, incluída la que se presenta para su evaluación, se encuentran alojadas en repositorios privados de GitHub.
* Acreditar que es capaz de editar ficheros de forma remota en su VM usando Visual Studio Code

### Indicaciones de caracter general

* La aplicación que desarrolle ha de ser orientada a objetos.
Ponga en práctica en su desarrollo los fundamentos, principios y buenas prácticas de la OOP así como los
conocimientos que haya adquirido en el uso de patrones de diseño.

* Configure adecuadamente ficheros `package.json` y `tsconfig.json` en el directorio raíz de su proyecto que
permitan gestionar las dependencias del mismo.

* Previo a la implementación de cada clase, diseñe y desarrolle un conjunto de tests para probar el correcto
funcionamiento de todos los métodos públicos.

* Utilice un fichero distinto para el código de cada una de las clases que intervienen en su programa.

* Encapsule las clases en módulos que exporten la correspondiete clase hacia otros programas clientes que pudieran utilizarla.

* Configure para la práctica una página web que sirva de índice para mostrar la documentación generada por
Typedoc para esta práctica.

* Todo el código estará ubicado en el directorio `src` del proyecto. Use subdirectorios de éste si le resulta conveniente.

* Antes de comenzar a desarrollar su programa dedique el tiempo necesario a diseñar la estructura de clases que
utilizará en su programa, así como las relaciones existentes entre las mismas.
Desarrolle un diagrama UML para esas clases, que ha de añadir a la página índice de esta práctica.
Asegúrese de la corrección de su diagrama.
Una aplicación para la realización de diagramas UML como
[Mermaid](https://mermaid.live/edit#pako:eNptkU1PwzAMhv9KlBOI9Q9UuyC2SRx22m2KhNzEdFbzAfnQBKP_nbSlYXT4ZD-OX72xL1w6hbzmUkMIG4LWgxGW5Xi0ZECz9VdVsU2S3S3dUTjd0iM2Hv7gmj2QjQxaXOJD9GRb1qJV6K-bw0jYg8np3f2iYSDiDEfbo73LBFgRbRC6J6edL41wJjMP5vI9gezmur_WGz5W9KrBe6BPfLY7xFiwBLuF-O_8uIJfQ41zmlF4OZNWBfpkF7Nz8BU36A2QyncZVQSPJzQoeJ1Tha-QdBRc2D4_TW8q72OrKDrP6-gTrjik6A4fVs719ObnuhPsvwES3pny)
puede resultarle útil para esta finalidad, aunque puede usar cualquier otro programa que conozca, 
o simplemente papel y bolígrafo.

* Realice, como siempre, un diseño incremental del programa comprobando cada una de las funcionalidades que añade, siguiendo un
desarrollo TDD.

### Las curvas de Lissajous
Las 
[curvas de Lissajous](https://es.wikipedia.org/wiki/Curva_de_Lissajous)
son las curvas que recorre un punto sometido a un doble movimiento armónico simple en dos direcciones perpendiculares. 

La forma de la curva depende exclusivamente de la relación entre las frecuencias de los dos movimientos, 
`a/b` y de su desfase *phi*. 
Si `a/b = 1`, la curva es un segmento, una elipse o una circunferencia en función del desfase. 
Si este cociente es racional, la curva será cerrada.
Aunque para algunos valores de `a` y `b`pueda parecer abierta, como `a = b = 1` y `a = 3` y `b = 9` con desfase *phi* = 0, 
en realidad la curva se recorre dos veces, en un sentido y otro. 
En cambio si el cociente es irracional, la curva será abierta y densa en el cuadrado `[0, 1] x [0, 1]`, en el sentido de que 
pasa arbitrariamente cerca de cualquier punto contenido en él.
Consulte 
[esta
referencia](https://www.investigacionyciencia.es/revistas/investigacion-y-ciencia/el-nuevo-coronavirus-796/las-figuras-de-lissajous-18475)
si quiere conocer la historia de estas curvas y
[estos
vídeos](https://www.investigacionyciencia.es/blogs/tecnologia/14/posts/las-figuras-de-lissajous-videos-18493)
si quiere ver las curvas y saber cómo generarlas físicamente.

Utilice
[esta página](https://academo.org/demos/lissajous-curves/) [2]
interactiva para visualizar la figura cambiando interactivamente los parámetros de la curva.

### La clase *Lissajous*
En esta práctica se propone desarrollar una aplicación
que posibilite la visualización en una página web de curvas de Lissajous.

Tenga en cuenta las siguientes especificaciones a la hora de diseñar su programa:

* Haga que el canvas junto con el área de entrada de datos ocupe la mayor parte del viewport de su navegador.

* La curva comenzará a dibujarse automáticamente una vez cagada la página en el navegador, sin esperar por ninguna interacción por parte del usuario.

* Para la actualización del dibujo en el navegador se propone utilizar una aproximación similar a
la que se ha utilizado en el ejemplo del reloj estudiado en clase.
Ello pasa por el uso de una función `update()` cuyo código JS podría ser similar al siguiente:

```js
function update() {
  time = (Date.now() - startTime) / 1000;
  context.clearRect(...);
  draw();
  requestAnimationFrame(update);
}
``` 
Aunque esta no es la única posibilidad disponible. 
Puede Ud. explorar otras si lo desea.

En ese código la variable `time` almacena el instante de tiempo actual, necesario para realizar la animación.
La finalidad del resto de funciones se deduce de su nombre y contexto. 
Puede asimismo consultarse la documentación sobre las mismas.

El diseño de su página, que ha de imitar el de la de referencia,
brinda una oportunidad para practicar los elementos HTML y CSS que se han estudiado hasta ahora.
No se pretende que se utilicen elementos no estudiados hasta esta fecha.

### Presentación de resultados
La visualización de la ejecución del programa se realizará a través de una página web alojada
en la máquina IaaS-ULL de la asignatura y cuya URL tendrá la forma:

[1] `http://10.6.129.123:8080/einstein-albert-lissajous.html`

en la que se incustará un lienzo (canvas) para dibujar las curvas.
Sustituya *Albert Einstein* por su nombre y apellido en la URL de su página
y la dirección IP anterior por la correspondiente a su máquina IaaS.

Utilice código HTML y CSS para lograr una página funcional y visualmente correcta,
imitando en lo posible  la apariencia de [2] 
[esta página](https://academo.org/demos/lissajous-curves/)
que se tomará como referencia. 

La página que Ud. diseñe ha de contener el canvas de dibujo de las curvas (área cuadriculada en
la web de referencia y una columna con los campos de texto que permitan introducir valores de los parámetros
(columna derecha en la web [2] de referencia).
En esa columna de la derecha puede Ud. utilizar campos de texto para introducir los valores de los parámetros
de la curva. 
Si lo desea, investigue asimismo cómo incluir *sliders* (a través de la etiqueta '<input>' de HTML) para
modificar los valores de los parámetros usando *sliders* controlados con el ratón.

Se propone además que su página muestre
* Texto explicativo de las curvas de Lissajous
* Enlaces a páginas de referencia que se hayan utilizado para realizar este trabajo.
* Cualquier elemento que les parezca oportuno e interesante


Diseñe asimismo otra página HTML simple 

[3] `http://10.6.129.123:8080/index.html`

que sirva de "página índice" para los ejercicios de la sesión de evaluación de la práctica.
La página [1] será uno de los enlaces de [3] y a su vez [1] tendrá un enlace "Home" que apunte a [3].
Enlace también en la página índice [3] la página que contiene la documentación de su proyecto generada con
Typedoc y también la página 

[4] `http://10.6.129.123:8080/uml.html`

que muestre el diagrama UML de las clases que intervienen en su aplicación.

## Referencias
* [Lissajous Curves](https://academo.org/demos/lissajous-curves/) An interactive demonstration of Lissajous curves
* [TypeDoc](https://typedoc.org/)
* [Google TypeScript Style Guide](https://google.github.io/styleguide/tsguide.html)
* [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html)
* [ESLint](https://eslint.org/)
* [JSDoc](https://jsdoc.app/)
* [PAI Code Examples](https://github.com/ULL-ESIT-PAI-2022-2023/PAI-class-code-examples)
