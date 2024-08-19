<a name="inicio"></a>
Arison WMS|TMS - API REST INTEGRACION
=======

- [Generalidades](#generalidades)
  - [Integraciones soportadas por Arison](#versiones)
  - [Estructura estándar de una URL en Arison](#url)
  - [Formatos de datos](#datos)
  - [Autenticación](#autenticacion)
  - [Consulta de datos](#consulta)
  - [Otras integraciones](#otras)
- [Documentación detallada de la API](#documentacion)
  - [Swagger](#swagger)
- [Ambientes](#ambientes)
  - [Descripción de los ambientes](#ambientesdescripcion)
  - [Gestión de las configuraciones](#gestion)
  - [Selección del ambiente](#ambientesseleccion)
- [Datos JSON](#datosjson) 

  
  

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

Las URLs en Arison siguen un patrón estándar para identificar los recursos y las acciones a realizar sobre ellos, la URL varia en cada implementación pero mantiene el estándar.


https://urlvariable.com/[api]/[recurso]/[id]
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

Implementado Arison y contratado el modulo de integración comienzan a estar disponible la API con datos. 

<a name="otras"></a>
### Otras integraciones
Nuestra API flexible se integra fácilmente con cualquier sistema, independientemente del formato o método de intercambio de datos, garantizando una adaptabilidad total a diversas plataformas y tecnologías. Nuestra API admite integraciones a través de múltiples métodos, incluyendo la importación de datos desde CSV, XML, archivos de texto, archivos excel, intercambios por FTP entre muchos otros mas.  
Para obtener más información, no dude en consultar con Arison.

<a name="documentacion"></a>
## Documentación detallada de la API

[<sub>Volver</sub>](#inicio)

<a name="Swagger"></a>
### Swagger
Para una exploración más detallada de la API y ejemplos interactivos, te invitamos a visitar nuestra documentación técnica en Swagger:  

http://loginarison.ongania.com:4508/swagger/index.html  
En este enlace encontrarás una descripción completa de todos los endpoints, parámetros, respuestas y ejemplos de uso. 

![Interfaz de Swagger de Arison](https://github.com/desarrolloOngania/IntegracionArison/blob/4cc80d2cf38c888837ae85feccd8d32f73021a26/Arison_Swagger.png)

Con Swagger podrás    

Explorar los endpoints: Descubre todos los recursos disponibles y las operaciones que puedes realizar.  
Ver ejemplos: Observa ejemplos prácticos de solicitudes y respuestas.  
Realizar pruebas: Interactúa directamente con la API para verificar su funcionamiento (solicitar habilitacion y token).  

<a name="ambientes"></a>

## Ambientes

Para garantizar la calidad y estabilidad de nuestra aplicación, hemos implementado un sistema de ambiente de trabajo. Estos ambientes se diferencian principalmente por la URL de la API.

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

<a name="datosjson"></a>

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
```

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
```

Ejemplo de JSON basado en RequerimientoDto

```json
{
  "empresa": "M",
  "codCd": "CD001",
  "codEstado": "E001",
  "estado": "Pendiente",
  "cantPedid": 100.0,
  "cantADes": 80.0,
  "cantPenD": 20.0,
  "codArticu": "ART123",
  "nRenglon": 1,
  "nroPedido": "P12345",
  "talonPed": "T001",
  "codRequisisor": "C001",
  "nombreRequisisor": "Cliente Ejemplo",
  "fechaPedi": "2024-08-16T00:00:00",
  "fechaEntr": "2024-08-20T00:00:00",
  "descripcion": "Artículo Ejemplo",
  "descAdic": "Descripción adicional del artículo",
  "unidadMedidaSeleccionada": "UN",
  "equivaleV": 1.0,
  "descCond": "Condición de venta ejemplo",
  "transporte": "Transporte Ejemplo",
  "localidad": "Localidad Ejemplo",
  "direccion": "Calle Ejemplo 123",
  "provincia": "Provincia Ejemplo",
  "leyenda1": "Leyenda 1",
  "leyenda2": "Leyenda 2",
  "leyenda3": "Leyenda 3",
  "leyenda4": "Leyenda 4",
  "leyenda5": "Leyenda 5",
  "idDireccionEntrega": "DIR001",
  "codTransp": "TR001",
  "generador": "Pedidos",
  "codDeposito": "DEP001",
  "tReq": "PED",
  "idTabla": "TBL001",
  "tablaOrigen": "Tabla Origen Ejemplo",
  "fechaApru": "2024-08-18T00:00:00",
  "clase": "A",
  "tipoCliente": "FINAL", 
  "vendedor": "Vendedor Ejemplo", 
  "tCompAsoc": "T001", 
  "nCompAsoc": "C001",
  "precio": 100.0, 
  "monCte": "ARS", 
  "depoProveedor": "DEP001" 
}

Descripción de los campos:
empresa: 'M' para base de datos maestra o 'B' para base de datos alternativa.
codCd: Código del centro de distribución que atenderá la demanda.
codEstado: Código que representa el estado del pedido.
estado: Descripción del estado del pedido.
cantPedid: Cantidad pedida originalmente en el pedido.
cantADes: Cantidad habilitada para recolectarse.
cantPenD: Cantidad no remitida aún.
codArticu: Código único del artículo solicitado.
nRenglon: Número del renglón del requerimiento dentro del pedido.
nroPedido: Número de identificación del pedido.
talonPed: Código del talonario asociado al pedido.
codRequisisor: Código del cliente o requisitor que solicitó el pedido.
nombreRequisisor: Nombre del cliente o requisitor.
fechaPedi: Fecha de ingreso del pedido en el sistema.
fechaEntr: Fecha solicitada para la entrega del pedido.
descripcion: Descripción del artículo solicitado.
descAdic: Descripción adicional del artículo.
unidadMedidaSeleccionada: Unidad de medida utilizada para expresar la cantidad del artículo.
equivaleV: Equivalencia entre unidades de medida y bultos.
descCond: Descripción de la condición de venta (OBLIGATORIO para remisión).
transporte: Nombre del transporte para la entrega (OBLIGATORIO para remisión).
localidad: Localidad de la dirección de entrega (OBLIGATORIO para remisión).
direccion: Dirección de entrega del pedido (OBLIGATORIO para remisión).
provincia: Provincia de la dirección de entrega (OBLIGATORIO para remisión).
leyenda1: Primera leyenda a imprimir en la remisión (OBLIGATORIO para remisión).
leyenda2: Segunda leyenda a imprimir en la remisión (OBLIGATORIO para remisión).
leyenda3: Tercera leyenda a imprimir en la remisión (OBLIGATORIO para remisión).
leyenda4: Cuarta leyenda a imprimir en la remisión (OBLIGATORIO para remisión).
leyenda5: Quinta leyenda a imprimir en la remisión (OBLIGATORIO para remisión).
idDireccionEntrega: Identificador único de la dirección de entrega (OBLIGATORIO para remisión).
codTransp: Código del transporte (OBLIGATORIO para remisión).
generador: Fuente o generador del pedido, en este caso 'Pedidos'.
codDeposito: Código del depósito seleccionado para abastecer la demanda.
tReq: Tipo de requerimiento, en este caso 'PED'.
idTabla: Identificador único de la tabla de origen.
tablaOrigen: Nombre de la tabla de origen.
fechaApru: Fecha de aprobación del pedido (puede ser nula).
clase: Categoría del cliente (por ejemplo, A, B, C).
tipoCliente: Tipo de cliente según la categorización (por ejemplo, FINAL, FRANQUICIA, DISTRIBUIDOR).
vendedor: Nombre del vendedor asociado al pedido.
tCompAsoc: Tipo de comprobante asociado al pedido.
nCompAsoc: Número del comprobante asociado.
precio: Precio unitario del artículo (puede ser nulo).
monCte: Moneda corriente utilizada en el pedido.
depoProveedor: Código del depósito que abastece la demanda.
```
### Ejemplo de JSON para la API REST basado en `DepositoDto`
```
{
  "CodigoDeposito": "DPT001",
  "Nombre": "Depósito Principal",
  "UsaIDPallet": 1,
  "CodigoDepositoTDI": 123,
  "RecuentaInventario": 1,
  "PidePalletOrigenEnPuk": 0,
  "PidePalletDestinoEnPuk": 1,
  "UsaZonas": 1,
  "LecturaEnPicking": "Sí",
  "LecturaEnAlmacenaje": "No",
  "PickingMultiPallet": 0,
  "AlmacenajeMultiPallet": 1,
  "VerificaStockEnEstiba": 1,
  "FractionsEnable": 0,
  "IdUbicacionNoHallados": 999,
  "IdUbicacionPivot": 100,
  "PermiteTransferenciaAUbicacion": 1,
  "EsDepositoDetallado": 1,
  "IdUbicacionCuarentena": 200,
  "CodigoCentroDistribucion": "CD001",
  "DiasAlVencimiento": 30,
  "DepositoDeTerceros": 0,
  "DimensionCambioSentidoRecoleccion": 10,
  "UsaStockUbicacion": 1,
  "DescDim1": "Altura",
  "DescDim2": "Ancho",
  "DescDim3": "Largo",
  "DescDim4": "Peso",
  "DescDim5": "Volumen"
}

Descripción de los Campos
CodigoDeposito: Código del depósito (Requerido)
Nombre: Nombre del depósito (Requerido)
UsaIDPallet: Indica si se utiliza ID de pallet (0: No, 1: Sí)
CodigoDepositoTDI: Código del depósito para TDI (Toma de inventario)
RecuentaInventario: Indica si se realiza recuento de inventario (0: No, 1: Sí)
PidePalletOrigenEnPuk: Indica si se pide pallet de origen en PUK (0: No, 1: Sí)
PidePalletDestinoEnPuk: Indica si se pide pallet de destino en PUK (0: No, 1: Sí)
UsaZonas: Indica si el depósito utiliza zonas (0: No, 1: Sí)
LecturaEnPicking: Indica si se requiere lectura en picking (Sí/No)
LecturaEnAlmacenaje: Indica si se requiere lectura en almacenaje (Sí/No)
PickingMultiPallet: Indica si se permite picking multi-pallet (0: No, 1: Sí)
AlmacenajeMultiPallet: Indica si se permite almacenaje multi-pallet (0: No, 1: Sí)
VerificaStockEnEstiba: Indica si se verifica stock en estiba (0: No, 1: Sí)
FractionsEnable: Indica si se habilita el uso de fracciones (0: No, 1: Sí)
IdUbicacionNoHallados: ID de ubicación para productos no hallados
IdUbicacionPivot: ID de ubicación pivote
PermiteTransferenciaAUbicacion: Indica si se permite transferencia a ubicación (0: No, 1: Sí)
EsDepositoDetallado: Indica si es un depósito detallado (0: No, 1: Sí)
IdUbicacionCuarentena: ID de ubicación de cuarentena
CodigoCentroDistribucion: Código del Centro de Distribución (CD) (Requerido)
DiasAlVencimiento: Días al vencimiento de los productos en el depósito
DepositoDeTerceros: Indica si el depósito pertenece a un tercero (0: No, 1: Sí)
DimensionCambioSentidoRecoleccion: Dimensión para cambiar el sentido de recolección
UsaStockUbicacion: Indica si se utiliza stock por ubicación (0: No, 1: Sí)
DescDim1: Descripción de la primera dimensión
DescDim2: Descripción de la segunda dimensión
DescDim3: Descripción de la tercera dimensión
DescDim4: Descripción de la cuarta dimensión
DescDim5: Descripción de la quinta dimensión

```
Ejemplo en JSON
### Ejemplo de JSON para la API REST basado en `DepositoDto`
```
public class VendedorDto
{
    /// <summary>
    /// Código del vendedor
    /// </summary>
    [Required]
    public string Codigo { get; set; }

    /// <summary>
    /// Nombre del vendedor
    /// </summary>
    [Required]
    public string Nombre { get; set; }

    /// <summary>
    /// Porcentaje de comisión
    /// </summary>
    public decimal PorcentageComision { get; set; }

    /// <summary>
    /// Código de la tienda
    /// </summary>
    public string CodigoShop { get; set; }

    /// <summary>
    /// Indica si el vendedor está inhabilitado
    /// </summary>
    public bool Inhabilita { get; set; }

    /// <summary>
    /// Tipo de documento (DNI, pasaporte, etc.)
    /// </summary>
    public string TipoDoc { get; set; }

    /// <summary>
    /// Número de documento
    /// </summary>
    public string NumeroDoc { get; set; }

    /// <summary>
    /// Domicilio del vendedor
    /// </summary>
    public string Domicilio { get; set; }

    /// <summary>
    /// Código postal
    /// </summary>
    public string CodPostal { get; set; }

    /// <summary>
    /// Localidad
    /// </summary>
    public string Localidad { get; set; }

    /// <summary>
    /// Código de provincia
    /// </summary>
    public string CodProvin { get; set; }

    /// <summary>
    /// Teléfono
    /// </summary>
    public string Telefono { get; set; }

    /// <summary>
    /// Correo electrónico
    /// </summary>
    public string EMail { get; set; }

    /// <summary>
    /// Código GVA23 (posiblemente un código de referencia interno)
    /// </summary>
    public string CodGVA23 { get; set; }

    /// <summary>
    /// Observaciones adicionales
    /// </summary>
    public string Observaciones { get; set; }

    /// <summary>
    /// Código GVA18 (posiblemente otro código de referencia interno)
    /// </summary>
    public string CodGVA18 { get; set; }

    /// <summary>
    /// Versión de la fila (para control de cambios)
    /// </summary>
    public int RowVersion { get; set; }

    /// <summary>
    /// Campos adicionales (para datos no especificados en esta clase)
    /// </summary>
    public string CamposAdicionales { get; set; }

    /// <summary>
    /// ID de GVA23 (posiblemente un identificador único)
    /// </summary>
    public int IdGVA23 { get; set; }

    /// <summary>
    /// ID de GVA18 (posiblemente un identificador único)
    /// </summary>
    public int IdGVA18 { get; set; }

    /// <summary>
    /// ID del tipo de documento en el sistema GVA
    /// </summary>
    public int IdTipoDocumentoGv { get; set; }
}

Descripción de los Campos
Codigo: Código del vendedor (Requerido)
Nombre: Nombre del vendedor (Requerido)
PorcentageComision: Porcentaje de comisión que recibe el vendedor.
CodigoShop: Código de la tienda a la que está asociado el vendedor.
Inhabilita: Indica si el vendedor está inhabilitado (true: Sí, false: No).
TipoDoc: Tipo de documento del vendedor (DNI, pasaporte, etc.).
NumeroDoc: Número de documento del vendedor.
Domicilio: Domicilio del vendedor.
CodPostal: Código postal del domicilio del vendedor.
Localidad: Localidad donde reside el vendedor.
CodProvin: Código de provincia donde reside el vendedor.
Telefono: Número de teléfono del vendedor.
EMail: Correo electrónico del vendedor.
CodGVA23: Código GVA23 (posiblemente un código de referencia interno).
Observaciones: Observaciones adicionales sobre el vendedor.
CodGVA18: Código GVA18 (posiblemente otro código de referencia interno).
RowVersion: Versión de la fila (para control de cambios).
CamposAdicionales: Campos adicionales para datos no especificados en esta clase.
IdGVA23: ID de GVA23 (posiblemente un identificador único).
IdGVA18: ID de GVA18 (posiblemente un identificador único).
IdTipoDocumentoGv: ID del tipo de documento en el sistema GVA.
```
### Ejemplo de JSON para la API REST basado en `TransporteDto`
```
public class TransporteDto
{
    /// <summary>
    /// Código único que identifica al transporte.
    /// </summary>
    [Required]
    public int CodigoTransporte { get; set; }

    /// <summary>
    /// CUIT del transporte.
    /// </summary>
    public string CUITTransporte { get; set; }

    /// <summary>
    /// Dirección del transporte.
    /// </summary>
    public string DomicilioTransporte { get; set; }

    /// <summary>
    /// Nombre del transporte.
    /// </summary>
    public string NombreTransporte { get; set; }

    /// <summary>
    /// Porcentaje de recargo aplicado.
    /// </summary>
    public decimal PorcentajeRecargo { get; set; }

    /// <summary>
    /// Código postal del transporte.
    /// </summary>
    public string CodigoPostal { get; set; }

    /// <summary>
    /// Localidad donde está ubicado el transporte.
    /// </summary>
    public string Localidad { get; set; }

    /// <summary>
    /// Código de la provincia donde está ubicado el transporte.
    /// </summary>
    public string CodigoProvincia { get; set; }

    /// <summary>
    /// Número de teléfono del transporte.
    /// </summary>
    public string Telefono { get; set; }

    /// <summary>
    /// Correo electrónico del transporte.
    /// </summary>
    public string Email { get; set; }

    /// <summary>
    /// Página web del transporte.
    /// </summary>
    public string Web { get; set; }

    /// <summary>
    /// Código GVA24, posiblemente un código de referencia interno.
    /// </summary>
    public string CodigoGVA24 { get; set; }

    /// <summary>
    /// Observaciones adicionales sobre el transporte.
    /// </summary>
    public string Observaciones { get; set; }

    /// <summary>
    /// Código GVA18, posiblemente otro código de referencia interno.
    /// </summary>
    public string CodigoGVA18 { get; set; }

    /// <summary>
    /// Identificador único de GVA24.
    /// </summary>
    public int IdGVA24 { get; set; }

    /// <summary>
    /// Versión de la fila para control de cambios.
    /// </summary>
    public string RowVersion { get; set; }

    /// <summary>
    /// Información adicional en formato XML o similar.
    /// </summary>
    public string CamposAdicionales { get; set; }

    /// <summary>
    /// Identificador único de GVA18.
    /// </summary>
    public string IdGVA18 { get; set; }
}

Descripción de los Campos 
CodigoTransporte: Código único que identifica al transporte.
CUITTransporte: CUIT del transporte.
DomicilioTransporte: Dirección del transporte.
NombreTransporte: Nombre del transporte.
PorcentajeRecargo: Porcentaje de recargo aplicado.
CodigoPostal: Código postal del transporte.
Localidad: Localidad donde está ubicado el transporte.
CodigoProvincia: Código de la provincia donde está ubicado el transporte.
Telefono: Número de teléfono del transporte.
Email: Correo electrónico del transporte.
Web: Página web del transporte.
CodigoGVA24: Código GVA24, posiblemente un código de referencia interno.
Observaciones: Observaciones adicionales sobre el transporte.
CodigoGVA18: Código GVA18, posiblemente otro código de referencia interno.
IdGVA24: Identificador único de GVA24.
RowVersion: Versión de la fila para control de cambios.
CamposAdicionales: Información adicional en formato XML o similar.
IdGVA18: Identificador único de GVA18.

``` 
