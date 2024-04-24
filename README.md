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


| **Complejidad** | **★★★** |
| ----- | ----  |
| **Popularidad** | **★✰✰** |


#### Propósito 

Separar una abstracción de su implementación, de modo que ambas puedan variar de forma independiente. Esto permite que las clases abstracción e implementación puedan cambiar sin afectar a la otra, proporcionando así flexibilidad en el diseño y facilitando la expansión y mantenimiento del código.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla la abstracción de la implementación       | Aumenta la complejidad del código                   |
| Facilita la expansión y mantenimiento del código    | Puede requerir una estructura adicional de clases   |
| Permite la variación independiente de abstracción e implementación | Puede ser excesivo para problemas simples           |



#### Problema

Consideremos que tenemos un sistema de entretenimiento que puede reproducir contenido multimedia, como películas y música, en diferentes dispositivos, como televisores y altavoces. Queremos que el sistema pueda trabajar con diferentes tipos de contenido y dispositivos de salida de forma independiente. Utilizaremos el patrón Bridge para separar la abstracción del contenido multimedia de su implementación en dispositivos de salida.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Abstracción: Reproductor multimedia
interface ReproductorMultimedia {
    reproducir(): void;
}

// Implementación: Dispositivo de salida
interface DispositivoSalida {
    reproducirContenido(): void;
}

// Implementación concreta: Dispositivo de salida - Televisor
class Televisor implements DispositivoSalida {
    reproducirContenido(): void {
        console.log('Reproduciendo contenido en el televisor...');
    }
}

// Implementación concreta: Dispositivo de salida - Altavoz
class Altavoz implements DispositivoSalida {
    reproducirContenido(): void {
        console.log('Reproduciendo contenido en el altavoz...');
    }
}

// Abstracción refinada: Reproductor multimedia - Película
class ReproductorPelicula implements ReproductorMultimedia {
    constructor(private dispositivoSalida: DispositivoSalida) {}

    reproducir(): void {
        console.log('Reproduciendo película...');
        this.dispositivoSalida.reproducirContenido();
    }
}

// Abstracción refinada: Reproductor multimedia - Música
class ReproductorMusica implements ReproductorMultimedia {
    constructor(private dispositivoSalida: DispositivoSalida) {}

    reproducir(): void {
        console.log('Reproduciendo música...');
        this.dispositivoSalida.reproducirContenido();
    }
}

// Cliente
const televisor = new Televisor();
const altavoz = new Altavoz();

const reproductorPelicula = new ReproductorPelicula(televisor);
const reproductorMusica = new ReproductorMusica(altavoz);

// Utilizar los reproductores multimedia
reproductorPelicula.reproducir(); // Reproducir película en televisor
reproductorMusica.reproducir(); // Reproducir música en altavoz

```





### Composite<a name="composite"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Componer objetos en estructuras de árbol para representar jerarquías parte-todo. Esto permite tratar tanto a los objetos individuales como a las composiciones de objetos de manera uniforme, lo que simplifica el diseño y la manipulación de las estructuras.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Permite manejar estructuras de árbol de manera uniforme | Puede complicar el diseño y la implementación      |
| Facilita la manipulación y navegación en estructuras complejas | Puede resultar menos eficiente en ciertos casos    |
| Proporciona flexibilidad en la construcción de objetos compuestos |                                                     |



#### Problema

Consideremos que necesitamos representar una jerarquía de elementos de menú, donde cada elemento puede ser un elemento de menú simple o un menú compuesto que contiene subelementos. Queremos poder mostrar el menú completo y realizar operaciones como agregar o eliminar elementos.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Componente: Elemento de menú
interface ElementoMenu {
    mostrar(): void;
}

// Hoja: Elemento de menú simple
class ElementoMenuSimple implements ElementoMenu {
    constructor(private nombre: string) {}

    mostrar(): void {
        console.log(`- ${this.nombre}`);
    }
}

// Compuesto: Menú
class Menu implements ElementoMenu {
    private elementos: ElementoMenu[] = [];

    agregarElemento(elemento: ElementoMenu): void {
        this.elementos.push(elemento);
    }

    eliminarElemento(elemento: ElementoMenu): void {
        const indice = this.elementos.indexOf(elemento);
        if (indice !== -1) {
            this.elementos.splice(indice, 1);
        }
    }

    mostrar(): void {
        console.log('Menú:');
        this.elementos.forEach(elemento => elemento.mostrar());
    }
}

// Cliente
const menuPrincipal = new Menu();
const menuDesayuno = new Menu();

const elementoPizza = new ElementoMenuSimple('Pizza');
const elementoEnsalada = new ElementoMenuSimple('Ensalada');
const elementoCafe = new ElementoMenuSimple('Café');
const elementoJugo = new ElementoMenuSimple('Jugo');

menuPrincipal.agregarElemento(elementoPizza);
menuPrincipal.agregarElemento(elementoEnsalada);
menuDesayuno.agregarElemento(elementoCafe);
menuDesayuno.agregarElemento(elementoJugo);

menuPrincipal.mostrar();                
console.log('---');
menuDesayuno.mostrar();

/*
Menú:
- Pizza
- Ensalada
---
Menú:
- Café
- Jugo

*/

```




### Decorator<a name="decorator"></a>


| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Agregar funcionalidades adicionales a objetos existentes de manera dinámica y flexible, sin modificar su estructura. Esto permite extender las capacidades de los objetos de forma modular y sin necesidad de modificar su código original.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Añade funcionalidades de forma flexible y dinámica | Puede generar una gran cantidad de clases decoradoras |
| Permite extender las capacidades de los objetos de forma modular | Puede aumentar la complejidad del código             |
| Facilita la combinación de funcionalidades         |                                                     |



#### Problema

Consideremos que tenemos una aplicación de edición de texto que permite aplicar diferentes formatos a un texto, como negrita, cursiva y subrayado. Queremos que los usuarios puedan aplicar múltiples formatos al texto de forma flexible.



#### Ejemplo

```ts
index.ts
-----------------------------------------
// Componente: Interfaz Texto
interface Texto {
    contenido(): string;
}

// Componente concreto: Implementación del texto
class TextoSimple implements Texto {
    constructor(private contenidoTexto: string) {}

    contenido(): string {
        return this.contenidoTexto;
    }
}

// Decorador abstracto: Decorador de texto
abstract class DecoradorTexto implements Texto {
    constructor(protected texto: Texto) {}

    abstract contenido(): string;
}

// Decorador concreto: Negrita
class Negrita extends DecoradorTexto {
    contenido(): string {
        return `<b>${this.texto.contenido()}</b>`;
    }
}

// Decorador concreto: Cursiva
class Cursiva extends DecoradorTexto {
    contenido(): string {
        return `<i>${this.texto.contenido()}</i>`;
    }
}

// Decorador concreto: Subrayado
class Subrayado extends DecoradorTexto {
    contenido(): string {
        return `<u>${this.texto.contenido()}</u>`;
    }
}

// Cliente
let texto: Texto = new TextoSimple("Hola, mundo!");

// Aplicar decoradores
texto = new Negrita(texto);
texto = new Cursiva(texto);
texto = new Subrayado(texto);

// Mostrar el texto con los decoradores aplicados
console.log(texto.contenido()); // Output: <u><i><b>Hola, mundo!</b></i></u>

```




### Facade<a name="facade"></a>


| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Proporcionar una interfaz unificada y simplificada para un conjunto complejo de subsistemas. Esto permite ocultar la complejidad y la interacción entre los subsistemas, proporcionando a los clientes una interfaz fácil de usar para acceder a la funcionalidad del sistema.


#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Oculta la complejidad del sistema                   | Puede limitar la flexibilidad                        |
| Proporciona una interfaz simple y unificada         | Puede introducir un acoplamiento adicional entre el cliente y los subsistemas |
| Simplifica el mantenimiento y la modificación del sistema |                                                     |



#### Problema

Consideremos que tenemos un sistema de compras en línea que consta de varios subsistemas, como el catálogo de productos, el carrito de compras y el proceso de pago. Queremos simplificar el proceso de compra para los clientes proporcionando una interfaz unificada que maneje la interacción con todos estos subsistemas.



#### Ejemplo

```ts
index.ts
-----------------------------------------
// Subsistema: Catálogo de productos
class CatalogoProductos {
    buscarProducto(nombre: string): string {
        // Simulación de búsqueda de producto
        return `Producto encontrado: ${nombre}`;
    }
}

// Subsistema: Carrito de compras
class CarritoCompras {
    agregarProducto(nombre: string): void {
        // Simulación de agregar producto al carrito
        console.log(`Producto agregado al carrito: ${nombre}`);
    }
}

// Subsistema: Proceso de pago
class ProcesoPago {
    realizarPago(precio: number): void {
        // Simulación de proceso de pago
        console.log(`Pago realizado por un precio de ${precio} USD`);
    }
}

// Facade: Interfaz unificada para el sistema de compras en línea
class ComprasEnLinea {
    constructor(
        private catalogo: CatalogoProductos,
        private carrito: CarritoCompras,
        private pago: ProcesoPago
    ) {}

    comprarProducto(nombre: string, precio: number): void {
        console.log(this.catalogo.buscarProducto(nombre));
        this.carrito.agregarProducto(nombre);
        this.pago.realizarPago(precio);
    }
}

// Cliente
const catalogo = new CatalogoProductos();
const carrito = new CarritoCompras();
const procesoPago = new ProcesoPago();

const compras = new ComprasEnLinea(catalogo, carrito, procesoPago);

// Realizar una compra utilizando la interfaz unificada
compras.comprarProducto('Camisa', 25.99);

```






### Flyweight<a name="flyweight"></a>


| **Complejidad** | **★★★** |
| ----- | ----  |
| **Popularidad** | **✰✰✰** |


#### Propósito 

Minimizar el uso de memoria o recursos compartiendo lo máximo posible entre múltiples objetos. Esto se logra mediante el uso compartido de objetos que son idénticos o similares, reduciendo así la cantidad de objetos creados y optimizando el rendimiento del sistema.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Reduce el uso de memoria y optimiza el rendimiento  | Puede aumentar la complejidad del código             |
| Mejora la eficiencia en sistemas con muchos objetos similares | No es adecuado para todos los tipos de objetos      |
| Facilita la gestión de objetos en memoria          |                                                     |



#### Problema

Consideremos que tenemos una aplicación que muestra una gran cantidad de íconos en una interfaz gráfica de usuario. Cada ícono tiene propiedades únicas como tamaño, color y tipo. Queremos optimizar el rendimiento de la aplicación minimizando la cantidad de objetos ícono creados en memoria.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Flyweight: Interfaz del ícono
interface Icono {
    dibujar(): void;
}

// Flyweight concreto: Implementación del ícono compartido
class IconoCompartido implements Icono {
    constructor(private tipo: string) {}

    dibujar(): void {
        console.log(`Dibujando el ícono ${this.tipo}`);
    }
}

// Fábrica de íconos: Gestiona la creación y almacenamiento de íconos compartidos
class FabricaIconos {
    private iconos: { [tipo: string]: Icono } = {};

    obtenerIcono(tipo: string): Icono {
        if (!this.iconos[tipo]) {
            this.iconos[tipo] = new IconoCompartido(tipo);
        }
        return this.iconos[tipo];
    }
}

// Cliente
const fabricaIconos = new FabricaIconos();

// Mostrar íconos en la GUI
const tiposIconos = ['Archivo', 'Carpeta', 'Documento', 'Imagen'];
const posiciones = [[10, 20], [30, 40], [50, 60], [70, 80]];

for (let i = 0; i < tiposIconos.length; i++) {
    const tipo = tiposIconos[i];
    const posicion = posiciones[i];

    const icono = fabricaIconos.obtenerIcono(tipo);
    icono.dibujar();
    console.log(`Ícono ${tipo} en la posición (${posicion[0]}, ${posicion[1]})`);
}

```

### Proxy<a name="proxy"></a>


| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★✰✰** |


#### Propósito 

Proporcionar un representante o sustituto de otro objeto para controlar el acceso a este objeto. Esto permite agregar funcionalidades adicionales, como la verificación de permisos, la carga perezosa o el caché, sin modificar el objeto original.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Controla el acceso al objeto original               | Aumenta la complejidad del código                   |
| Permite agregar funcionalidades adicionales         | Puede introducir un nivel adicional de indirección  |
| Facilita la implementación de técnicas como la carga perezosa o el caché |                                                 |



#### Problema

Consideremos que tenemos una aplicación que carga imágenes desde un servidor remoto. Queremos implementar una funcionalidad de caché para almacenar las imágenes cargadas recientemente y evitar la carga repetida de la misma imagen.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Sujeto: Interfaz para cargar imágenes
interface CargadorImagen {
    cargarImagen(nombre: string): void;
}

// Sujeto real: Implementación concreta del cargador de imágenes
class CargadorImagenReal implements CargadorImagen {
    cargarImagen(nombre: string): void {
        console.log(`Cargando imagen '${nombre}' desde el servidor remoto...`);
    }
}

// Proxy: Implementación del proxy para controlar el acceso al cargador de imágenes real
class ProxyCargadorImagen implements CargadorImagen {
    private cargadorReal: CargadorImagenReal;
    private cache: string[] = [];

    constructor() {
        this.cargadorReal = new CargadorImagenReal();
    }

    cargarImagen(nombre: string): void {
        if (this.cache.includes(nombre)) {
            console.log(`Obteniendo imagen '${nombre}' desde el caché...`);
        } else {
            this.cargadorReal.cargarImagen(nombre);
            this.cache.push(nombre);
        }
    }
}

// Cliente
const proxyCargador = new ProxyCargadorImagen();

// Cargar imágenes utilizando el proxy
proxyCargador.cargarImagen('imagen1.jpg'); // Se carga desde el servidor remoto
proxyCargador.cargarImagen('imagen2.jpg'); // Se carga desde el servidor remoto
proxyCargador.cargarImagen('imagen1.jpg'); // Se obtiene desde el caché

```

---

## Patrones de comportamiento<a name="comportamiento"></a>

Los patrones de comportamiento tratan con algoritmos y la asignación de responsabilidades entre objetos.





### Chain of Responsibility<a name="chain-of-responsibility"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★✰✰** |


#### Propósito 

Permitir que varios objetos manejen una solicitud de manera secuencial, pasándola a lo largo de una cadena hasta que un objeto pueda manejarla. Esto evita acoplar el remitente de una solicitud con su receptor, permitiendo que múltiples objetos tengan la oportunidad de manejar la solicitud.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla el remitente de la solicitud de sus receptores | Puede ser difícil determinar el flujo de la cadena  |
| Permite la flexibilidad en la asignación de responsabilidades | Puede haber un riesgo de que la solicitud no sea manejada |
| Facilita la extensibilidad y la reutilización del código |                                                     |



#### Problema

Consideremos que tenemos un sistema de aprobación de solicitudes de compra, donde cada solicitud debe ser aprobada por un conjunto específico de autoridades en un orden específico. Queremos implementar un sistema que maneje la aprobación de solicitudes de manera secuencial, pasando la solicitud de aprobación a través de una cadena de autoridades hasta que sea aprobada.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Handler: Interfaz para manejar la solicitud
interface ManejadorSolicitud {
    establecerSiguiente(manejador: ManejadorSolicitud): void;
    manejarSolicitud(precio: number): void;
}

// Handler concreto: Autoridad de aprobación
class AutoridadAprobacion implements ManejadorSolicitud {
    private siguiente: ManejadorSolicitud;

    establecerSiguiente(manejador: ManejadorSolicitud): void {
        this.siguiente = manejador;
    }

    manejarSolicitud(precio: number): void {
        console.log("Autoridad de aprobación aprobando la solicitud...");
    }
}

// Cliente
const autoridad1 = new AutoridadAprobacion();
const autoridad2 = new AutoridadAprobacion();
const autoridad3 = new AutoridadAprobacion();

autoridad1.establecerSiguiente(autoridad2);
autoridad2.establecerSiguiente(autoridad3);

// Manejar la solicitud
autoridad1.manejarSolicitud(500); // La solicitud pasa por la cadena de autoridades hasta ser aprobada

```




### Command<a name="command"></a>


| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |


#### Propósito 

Encapsular una solicitud como un objeto, permitiendo parametrizar clientes con operaciones y permitiendo la operación de solicitudes de forma asíncrona, en cola o con registro. Esto desacopla el objeto que invoca la operación de los objetos que conocen los detalles de la operación.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla el remitente de la solicitud de su receptor | Puede aumentar la complejidad del código             |
| Permite la parametrización de objetos con operaciones | Puede requerir la creación de múltiples clases para cada comando |
| Facilita la implementación de operaciones reversibles o encolables |                                                     |


#### Problema

Consideremos que tenemos un editor de texto que permite al usuario realizar operaciones como copiar, cortar y pegar texto. Queremos implementar estas operaciones como comandos para que puedan ser ejecutadas de forma asíncrona o en cola.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Comando: Interfaz para los comandos
interface Comando {
    ejecutar(): void;
}

// Comandos concretos: Implementaciones de los comandos
class ComandoCopiar implements Comando {
    constructor(private texto: string) {}

    ejecutar(): void {
        console.log(`Texto copiado: ${this.texto}`);
    }
}

class ComandoCortar implements Comando {
    constructor(private texto: string) {}

    ejecutar(): void {
        console.log(`Texto cortado: ${this.texto}`);
    }
}

class ComandoPegar implements Comando {
    constructor(private texto: string) {}

    ejecutar(): void {
        console.log(`Texto pegado: ${this.texto}`);
    }
}

// Invocador: Clase que invoca los comandos
class EditorTexto {
    ejecutarComando(comando: Comando): void {
        comando.ejecutar();
    }
}

// Cliente
const editor = new EditorTexto();

// Ejecutar comandos
const comandoCopiar = new ComandoCopiar("Texto seleccionado");
const comandoCortar = new ComandoCortar("Texto seleccionado");
const comandoPegar = new ComandoPegar("Texto copiado");

editor.ejecutarComando(comandoCopiar);
editor.ejecutarComando(comandoCortar);
editor.ejecutarComando(comandoPegar);

```






### Iterator<a name="iterator"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |


#### Propósito 

Proporcionar una forma de acceder a los elementos de una colección secuencialmente sin exponer su representación subyacente. Esto permite recorrer una colección de objetos sin conocer los detalles de su implementación interna.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla el código cliente de la estructura de la colección | Puede aumentar la complejidad del código cliente    |
| Permite recorrer una colección de objetos sin conocer su implementación interna | Puede requerir la implementación de un iterador personalizado para cada tipo de colección |
| Facilita la implementación de algoritmos de recorrido y procesamiento de colecciones |                                                     |


#### Problema

Consideremos que tenemos una lista de tareas pendientes y queremos implementar un iterador para recorrerlas y mostrarlas en la consola.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Iterador: Interfaz para el iterador
interface Iterador<T> {
    siguiente(): T;
    tieneSiguiente(): boolean;
}

// Agregado: Interfaz para el agregado
interface Agregado<T> {
    crearIterador(): Iterador<T>;
}

// Colección concreta: Implementación de la lista de tareas pendientes
class ListaTareas implements Agregado<string> {
    private tareas: string[] = [];

    agregarTarea(tarea: string): void {
        this.tareas.push(tarea);
    }

    obtenerTarea(index: number): string {
        return this.tareas[index];
    }

    obtenerCantidadTareas(): number {
        return this.tareas.length;
    }

    crearIterador(): Iterador<string> {
        return new IteradorListaTareas(this);
    }
}

// Iterador concreto: Implementación del iterador para la lista de tareas
class IteradorListaTareas implements Iterador<string> {
    private index: number = 0;

    constructor(private listaTareas: ListaTareas) {}

    siguiente(): string {
        const tarea = this.listaTareas.obtenerTarea(this.index);
        this.index++;
        return tarea;
    }

    tieneSiguiente(): boolean {
        return this.index < this.listaTareas.obtenerCantidadTareas();
    }
}

// Cliente
const listaTareas = new ListaTareas();
listaTareas.agregarTarea("Hacer la compra");
listaTareas.agregarTarea("Lavar el coche");
listaTareas.agregarTarea("Estudiar para el examen");

const iterador = listaTareas.crearIterador();

// Recorrer la lista de tareas y mostrarlas en la consola
while (iterador.tieneSiguiente()) {
    console.log(iterador.siguiente());
}

```



### Mediator<a name="mediator"></a>

| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **✰✰✰** |


#### Propósito 

Definir un objeto que encapsula cómo un conjunto de objetos interactúan entre sí, promoviendo un acoplamiento débil al evitar que los objetos se refieran directamente entre sí. El mediador actúa como intermediario entre los objetos y facilita la comunicación y la coordinación entre ellos.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla los componentes del sistema               | Puede introducir un punto único de fallo            |
| Facilita la reutilización de los componentes        | Puede aumentar la complejidad del mediador          |
| Promueve un diseño más flexible y mantenible        | Puede ser difícil de implementar en sistemas grandes |                                                 |


#### Problema

Consideremos que tenemos un sistema de chat donde múltiples usuarios pueden enviar mensajes entre sí. Queremos implementar un mediador para facilitar la comunicación entre los usuarios.

#### Ejemplo

```ts
index.ts
-----------------------------------------
// Mediador: Interfaz para el mediador
interface Mediador {
    enviarMensaje(mensaje: string, remitente: Usuario): void;
}

// Usuario: Clase para representar a un usuario
class Usuario {
    constructor(private nombre: string, private mediador: Mediador) {}

    enviarMensaje(mensaje: string): void {
        console.log(`${this.nombre} envía mensaje: ${mensaje}`);
        this.mediador.enviarMensaje(mensaje, this);
    }

    recibirMensaje(mensaje: string): void {
        console.log(`${this.nombre} recibe mensaje: ${mensaje}`);
    }
}

// Mediador concreto: Implementación del mediador para el chat
class MediadorChat implements Mediador {
    private usuarios: Usuario[] = [];

    agregarUsuario(usuario: Usuario): void {
        this.usuarios.push(usuario);
    }

    enviarMensaje(mensaje: string, remitente: Usuario): void {
        this.usuarios.forEach((usuario) => {
            if (usuario !== remitente) {
                usuario.recibirMensaje(mensaje);
            }
        });
    }
}

// Cliente
const mediador = new MediadorChat();

const usuario1 = new Usuario("Juan", mediador);
const usuario2 = new Usuario("María", mediador);
const usuario3 = new Usuario("Pedro", mediador);

mediador.agregarUsuario(usuario1);
mediador.agregarUsuario(usuario2);
mediador.agregarUsuario(usuario3);

// Simular conversación entre usuarios
usuario1.enviarMensaje("Hola a todos");
usuario2.enviarMensaje("Hola Juan");
usuario3.enviarMensaje("Hola María");

```


### Memento<a name="memento"></a>


| **Complejidad** | **★★★** |
| ----- | ----  |
| **Popularidad** | **★✰✰** |


#### Propósito 

Capturar y externalizar el estado interno de un objeto sin violar la encapsulación, de modo que el objeto pueda ser restaurado a ese estado más tarde. Esto permite implementar la funcionalidad "deshacer" o "volver atrás" en una aplicación, así como mantener un historial de cambios.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Permite la restauración de un objeto a un estado anterior | Puede aumentar la complejidad de implementación     |
| Proporciona un mecanismo de "deshacer" o "volver atrás" | Requiere el almacenamiento de múltiples instantáneas del estado |
| Facilita la implementación de patrones como "Command" o "Snapshot" |                                                     |


#### Problema

Consideremos que tenemos un un editor de texto que permite al usuario escribir y modificar contenido. Queremos implementar una funcionalidad de "deshacer" que permita al usuario revertir los cambios realizados en el texto.

#### Ejemplo

```ts
index.ts
-----------------------------------------
// Memento: Clase para almacenar el estado del editor de texto
class MementoTexto {
    constructor(private estado: string) {}

    obtenerEstado(): string {
        return this.estado;
    }
}

// Editor de texto: Clase para representar el editor de texto
class EditorTexto {
    private contenido: string = "";

    escribirTexto(texto: string): void {
        this.contenido += texto;
    }

    obtenerTexto(): string {
        return this.contenido;
    }

    guardarEstado(): MementoTexto {
        return new MementoTexto(this.contenido);
    }

    restaurarEstado(memento: MementoTexto): void {
        this.contenido = memento.obtenerEstado();
    }
}

// Caretaker: Clase que gestiona los estados del editor de texto
class GestorEstados {
    private estados: MementoTexto[] = [];

    guardarEstado(memento: MementoTexto): void {
        this.estados.push(memento);
    }

    obtenerEstado(index: number): MementoTexto {
        return this.estados[index];
    }
}

// Cliente
const editor = new EditorTexto();
const gestorEstados = new GestorEstados();

// Escribir y guardar estados del editor de texto
editor.escribirTexto("Hola, ");
gestorEstados.guardarEstado(editor.guardarEstado());

editor.escribirTexto("¿cómo estás?");
gestorEstados.guardarEstado(editor.guardarEstado());

// Restaurar estado anterior del editor de texto
editor.restaurarEstado(gestorEstados.obtenerEstado(0));
console.log("Texto actual después de deshacer: ", editor.obtenerTexto());

```




### Observer<a name="observer"></a>


| **Complejidad** | **★★✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |


#### Propósito 

Establecer una relación uno a muchos entre objetos, de modo que cuando el estado de uno de los objetos cambie, todos los objetos dependientes sean notificados y actualizados automáticamente. Esto permite mantener la consistencia entre los objetos y asegura que los cambios en un objeto se reflejen en otros objetos relacionados.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Desacopla el sujeto observable de sus observadores  | Puede haber una sobrecarga de notificaciones        |
| Permite la actualización automática de los observadores cuando cambia el estado del sujeto observable | Puede ser difícil de depurar en sistemas complejos   |
| Facilita la implementación de sistemas distribuidos y basados en eventos |                                                     |


#### Problema

Consideremos que tenemos un sistema de noticias donde múltiples suscriptores desean recibir actualizaciones cuando se publiquen nuevas noticias. Queremos implementar un sistema utilizando el patrón Observer para notificar automáticamente a los suscriptores cuando se publiquen nuevas noticias.


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Sujeto observable: Interfaz para el sujeto observable
interface SujetoObservable {
    registrarObservador(observador: Observador): void;
    eliminarObservador(observador: Observador): void;
    notificarObservadores(): void;
}

// Observador: Interfaz para los observadores
interface Observador {
    actualizar(nuevaNoticia: string): void;
}

// Sujeto concreto observable: Implementación del sujeto observable (Editor de noticias)
class EditorNoticias implements SujetoObservable {
    private observadores: Observador[] = [];
    private ultimaNoticia: string = "";

    registrarObservador(observador: Observador): void {
        this.observadores.push(observador);
    }

    eliminarObservador(observador: Observador): void {
        this.observadores = this.observadores.filter(obs => obs !== observador);
    }

    notificarObservadores(): void {
        this.observadores.forEach(observador => {
            observador.actualizar(this.ultimaNoticia);
        });
    }

    public publicarNoticia(nuevaNoticia: string): void {
        this.ultimaNoticia = nuevaNoticia;
        this.notificarObservadores();
    }
}

// Observador concreto: Implementación del observador (Suscriptor de noticias)
class SuscriptorNoticias implements Observador {
    constructor(private nombre: string) {}

    actualizar(nuevaNoticia: string): void {
        console.log(`${this.nombre} recibe la nueva noticia: ${nuevaNoticia}`);
    }
}

// Cliente
const editorNoticias = new EditorNoticias();

const suscriptor1 = new SuscriptorNoticias("Juan");
const suscriptor2 = new SuscriptorNoticias("María");
const suscriptor3 = new SuscriptorNoticias("Pedro");

editorNoticias.registrarObservador(suscriptor1);
editorNoticias.registrarObservador(suscriptor2);
editorNoticias.registrarObservador(suscriptor3);

// Publicar nueva noticia
editorNoticias.publicarNoticia("Se lanza un nuevo producto");

```




### State<a name="state"></a>

| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★✰** |


#### Propósito 

Permitir que un objeto altere su comportamiento cuando su estado interno cambia. El objeto aparecerá como si cambiara su clase.



#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Facilita la gestión de estados y comportamientos complejos | Puede aumentar la complejidad del código            |
| Promueve un diseño más flexible y mantenible        | Puede requerir la implementación de múltiples clases de estado |
| Permite que el objeto cambie su comportamiento dinámicamente |                                                     |


#### Problema

Consideremos que tenemos un reproductor de música que puede reproducir, pausar y detener la reproducción. Queremos implementar el patrón State para que el reproductor cambie su comportamiento dependiendo de su estado actual (reproduciendo, pausado o detenido).


#### Ejemplo

```ts
index.ts
-----------------------------------------
// Estado: Interfaz para los estados del reproductor
interface EstadoReproductor {
    reproducir(): void;
    pausar(): void;
    detener(): void;
}

// Contexto: Clase que representa al reproductor y mantiene una referencia al estado actual
class ReproductorMusica {
    private estadoActual: EstadoReproductor;

    constructor() {
        // El estado inicial es detenido
        this.estadoActual = new EstadoDetenido(this);
    }

    // Métodos para cambiar el estado del reproductor
    cambiarEstado(estado: EstadoReproductor): void {
        this.estadoActual = estado;
    }

    reproducir(): void {
        this.estadoActual.reproducir();
    }

    pausar(): void {
        this.estadoActual.pausar();
    }

    detener(): void {
        this.estadoActual.detener();
    }
}

// Estados concretos: Implementaciones de los estados del reproductor
class EstadoReproduciendo implements EstadoReproductor {
    constructor(private reproductor: ReproductorMusica) {}

    reproducir(): void {
        console.log("La canción ya está reproduciendo");
    }

    pausar(): void {
        console.log("Canción en pausa");
        this.reproductor.cambiarEstado(new EstadoPausado(this.reproductor));
    }

    detener(): void {
        console.log("Canción detenida");
        this.reproductor.cambiarEstado(new EstadoDetenido(this.reproductor));
    }
}

class EstadoPausado implements EstadoReproductor {
    constructor(private reproductor: ReproductorMusica) {}

    reproducir(): void {
        console.log("Continuando la reproducción");
        this.reproductor.cambiarEstado(new EstadoReproduciendo(this.reproductor));
    }

    pausar(): void {
        console.log("La canción ya está en pausa");
    }

    detener(): void {
        console.log("Canción detenida");
        this.reproductor.cambiarEstado(new EstadoDetenido(this.reproductor));
    }
}

class EstadoDetenido implements EstadoReproductor {
    constructor(private reproductor: ReproductorMusica) {}

    reproducir(): void {
        console.log("Reproduciendo la canción");
        this.reproductor.cambiarEstado(new EstadoReproduciendo(this.reproductor));
    }

    pausar(): void {
        console.log("La canción está detenida, no se puede pausar");
    }

    detener(): void {
        console.log("El reproductor ya está detenido");
    }
}

// Cliente
const reproductor = new ReproductorMusica();

// Simular operaciones de reproducción
reproductor.reproducir(); // Imprime "Reproduciendo la canción"
reproductor.pausar();    // Imprime "Canción en pausa"
reproductor.reproducir(); // Imprime "Continuando la reproducción"
reproductor.detener();   // Imprime "Canción detenida"

```





### Strategy<a name="strategy"></a>


| **Complejidad** | **★✰✰** |
| ----- | ----  |
| **Popularidad** | **★★★** |


#### Propósito 

Definir una familia de algoritmos, encapsular cada uno de ellos y hacerlos intercambiables. Esto permite que el algoritmo varíe independientemente de los clientes que lo utilizan.

#### Pros y contras

| Pros                                                | Contras                                             |
|-----------------------------------------------------|-----------------------------------------------------|
| Permite cambiar el comportamiento de un objeto sin modificar su estructura | Requiere la creación de múltiples clases concretas |
| Facilita la reutilización de algoritmos            | Puede aumentar la complejidad de la aplicación      |
| Promueve un diseño flexible y mantenible           | Puede introducir una sobrecarga de abstracción      |


#### Problema

Consideremos que tenemos un sistema de procesamiento de pagos que necesita calcular el precio final de una compra aplicando diferentes estrategias de descuento según el tipo de cliente. Queremos implementar el patrón Strategy para permitir que el sistema aplique fácilmente diferentes estrategias de descuento.

#### Ejemplo

```ts
index.ts
-----------------------------------------
// Contexto: Clase que representa el contexto en el que se aplica la estrategia de descuento
class ContextoCompra {
    constructor(private estrategiaDescuento: EstrategiaDescuento) {}

    calcularDescuento(precio: number): number {
        return this.estrategiaDescuento.calcularDescuento(precio);
    }

    setEstrategiaDescuento(estrategiaDescuento: EstrategiaDescuento): void {
        this.estrategiaDescuento = estrategiaDescuento;
    }
}

// Estrategia: Interfaz para definir las estrategias de descuento
interface EstrategiaDescuento {
    calcularDescuento(precio: number): number;
}

// Estrategias concretas: Implementaciones de las estrategias de descuento
class DescuentoNormal implements EstrategiaDescuento {
    calcularDescuento(precio: number): number {
        return precio;
    }
}

class DescuentoMiembroPlata implements EstrategiaDescuento {
    calcularDescuento(precio: number): number {
        return precio * 0.9; // 10% de descuento para miembros de nivel plata
    }
}

class DescuentoMiembroOro implements EstrategiaDescuento {
    calcularDescuento(precio: number): number {
        return precio * 0.8; // 20% de descuento para miembros de nivel oro
    }
}

// Cliente
const contexto = new ContextoCompra(new DescuentoNormal());

// Simular una compra con diferentes tipos de cliente
const precioCompra = 100;

console.log("precio sin descuento:", precioCompra);

contexto.setEstrategiaDescuento(new DescuentoMiembroPlata());
console.log("precio con descuento para miembro plata:", contexto.calcularDescuento(precioCompra));

contexto.setEstrategiaDescuento(new DescuentoMiembroOro());
console.log("precio con descuento para miembro oro:", contexto.calcularDescuento(precioCompra));

```




### Template Method<a name="template-method"></a>
### Visitor<a name="visitor"></a>

---




---

# 3. Bibliografía<a name="biblio"></a>

* https://refactoring.guru/

---

