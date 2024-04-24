# **Índice**  

1. [Patrones de diseño](#diseño)
    1. [¿Qué es un patrón de diseño?](#diseño-1)
    2. [¿En qué consiste los patrones de diseño?](#diseño-2)
    3. [¿Por qué debería aprender sobre patrones?](#diseño-3)
    4. [Crítica de los patrones](#diseño-4)
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

**`Los patrones de diseño son soluciones habituales a problemas que ocurren con frecuencia en el diseño de software`**.  Son como planos prefabricados que se pueden personalizar para resolver un problema de diseño recurrente en tu código.

***No se puede elegir un patrón y copiarlo*** en el programa como si se tratara de funciones o bibliotecas ya preparadas. El patrón no es una porción específica de código, sino un concepto general para resolver un problema particular. Puedes seguir los detalles del patrón e implementar una solución que encaje con las realidades de tu propio programa.

A menudo los patrones se confunden con algoritmos porque ambos conceptos describen soluciones típicas a problemas conocidos. Mientras que un algoritmo siempre define un grupo claro de acciones para lograr un objetivo, un patrón es una descripción de más alto nivel de una solución. El código del mismo patrón aplicado a dos programas distintos puede ser diferente.


* ### ¿En qué consiste los patrones de diseño?<a name="diseño-2"></a>

La mayoría de los patrones se describe con mucha formalidad para que la gente pueda reproducirlos en muchos contextos. Aquí tienes las secciones que suelen estar presentes en la descripción de un patrón:

    * El propósito del patrón explica brevemente el problema y la solución.
    
    * La motivación explica en más detalle el problema y la solución que brinda el patrón.

    * La estructura de las clases muestra cada una de las partes del patrón y el modo
     en que se relacionan.

    * El ejemplo de código en uno de los lenguajes de programación populares facilita
     la asimilación de la idea que se esconde tras el patrón.

    * Algunos catálogos de patrones enumeran otros detalles útiles, como la aplicabilidad
     del patrón, los pasos de implementación y las relaciones con otros patrones.




* ### ¿Por qué debería aprender sobre patrones?<a name="diseño-3"></a>

***La realidad es que podrías trabajar durante años como programador sin conocer un solo patrón***. Mucha gente lo hace. Incluso en ese caso, podrías estar implementando patrones sin saberlo. Así que, ¿por qué dedicar tiempo a aprenderlos?

**`Los patrones de diseño son un juego de herramientas de soluciones comprobadas a problemas habituales en el diseño de software`**. Incluso aunque nunca te encuentres con estos problemas, conocer los patrones sigue siendo de utilidad, porque te enseña a resolver todo tipo de problemas utilizando principios del diseño orientado a objetos.

**`Los patrones de diseño definen un lenguaje común`** que puedes utilizar con tus compañeros de equipo para comunicaros de forma más eficiente.


* ### Crítica de los patrones<a name="diseño-4"></a>

Las principales críticas hacia los patrones de diseño suelen ser las siguientes: 

#### "Chapuzas para un lenguaje de programación débil"
Normalmente, la necesidad por los patrones surge cuando la gente elige un lenguaje de programación o una tecnología que carece del nivel necesario de abstracción. En este caso, los patrones se convierten en una chapuza que otorga al lenguaje unas súper habilidades muy necesitadas.


#### "Soluciones ineficientes"
Los patrones intentan sistematizar soluciones cuyo uso ya es generalizado. Esta unificación es vista por muchos como un dogma, e implementan los patrones “al pie de la letra”, sin adaptarlos al contexto del proyecto particular.

### "Uso injustificado"
 > Es tentador tratar todo como si fuera un clavo, si la única herramienta que tienes es un martillo — Abraham Maslow


Este es el problema que persigue a muchos principiantes que acaban de familiarizarse con los patrones. Una vez que aprenden sobre patrones, intentan aplicarlos en todas partes, incluso en situaciones en las que un código más simple funcionaría perfectamente bien.





---







# 2. Tipos de patrones<a name="tipos-patrones"></a>

Los patrones de diseño varían en su complejidad, nivel de detalle y escala de aplicabilidad al sistema completo que se diseña.

Los patrones más básicos y de más bajo nivel suelen llamarse `idioms`. Normalmente se aplican a un único lenguaje de programación.

Los patrones más universales y de más alto nivel son los `patrones de arquitectura`. Los desarrolladores pueden implementar estos patrones prácticamente en cualquier lenguaje. Al contrario que otros patrones, pueden utilizarse para diseñar la arquitectura de una aplicación completa.

Además, **todos los patrones pueden clasificarse por su propósito:**

* ***[Los patrones creacionales](#patrones-creacionales)***. Proporcionan mecanismos de creación de objetos que incrementan la flexibilidad y la reutilización de código existente.

* ***[Los patrones estructurales](#patrones-estructurales)***. Explican cómo ensamblar objetos y clases en estructuras más grandes a la vez que se mantiene la flexibilidad y eficiencia de la estructura.

* ***[Los patrones de comportamiento](#patrones-de-comportamiento)***. Se encargan de una comunicación efectiva y la asignación de responsabilidades entre objetos.

## Patrones creacionales<a name="creacionales"></a>

 Los patrones creacionales proporcionan varios mecanismos de creación de objetos que incrementan la flexibilidad y la reutilización del código existente.


### Factory Method<a name="factory-method"></a>

| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |

#### Propósito 

Proporcionar una interfaz para crear objetos en una superclase, pero permitiendo a las subclases alterar el tipo de objetos que se crearán. Esto promueve la abstracción y la flexibilidad al encapsular la creación de objetos en métodos específicos que pueden ser implementados de manera diferente por las subclases.


#### Problema

Imagina que estás creando una aplicación de gestión logística. La primera versión de tu aplicación sólo es capaz de manejar el transporte en camión, por lo que la mayor parte de tu código se encuentra dentro de la clase Camión.

Al cabo de un tiempo, tu aplicación se vuelve bastante popular. Cada día recibes decenas de peticiones de empresas de transporte marítimo para que incorpores la logística por mar a la aplicación.

Estupendo, ¿verdad? Pero, ¿qué pasa con el código? En este momento, la mayor parte de tu código está acoplado a la clase Camión. Para añadir barcos a la aplicación habría que hacer cambios en toda la base del código. Además, si más tarde decides añadir otro tipo de transporte a la aplicación, probablemente tendrás que volver a hacer todos estos cambios.

Al final acabarás con un código bastante sucio, plagado de condicionales que cambian el comportamiento de la aplicación dependiendo de la clase de los objetos de transporte


#### Pros y contras

| Pros                                    | Contras                                     |
|-----------------------------------------|---------------------------------------------|
| Flexibilidad                          | Complejidad adicional                     |
| Abstracción                           | Diseño adicional necesario                |
| Extensibilidad                        | Acoplamiento potencial                    |
| Reutilización del código              | Sobrecarga inicial                        |


#### Ejemplo
 

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

