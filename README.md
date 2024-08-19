<a name="inicio"></a>
Arison WMS|TMS - API REST INTEGRACION
=======

- [Generalidades](#generalidades)
  - [Integraciones soportadas por Arison](#versiones)
  - [Estructura estándar de una URL en Arison](#url)
  - [Formatos de datos](#datos)
  - [Autenticación](#autenticacion)
  - [Consulta de datos](#consulta)
- [Documentación detallada de la API](#documentacion)
  - [Swagger](#swagger)
- [Ambientes](#ambientes)
  - [Descripción de los ambientes](#ambientesdescripcion)
  - [Gestión de las configuraciones](#gestion)
  - [Selección del ambiente](#ambientesseleccion)
- [Datos JSON](#datos) 

  
  

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

<a name="url"></a>
### Estructura estándar de una URL en Arison

Las URLs en Arison siguen un patrón estándar para identificar los recursos y las acciones a realizar sobre ellos, la URL varia en cada implementacion pero mantiene el standars


[https://urlvariable.com/[api]/[recurso]/[id]
recurso: Especifica el tipo de recurso sobre el que se va a realizar la operación (usuarios, productos, etc.).
id: Identificador único del recurso (opcional, según la operación).
Ejemplo:

https://api.arison.com/api/clientes/123
Esta URL se utilizaría para obtener la información del cliente con el ID 123.

<a name="datos"></a>
### Formatos de datos

Arison utiliza el formato JSON (JavaScript Object Notation) para intercambiar datos entre el cliente y el servidor. JSON es un formato ligero y fácil de leer tanto por humanos como por máquinas.

<a name="autenticacion"></a>
### Autenticación

Para proteger los recursos de la API, Arison utiliza el metodo bearer token

<a name="consulta"></a>
### Consulta de datos

Implementado Arison y contratado el modulo de integracion comienzan a estar disponible la API con datos. 

<a name="documentacion"></a>

## Documentación detallada de la API

[<sub>Volver</sub>](#inicio)

<a name="Swagger"></a>
### Swagger
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

<a name="ambientesdescripcion"></a>
### Descripción de los ambientes
* **Desarrollo:** Este ambiente está destinado a los desarrolladores para realizar pruebas, depurar código y desarrollar nuevas funcionalidades. Las configuraciones en este ambiente pueden ser modificadas con frecuencia.
* **Producción:** Este es el ambiente en vivo donde los usuarios interactúan con la aplicación. Las configuraciones en este ambiente son estables y se modifican con cuidado para evitar interrupciones en el servicio.
<a name="gestion"></a>
### Gestión de las configuraciones
Las diferencias entre los ambientes se gestionan principalmente a través de:

* **Variables de entorno:** Estas variables permiten configurar de manera dinámica diferentes aspectos de la aplicación, como la URL de la base de datos, las claves de API y otras configuraciones sensibles.
* **Archivos de configuración:** Algunos ajustes específicos pueden estar definidos en archivos de configuración separados para cada ambiente.

<a name="ambientesseleccion"></a>
### Selección del ambiente
La selección del ambiente se realiza de la siguiente manera:

* **Durante el desarrollo:** Los desarrolladores configuran localmente las variables de entorno o utilizan herramientas de desarrollo que permiten cambiar el ambiente de forma sencilla.
* **En producción:** El ambiente de producción se configura de forma fija y no puede ser modificado por los usuarios finales.

### Tabla comparativa
| Ambiente | URL de ejemplo | Propósito | Características clave |
|---|---|---|---|
| Desarrollo | http://api.arison.ongania.com:4508/dev | Pruebas y desarrollo | Configuraciones flexibles, datos de prueba |
| Producción | https://api.arison.ongania.com | Uso en producción | Configuraciones estables, datos reales |

<a name="datos"></a>

## Datos JSON

### Ejemplo de JSON para la API REST basado en ClienteDto

```json
{
  "codigo": "C12345",
  "documentoIdentificatorio": "20304050607",
  "nombre": "Acme Corporation S.A.",
  "nombreComercial": "Acme",
  "clase": "A",
  "tipo": "DISTRIBUIDOR",
  "tiempoDescarga": 15,
  "generarPasswordEntrega": true
}

Descripción de los campos
codigo: Código identificatorio del cliente. Ejemplo: "C12345".
documentoIdentificatorio: CUIT o documento identificatorio del cliente. Ejemplo: "20304050607".
nombre: Razón social del cliente. Ejemplo: "Acme Corporation S.A.".
nombreComercial: Nombre comercial del cliente. Ejemplo: "Acme".
clase: Clase del cliente, como "A", "B", "C", etc. Ejemplo: "A".
tipo: Categorización del cliente, como "DISTRIBUIDOR", "INDUSTRIA", "COMERCIO". Ejemplo: "DISTRIBUIDOR".
tiempoDescarga: Tiempo en minutos de descarga de entregas del cliente. Ejemplo: 15.
generarPasswordEntrega: Indicador de si se debe generar un código de entrega para el cliente. Ejemplo: true.

### Ejemplo de JSON para la API REST basado en `ArticuloDto`

```json
{
  "codigo": "A12345",
  "codigoBarra": "1234567890123",
  "descripcion": "Producto Ejemplo",
  "descripcionAdicional": "Versión mejorada del Producto Ejemplo",
  "sinonimo": "ProductoX",
  "equivalencia": 1.5,
  "permiteSobreVenta": true,
  "diasPreparacion": 3,
  "diasAlVencimiento": 180,
  "codigoDepositoProveedor": "D001",
  "codigoZona": "Z001",
  "idMedidaPeso": 1,
  "peso": 2.5,
  "idMedidaVolumen": 2,
  "volumen": 1.75
}
Descripción de los campos
codigo: Código del artículo. Ejemplo: "A12345".
codigoBarra: Código de barras del artículo. Ejemplo: "1234567890123".
descripcion: Descripción principal del artículo. Ejemplo: "Producto Ejemplo".
descripcionAdicional: Descripción secundaria del artículo. Ejemplo: "Versión mejorada del Producto Ejemplo".
sinonimo: Sinónimo para identificar el artículo. Ejemplo: "ProductoX".
equivalencia: Equivalencia del artículo en unidades. Ejemplo: 1.5.
permiteSobreVenta: Indica si se permite el stock negativo del artículo. Ejemplo: true.
diasPreparacion: Número de días de preparación del artículo. Ejemplo: 3.
diasAlVencimiento: Días restantes hasta el vencimiento del artículo. Ejemplo: 180.
codigoDepositoProveedor: Código del depósito que provee al artículo por defecto. Ejemplo: "D001".
codigoZona: Código de la zona donde se almacena el artículo. Ejemplo: "Z001".
idMedidaPeso: Identificador de la unidad de medida del peso del artículo. Ejemplo: 1.
peso: Peso del artículo en la unidad correspondiente. Ejemplo: 2.5.
idMedidaVolumen: Identificador de la unidad de medida del volumen del artículo. Ejemplo: 2.
volumen: Volumen del artículo en la unidad correspondiente. Ejemplo: 1.75.

