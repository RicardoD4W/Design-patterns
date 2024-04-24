# **Índice**  

1. [Patrones de diseño](#diseño)
    1. [¿Qué es un patrón de diseño?](#diseño-1)
    2. [¿En qué consiste el patrón?](#diseño-2)
    3. [¿Por qué debería aprender sobre patrones?](#diseño-3)
    4. [Crítica de los patrones](#diseño-4)
    5. [Clasificación de los patrones](#diseño-5)
2. [Tipos de patrones](#tipos-patrones)
    1. [Patrones creacionales](#creacionales)
        1. [Factory Method](#factory-method)
        2. [Abstract Factory](#abstract-factory)
        3. [Builder](#builder)
        4. [Prototype](#prototype)
        5. [Singleton](#singleton)
    2. [Patrones estructurales](#estructurales)
        1. [Adapter](#adapter)
        2. [Bridge](#bridge)
        3. [Composite](#composite)
        4. [Decorator](#decorator)
        5. [Facade](#facade)
        6. [Flyweight](#flyweight)
        7. [Proxy](#proxy)
    3. [Patrones de comportamiento](#comportamiento)
        1.  [Chain of Responsibility](#chain-of-responsibility)
        2.  [Command](#command)
        3.  [Iterator](#iterator)
        4.  [Mediator](#mediator)
        5.  [Memento](#memento)
        6.  [Observer](#observer)
        7.  [State](#state)
        8.  [Strategy](#strategy)
        9.  [Template Method](#template-method)
        10. [Visitor](#visitor)
3. [Bibliografía](#biblio)


--- 

# 1. Patrones de diseño<a name="diseño"></a>

* ### ¿Qué es un patrón de diseño?<a name="diseño-1"></a>

**`Los patrones de diseño son soluciones habituales a problemas que ocurren con frecuencia en el diseño de software`**. Son como planos prefabricados que se pueden personalizar para resolver un problema de diseño recurrente en tu código.

***No se puede elegir un patrón y copiarlo*** en el programa como si se tratara de funciones o bibliotecas ya preparadas. El patrón no es una porción específica de código, sino un concepto general para resolver un problema particular. Puedes seguir los detalles del patrón e implementar una solución que encaje con las realidades de tu propio programa.

A menudo los patrones se confunden con algoritmos porque ambos conceptos describen soluciones típicas a problemas conocidos. Mientras que un algoritmo siempre define un grupo claro de acciones para lograr un objetivo, **`un patrón es una descripción de más alto nivel de una solución`**. El código del mismo patrón aplicado a dos programas distintos puede ser diferente.

Una analogía de un algoritmo sería una receta de cocina: ambos cuentan con pasos claros para alcanzar una meta. Por su parte, un patrón es más similar a un plano, ya que puedes observar cómo son su resultado y sus funciones, pero el orden exacto de la implementación depende de ti.



* ### ¿En qué consiste el patrón?<a name="diseño-2"></a>

La mayoría de los patrones se describe con mucha formalidad para que la gente pueda reproducirlos en muchos contextos. Aquí tienes las secciones que suelen estar presentes en la descripción de un patrón:

    * El propósito del patrón explica brevemente el problema y la solución.
    
    * La motivación explica en más detalle el problema y la solución que brinda el patrón.

    * La estructura de las clases muestra cada una de las partes del patrón y el modo en que se relacionan.

    * El ejemplo de código en uno de los lenguajes de programación populares facilita la asimilación de la idea que se esconde tras el patrón.

    * Algunos catálogos de patrones enumeran otros detalles útiles, como la aplicabilidad del patrón, los pasos de implementación y las relaciones con otros patrones.



* ### ¿Por qué debería aprender sobre patrones?<a name="diseño-3"></a>

***La realidad es que podrías trabajar durante años como programador sin conocer un solo patrón***. Mucha gente lo hace. Incluso en ese caso, podrías estar implementando patrones sin saberlo. Así que, ¿por qué dedicar tiempo a aprenderlos?

**`Los patrones de diseño son un juego de herramientas de soluciones comprobadas a problemas habituales en el diseño de software`**. Incluso aunque nunca te encuentres con estos problemas, conocer los patrones sigue siendo de utilidad, porque te enseña a resolver todo tipo de problemas utilizando principios del diseño orientado a objetos.

**`Los patrones de diseño definen un lenguaje común`** que puedes utilizar con tus compañeros de equipo para comunicaros de forma más eficiente. Podrías decir: “Oh, utiliza un singleton para eso”, y todos entenderían la idea de tu sugerencia. No habría necesidad de explicar qué es un singleton si conocen el patrón y su nombre.


* ### Crítica de los patrones<a name="diseño-4"></a>

Da la sensación de que todos los holgazanes han criticado ya los patrones de diseño. Veamos los argumentos más habituales contra el uso de los patrones.

#### Chapuzas para un lenguaje de programación débil 
Normalmente, la necesidad por los patrones surge cuando la gente elige un lenguaje de programación o una tecnología que carece del nivel necesario de abstracción. En este caso, los patrones se convierten en una chapuza que otorga al lenguaje unas súper habilidades muy necesitadas.


#### Soluciones ineficientes
Los patrones intentan sistematizar soluciones cuyo uso ya es generalizado. Esta unificación es vista por muchos como un dogma, e implementan los patrones “al pie de la letra”, sin adaptarlos al contexto del proyecto particular.

### Uso injustificado
 > Es tentador tratar todo como si fuera un clavo, si la única herramienta que tienes es un martillo — Abraham Maslow


Este es el problema que persigue a muchos principiantes que acaban de familiarizarse con los patrones. Una vez que aprenden sobre patrones, intentan aplicarlos en todas partes, incluso en situaciones en las que un código más simple funcionaría perfectamente bien.




* ### Clasificación de los patrones<a name="diseño-5"></a>

Los patrones de diseño varían en su complejidad, nivel de detalle y escala de aplicabilidad al sistema completo que se diseña. Me gusta la analogía de la construcción de carreteras: puedes hacer más segura una intersección instalando semáforos o construyendo un intercambiador completo de varios niveles con pasajes subterráneos para peatones.

Los patrones más básicos y de más bajo nivel suelen llamarse `idioms`. Normalmente se aplican a un único lenguaje de programación.

Los patrones más universales y de más alto nivel son los `patrones de arquitectura`. Los desarrolladores pueden implementar estos patrones prácticamente en cualquier lenguaje. Al contrario que otros patrones, pueden utilizarse para diseñar la arquitectura de una aplicación completa.

Además, **todos los patrones pueden clasificarse por su propósito:**

* ***Los patrones creacionales***. Proporcionan mecanismos de creación de objetos que incrementan la flexibilidad y la reutilización de código existente.

* ***Los patrones estructurales***. Explican cómo ensamblar objetos y clases en estructuras más grandes a la vez que se mantiene la flexibilidad y eficiencia de la estructura.

* ***Los patrones de comportamiento***. Se encargan de una comunicación efectiva y la asignación de responsabilidades entre objetos.

---







# 2. Tipos de patrones<a name="tipos-patrones"></a>


## Patrones creacionales<a name="creacionales"></a>

### Factory Method<a name="factory-method"></a>
### Abstract Factory<a name="abstract-factory"></a>
### Builder<a name="builder"></a>
### Prototype<a name="prototype"></a>
### Singleton<a name="singleton"></a>

---



## Patrones estructurales<a name="estructurales"></a>

### Adapter<a name="adapter"></a>
### Bridge<a name="bridge"></a>
### Composite<a name="composite"></a>
### Decorator<a name="decorator"></a>
### Facade<a name="facade"></a>
### Flyweight<a name="flyweight"></a>
### Proxy<a name="proxy"></a>


---

## Patrones de comportamiento<a name="comportamiento"></a>

### Chain of Responsibility<a name="chain-of-responsibility"></a>
### Command<a name="command"></a>
### Iterator<a name="iterator"></a>
### Mediator<a name="mediator"></a>
### Memento<a name="memento"></a>
### Observer<a name="observer"></a>
### State<a name="state"></a>
### Strategy<a name="strategy"></a>
### Template Method<a name="template-method"></a>
### Visitor<a name="visitor"></a>

---




---

# 3. Bibliografía<a name="biblio"></a>

* https://refactoring.guru/

---

