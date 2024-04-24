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

#### Pros y contras

| Pros                                    | Contras                                     |
|-----------------------------------------|---------------------------------------------|
| Flexibilidad                          | Complejidad adicional                     |
| Abstracción                           | Diseño adicional necesario                |
| Extensibilidad                        | Acoplamiento potencial                    |
| Reutilización del código              | Sobrecarga inicial                        |

#### Problema

Consideremos un sistema de manejo de envíos en una aplicación de comercio electrónico. El problema es que el sistema necesita manejar diferentes tipos de envíos, como envío terrestre, envío aéreo y envío marítimo, y cada uno de ellos tiene un proceso de creación diferente. Utilizaremos el patrón Factory Method para resolver este problema.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Definimos la clase base para los envíos
abstract class Shipment {
    abstract deliver(): string;
}

// Creamos las subclases específicas para cada tipo de envío
class LandShipment extends Shipment {
    deliver(): string {
        return 'Entrega por tierra';
    }
}

class AirShipment extends Shipment {
    deliver(): string {
        return 'Entrega por aire';
    }
}

class SeaShipment extends Shipment {
    deliver(): string {
        return 'Entrega por mar';
    }
}

// Creamos la clase Creator que tendrá el Factory Method
abstract class ShipmentCreator {
    abstract createShipment(): Shipment;

    // Otros métodos comunes pueden ir aquí
}

// Implementamos el Factory Method en las subclases concretas del Creator
class LandShipmentCreator extends ShipmentCreator {
    createShipment(): Shipment {
        return new LandShipment();
    }
}

class AirShipmentCreator extends ShipmentCreator {
    createShipment(): Shipment {
        return new AirShipment();
    }
}

class SeaShipmentCreator extends ShipmentCreator {
    createShipment(): Shipment {
        return new SeaShipment();
    }
}

// Cliente
function handleShipment(shipmentCreator: ShipmentCreator) {
    const shipment = shipmentCreator.createShipment();
    console.log(shipment.deliver());
}

// Uso del Factory Method
handleShipment(new LandShipmentCreator()); // Output: Entrega por tierra
handleShipment(new AirShipmentCreator());  // Output: Entrega por aire
handleShipment(new SeaShipmentCreator());  // Output: Entrega por mar
```






### Abstract Factory<a name="abstract-factory"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |

#### Propósito 

Proporcionar una interfaz para crear familias de objetos relacionados o dependientes sin especificar sus clases concretas. Esto permite que un cliente trabaje con las familias de objetos a través de interfaces abstractas, lo que facilita la creación de productos relacionados pero independientes de la implementación.

#### Pros y contras

| Pros                                    | Contras                                     |
|-----------------------------------------|---------------------------------------------|
| Flexibilidad                          | Complejidad adicional                     |
| Abstracción                           | Diseño adicional necesario                |
| Extensibilidad                        | Acoplamiento potencial                    |
| Reutilización del código              | Sobrecarga inicial                        |

#### Problema

Consideremos un sistema de generación de contenido multimedia, donde necesitamos crear tanto imágenes como vídeos. Además, queremos tener diferentes estilos para cada tipo de contenido, como un estilo moderno y un estilo clásico. Utilizaremos el patrón Abstract Factory para manejar esta variabilidad y crear tanto imágenes como vídeos en los estilos especificados.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Definimos las interfaces para los productos
interface Image {
    display(): void;
}

interface Video {
    play(): void;
}

// Creamos las implementaciones concretas de los productos
class ModernImage implements Image {
    display(): void {
        console.log('Mostrando imagen en estilo moderno');
    }
}

class ClassicImage implements Image {
    display(): void {
        console.log('Mostrando imagen en estilo clásico');
    }
}

class ModernVideo implements Video {
    play(): void {
        console.log('Reproduciendo video en estilo moderno');
    }
}

class ClassicVideo implements Video {
    play(): void {
        console.log('Reproduciendo video en estilo clásico');
    }
}

// Definimos la interfaz Abstract Factory
interface MediaFactory {
    createImage(): Image;
    createVideo(): Video;
}

// Implementamos las fábricas concretas
class ModernMediaFactory implements MediaFactory {
    createImage(): Image {
        return new ModernImage();
    }

    createVideo(): Video {
        return new ModernVideo();
    }
}

class ClassicMediaFactory implements MediaFactory {
    createImage(): Image {
        return new ClassicImage();
    }

    createVideo(): Video {
        return new ClassicVideo();
    }
}

// Cliente
function createMedia(mediaFactory: MediaFactory) {
    const image = mediaFactory.createImage();
    const video = mediaFactory.createVideo();

    image.display();
    video.play();
}

// Uso del Abstract Factory
console.log('Creando contenido multimedia en estilo moderno:');
createMedia(new ModernMediaFactory());

console.log('\nCreando contenido multimedia en estilo clásico:');
createMedia(new ClassicMediaFactory());

```




### Builder<a name="builder"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |

#### Propósito 

Separar la construcción de un objeto complejo de su representación, de modo que el mismo proceso de construcción pueda crear diferentes representaciones. Esto permite construir objetos complejos paso a paso, de manera flexible, y ocultar la complejidad de su construcción al cliente.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Separación de preocupaciones                        | Complejidad adicional                               |
| Flexibilidad                                        | Overhead adicional                                  |
| Oculta la complejidad                               | Aumento del acoplamiento entre clases               |


#### Problema

Consideremos un sistema de construcción de casas, donde cada casa puede tener diferentes tipos de habitaciones, materiales de construcción y estilos arquitectónicos. Utilizaremos el patrón Builder para construir diferentes tipos de casas de manera flexible y ocultar la complejidad de su construcción al cliente.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Definimos la clase Casa que será construida
class Casa {
    private habitaciones: string[] = [];
    private material: string = '';
    private estilo: string = '';

    constructor(material: string, estilo: string) {
        this.material = material;
        this.estilo = estilo;
    }

    agregarHabitacion(habitacion: string): void {
        this.habitaciones.push(habitacion);
    }

    mostrar(): void {
        console.log(`Casa construida con material ${this.material}, estilo ${this.estilo} y las siguientes habitaciones:`);
        this.habitaciones.forEach((habitacion, index) => {
            console.log(`- Habitación ${index + 1}: ${habitacion}`);
        });
    }
}

// Definimos la interfaz Builder para la construcción de la casa
interface CasaBuilder {
    construirHabitaciones(): void;
    construirMaterial(): void;
    construirEstilo(): void;
    obtenerCasa(): Casa;
}

// Implementamos el Builder para construir una casa moderna
class CasaModernaBuilder implements CasaBuilder {
    private casa: Casa;

    constructor() {
        this.casa = new Casa('Cemento', 'Moderno');
    }

    construirHabitaciones(): void {
        this.casa.agregarHabitacion('Sala de estar');
        this.casa.agregarHabitacion('Dormitorio principal');
        this.casa.agregarHabitacion('Cocina');
        this.casa.agregarHabitacion('Baño');
    }

    construirMaterial(): void {
        // En este caso, el material ya está definido al crear la casa moderna
    }

    construirEstilo(): void {
        // En este caso, el estilo ya está definido al crear la casa moderna
    }

    obtenerCasa(): Casa {
        return this.casa;
    }
}

// Director que construye una casa según las especificaciones del Builder
class ConstructorDeCasas {
    private casaBuilder: CasaBuilder;

    constructor(casaBuilder: CasaBuilder) {
        this.casaBuilder = casaBuilder;
    }

    construirCasa(): void {
        this.casaBuilder.construirHabitaciones();
        this.casaBuilder.construirMaterial();
        this.casaBuilder.construirEstilo();
    }

    obtenerCasa(): Casa {
        return this.casaBuilder.obtenerCasa();
    }
}

// Cliente
const builderModerno = new CasaModernaBuilder();
const constructor = new ConstructorDeCasas(builderModerno);

constructor.construirCasa();
const casaModerna = constructor.obtenerCasa();
casaModerna.mostrar(); // Casa construida con material cemento, estilo moderno y las siguientes habitaciones:
                       // - Habitación 1: Sala de estar - Habitación 2: Dormitorio principal - Habitación 3: Cocina - Habitación 4: Baño

```








### Prototype<a name="prototype"></a>

| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Permitir la creación de nuevos objetos duplicando una instancia existente, conocida como prototipo, en lugar de crear una instancia desde cero. Esto permite la creación de nuevos objetos con la misma estructura y propiedades que un objeto existente, reduciendo la complejidad y el acoplamiento en el proceso de creación de objetos.


#### Pros y contras

| Pros                                                       | Contras                                                         |
|------------------------------------------------------------|-----------------------------------------------------------------|
| Facilita la creación de nuevos objetos                     | Puede ser complicado si el objeto tiene una estructura compleja |
| Reduce el acoplamiento en el proceso de creación           | Duplicación de código                                           |
| Permite la personalización de objetos existentes           |                                                                 |


#### Problema

Consideremos un sistema de gestión de empleados, necesitamos crear diferentes tipos de empleados, como desarrolladores, diseñadores y gerentes. Cada empleado tiene atributos comunes como nombre, edad y salario. Utilizaremos el patrón Prototype para crear nuevos empleados a partir de un prototipo existente.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Definimos la clase Empleado como prototipo
class Empleado {
    constructor(public nombre: string, public edad: number, public salario: number) {}

    // Método para clonar el prototipo
    clonar(): Empleado {
        return new Empleado(this.nombre, this.edad, this.salario);
    }

    // Método para mostrar los detalles del empleado
    detalles(): string {
        return `Nombre: ${this.nombre}, Edad: ${this.edad}, Salario: ${this.salario}`;
    }
}

// Crear un empleado prototipo
const prototipoEmpleado = new Empleado('John Doe', 30, 50000);

// Crear nuevos empleados a partir del prototipo
const empleado1 = prototipoEmpleado.clonar();
const empleado2 = prototipoEmpleado.clonar();

// Modificar los detalles de los nuevos empleados si es necesario, por simplicidad del ejemplo omitimos la encapsulación
// OJO esta es muy importante al trabajar con POO
empleado1.nombre = 'Alice';
empleado2.nombre = 'Bob';

// Mostrar detalles de los empleados
console.log('Empleado 1:', empleado1.detalles()); // Empleado 1: Nombre: Alice, Age: 30, Salary: 50000
console.log('Empleado 2:', empleado2.detalles()); // Empleado 2: Nombre: Bob, Age: 30, Salary: 50000

```








### Singleton<a name="singleton"></a>

| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Garantizar que una clase tenga una única instancia y proporcionar un punto de acceso global a esa instancia. Esto se utiliza cuando queremos asegurarnos de que una clase tenga exactamente una instancia y que esta instancia sea accesible desde cualquier parte del programa.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Garantiza una única instancia de la clase           | Violación del principio de responsabilidad única ([```S```OLID](https://github.com/RicardoD4w/Buenas-Practicas-Clean-Code-Version?tab=readme-ov-file#srp))    |
| Proporciona un punto de acceso global               | Dificulta la prueba unitaria                        |
| Evita la creación de múltiples instancias           |                                                     |



#### Problema

Consideremos un sistema de registro de usuarios, necesitamos una clase que maneje la conexión a la base de datos y garantice que solo haya una instancia de esta clase en todo el programa.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Definimos la clase Singleton para manejar la conexión a la base de datos
class DBConnection {
    private static instance: DBConnection;
    private constructor() {} // Constructor privado para evitar la creación de instancias fuera de la clase

    static getInstance(): DBConnection {
        // Si no hay una instancia existente, creamos una nueva
        if (!DBConnection.instance) {
            DBConnection.instance = new DBConnection();
        }
        return DBConnection.instance;
    }

    // Método para simular la conexión a la base de datos
    connect(): void {
        console.log('Conexión a la base de datos establecida.');
    }
}

// Cliente
const dbConnection1 = DBConnection.getInstance();
const dbConnection2 = DBConnection.getInstance();

// Verificar si dbConnection1 y dbConnection2 son la misma instancia
console.log(dbConnection1 === dbConnection2); // Output: true

// Conectar a la base de datos a través de dbConnection1
dbConnection1.connect(); // Output: Conexión a la base de datos establecida.

```



---




## Patrones estructurales<a name="estructurales"></a>

Los patrones estructurales explican cómo ensamblar objetos y clases en estructuras más grandes, a la vez que se mantiene la flexibilidad y eficiencia de estas estructuras.

### Adapter<a name="adapter"></a>

| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |


#### Propósito 

Permitir que objetos con interfaces incompatibles puedan colaborar entre sí. Esto se logra creando un adaptador que actúa como un intermediario entre dos interfaces diferentes, permitiendo que interactúen sin necesidad de modificar su código fuente.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Permite la colaboración entre objetos con interfaces incompatibles | Puede introducir complejidad adicional en el código |
| Reutilización de código existente                   | Puede afectar el rendimiento                         |
| Facilita la integración de sistemas existentes      |                                                     |



#### Problema

Consideremos que tenemos una aplicación que utiliza un servicio de mapas externo para mostrar ubicaciones. Sin embargo, el servicio de mapas tiene una interfaz incompatible con nuestra aplicación. Utilizaremos el patrón Adapter para adaptar la interfaz del servicio de mapas externo a la interfaz que espera nuestra aplicación.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Interfaz del servicio de mapas externo
interface ServicioMapasExterno {
    mostrarMapa(ubicacion: string): void;
}

// Implementación del servicio de mapas externo
class ServicioMapasTerceros implements ServicioMapasExterno {
    mostrarMapa(ubicacion: string): void {
        console.log(`Mostrando mapa en ${ubicacion} a través del servicio de mapas externo.`);
    }
}

// Interfaz esperada por nuestra aplicación
interface ServicioMapas {
    verMapa(ubicacion: string): void;
}

// Adaptador que convierte la interfaz del servicio de mapas externo a la interfaz de nuestra aplicación
class AdaptadorServicioMapas implements ServicioMapas {
    private servicioMapasExterno: ServicioMapasExterno;

    constructor(servicioMapasExterno: ServicioMapasExterno) {
        this.servicioMapasExterno = servicioMapasExterno;
    }

    verMapa(ubicacion: string): void {
        // Llamar al método del servicio de mapas externo a través del adaptador
        this.servicioMapasExterno.mostrarMapa(ubicacion);
    }
}

// Cliente
const servicioMapasTerceros = new ServicioMapasTerceros();
const adaptadorServicioMapas = new AdaptadorServicioMapas(servicioMapasTerceros);

// Utilizar el servicio de mapas a través del adaptador
adaptadorServicioMapas.verMapa('Nueva York');

```





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

