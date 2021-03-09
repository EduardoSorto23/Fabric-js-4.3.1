# Fabric-js-4.3.1

Hoy me gustaría presentarte Fabric.js , una poderosa biblioteca de Javascript que hace que trabajar con el lienzo HTML5 sea muy sencillo. Fabric proporciona un modelo de objeto faltante para el lienzo, así como un analizador de SVG, una capa de interactividad y un conjunto completo de otras herramientas indispensables. Es un proyecto totalmente de código abierto, con licencia del MIT, con muchas contribuciones a lo largo de los años.

Fabric comenzó alrededor de 2010, después de descubrir las dificultades de trabajar con la API de lienzo nativa. El autor original estaba creando un editor de diseño interactivo para printio.ru , su startup que permite a los usuarios diseñar su propia ropa. El tipo de interactividad que querían solo existía en las aplicaciones Flash en esos días. Incluso ahora, muy pocos se acercan a lo que se hizo posible con Fabric.

¡Miremos más de cerca!

Canvas nos permite crear algunos gráficos absolutamente increíbles en la web en estos días. Pero la API que proporciona es decepcionantemente de bajo nivel . Una cosa es si simplemente queremos dibujar algunas formas básicas en el lienzo y olvidarnos de ellas. Pero tan pronto como hay necesidad de cualquier tipo de interacción, cambio de imagen en cualquier punto o dibujo de formas más complejas, la situación cambia drásticamente.

Fabric tiene como objetivo resolver este problema.

Objetos
Ya vimos cómo trabajar con rectángulos instanciando fabric.Rectconstructor. Pero, por supuesto, Fabric también cubre todas las demás formas básicas: círculos, triángulos, elipses, etc. Todos ellos están expuestos bajo el fabric“espacio de nombres”, como fabric.Circle, fabric.Triangle, fabric.Ellipse, etc.

Echemos un vistazo a un ejemplo sencillo que demuestra esta diferencia. Digamos que queremos dibujar un rectángulo rojo en algún lugar del lienzo. Así es como haríamos esto con la API nativa <canvas>.

// elemento de lienzo de referencia (con id = "c") 
var canvasEl = document.getElementById ('c');

// obtener contexto 2d para dibujar (el "mapa de bits" mencionado anteriormente)
var ctx = canvasEl.getContext ('2d');

// establecer el color de relleno del contexto
ctx.fillStyle = 'rojo';

// crea un rectángulo en un punto 100,100, con dimensiones de 20x20
ctx.fillRect (100, 100, 20, 20);
Ahora, echemos un vistazo a hacer lo mismo con Fabric:

// crea una envoltura alrededor del elemento de lienzo nativo (con id = "c")
var canvas = new fabric.Canvas ('c');

// crea un objeto rectangular
var rect = new fabric.Rect ({
  izquierda: 100,
  Top 100,
  relleno: 'rojo',
  ancho: 20,
  altura: 20
});

// "agregar" rectángulo al lienzo
lienzo.add (rect);

![image](https://user-images.githubusercontent.com/20000721/110523274-7ab5f080-80d7-11eb-9a32-f22cf2494614.png)

En este punto, casi no hay diferencia de tamaño; los dos ejemplos son bastante similares. Sin embargo, ya puede ver cuán diferente es el enfoque para trabajar con lienzo. Con los métodos nativos, operamos en el contexto : un objeto que representa el mapa de bits del lienzo completo. En Fabric, operamos con objetos : los instanciamos, cambiamos sus propiedades y los agregamos al lienzo. Puedes ver que estos objetos son ciudadanos de primera clase en la tierra de Fabric.

Echemos un vistazo a un ejemplo sencillo que demuestra esta diferencia. Digamos que queremos dibujar un rectángulo rojo en algún lugar del lienzo. Así es como haríamos esto con la API nativa <canvas>.

// elemento de lienzo de referencia (con id = "c")
var canvasEl = document.getElementById ('c');

// obtener contexto 2d para dibujar (el "mapa de bits" mencionado anteriormente)
var ctx = canvasEl.getContext ('2d');

// establecer el color de relleno del contexto
ctx.fillStyle = 'rojo';

// crea un rectángulo en un punto 100,100, con dimensiones de 20x20
ctx.fillRect (100, 100, 20, 20);

Ahora, echemos un vistazo a hacer lo mismo con Fabric: 

// crea una envoltura alrededor del elemento de lienzo nativo (con id = "c")
var canvas = new fabric.Canvas ('c');

// crea un objeto rectangular
var rect = new fabric.Rect ({
  izquierda: 100,
  Top 100,
  relleno: 'rojo',
  ancho: 20,
  altura: 20
});

// "agregar" rectángulo al lienzo
lienzo.add (rect);

![image](https://user-images.githubusercontent.com/20000721/110523702-134c7080-80d8-11eb-805c-70e479a9f8bb.png)

  
7 formas básicas proporcionadas en fabric:

fabric.Circle
fabric.Ellipse
fabric.Line
fabric.Polygon
fabric.Polyline
fabric.Rect
fabric.Triangle

¿Quieres dibujar un círculo? Simplemente cree un objeto circular y agréguelo al lienzo. Lo mismo con cualquier otra forma básica:

var circle = new fabric.Circle ({
  radio: 20, relleno: 'verde', izquierda: 100, arriba: 100
});
var triangle = new fabric.Triangle ({
  ancho: 20, alto: 30, relleno: 'azul', izquierda: 50, arriba: 50
});

lienzo.add (círculo, triángulo);

![image](https://user-images.githubusercontent.com/20000721/110524007-7a6a2500-80d8-11eb-9973-f999006695a5.png)


... y ahí tenemos un círculo verde, dibujado en la ubicación 100,100 y un triángulo azul en la ubicación 50,50.
