<a name="inicio"></a>
Arison WMS|TMS - API REST INTEGRACION
=======

- [Generalidades](#generalidades)
  - [Integraciones soportadas por Arison](#versiones)
  - [Estructura estándar de una URL en Arison](#generalidades)
  - [Formatos de datos](#asociarapi)
  - [Autenticación](#asociarapi)
  - [Consulta de datos](#asociarapi)
- [Documentación detallada de la API](#documentacion)
  - [Novedades](#novedades)
  - [Datos del JSON](#djson)
  - [Ordenes por Lote](#lote)
  - [Tablas de Referencia](#tablas)
  - [Ejemplo de JSON de una órden](#ejemplojson)
- [Ambientes](#subida)
  - [Configuración](#configuracion)
  - [Conceptos básicos](#ConceptosBasicos)
  - [Recursos de consulta](#recursos)

<a name="generalidades"></a>

## Generalidades

<a name="versiones"></a>


### Integraciones soportadas por Arison

Arison ofrece una robusta API REST que permite a los desarrolladores integrar su aplicación con una amplia variedad de sistemas y servicios. Esta API sigue los estándares RESTful, lo que garantiza una integración sencilla y flexible.

¿Qué es una API REST?
Una API REST (Representational State Transfer) es una interfaz de programación de aplicaciones que permite a diferentes sistemas comunicarse entre sí de manera sencilla y eficiente. Utiliza el protocolo HTTP y los métodos estándar para realizar operaciones sobre recursos.

Métodos HTTP soportados por Arison
Arison soporta los siguientes métodos HTTP, cada uno con una función específica:

GET: Se utiliza para obtener datos de un recurso específico. Por ejemplo, para obtener la información de un usuario en particular.  
POST: Se utiliza para crear un nuevo recurso. Por ejemplo, para registrar un nuevo usuario.  
PUT: Se utiliza para actualizar un recurso existente. Por ejemplo, para modificar la información de un usuario.  
DELETE: Se utiliza para eliminar un recurso. Por ejemplo, para eliminar un usuario.  

### Estructura estándar de una URL en Arison

Las URLs en Arison siguen un patrón estándar para identificar los recursos y las acciones a realizar sobre ellos, la URL varia en cada implementacion pero mantiene el standars


[https://urlvariable.com/[api]/[recurso]/[id]
recurso: Especifica el tipo de recurso sobre el que se va a realizar la operación (usuarios, productos, etc.).
id: Identificador único del recurso (opcional, según la operación).
Ejemplo:

https://api.arison.com/api/clientes/123
Esta URL se utilizaría para obtener la información del cliente con el ID 123.

### Formatos de datos

Arison utiliza el formato JSON (JavaScript Object Notation) para intercambiar datos entre el cliente y el servidor. JSON es un formato ligero y fácil de leer tanto por humanos como por máquinas.

### Autenticación

Para proteger los recursos de la API, Arison utiliza el metodo bearer token

### Consulta de datos

Implementado Arison y contratado el modulo de integracion comienzan a estar disponible la API con datos. 

<a name="documentacion"></a>

## Documentación detallada de la API

[<sub>Volver</sub>](#inicio)

Para una exploración más detallada de la API y ejemplos interactivos, te invitamos a visitar nuestra documentación técnica en Swagger:  

http://loginarison.ongania.com:4508/swagger/index.html  
En este enlace encontrarás una descripción completa de todos los endpoints, parámetros, respuestas y ejemplos de uso. 

![Interfaz de Swagger de Arison](https://github.com/desarrolloOngania/IntegracionArison/blob/4cc80d2cf38c888837ae85feccd8d32f73021a26/Arison_Swagger.png)

Con Swagger podras    

Explorar los endpoints: Descubre todos los recursos disponibles y las operaciones que puedes realizar.  
Ver ejemplos: Observa ejemplos prácticos de solicitudes y respuestas.  
Realizar pruebas: Interactúa directamente con la API para verificar su funcionamiento (solicitar habilitacion y token).  

<a name="ambientes"></a>

## Ambientes

Para garantizar la calidad y estabilidad de nuestra aplicación, hemos implementado un sistema de ambientes de trabajo. Estos ambientes se diferencian principalmente por la URL de la API.

### Descripción de los ambientes
* **Desarrollo:** Este ambiente está destinado a los desarrolladores para realizar pruebas, depurar código y desarrollar nuevas funcionalidades. Las configuraciones en este ambiente pueden ser modificadas con frecuencia.
* **Producción:** Este es el ambiente en vivo donde los usuarios interactúan con la aplicación. Las configuraciones en este ambiente son estables y se modifican con cuidado para evitar interrupciones en el servicio.

### Gestión de las configuraciones
Las diferencias entre los ambientes se gestionan principalmente a través de:

* **Variables de entorno:** Estas variables permiten configurar de manera dinámica diferentes aspectos de la aplicación, como la URL de la base de datos, las claves de API y otras configuraciones sensibles.
* **Archivos de configuración:** Algunos ajustes específicos pueden estar definidos en archivos de configuración separados para cada ambiente.

### Selección del ambiente
La selección del ambiente se realiza de la siguiente manera:

* **Durante el desarrollo:** Los desarrolladores configuran localmente las variables de entorno o utilizan herramientas de desarrollo que permiten cambiar el ambiente de forma sencilla.
* **En producción:** El ambiente de producción se configura de forma fija y no puede ser modificado por los usuarios finales.

### Tabla comparativa
| Ambiente | URL de ejemplo | Propósito | Características clave |
|---|---|---|---|
| Desarrollo | http://api.arison.ongania.com:4508/dev | Pruebas y desarrollo | Configuraciones flexibles, datos de prueba |
| Producción | https://api.arison.ongania.com | Uso en producción | Configuraciones estables, datos reales |

