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
  - [ClienteDto](#ClienteDTO)

  
  

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

<a name="ClienteDTO"></a>

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

[<sub>Volver</sub>](#inicio)

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

### Ejemplo de JSON para la API REST basado en `VendedorDto`
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
### Ejemplo de JSON para la API REST basado en `VendedorDto`
```
{
    "IdGVA43": 106,
    "CAI": "",
    "CFCopias": 0,
    "Comprobante": "PED",
    "ControlFiscal": 0,
    "Descripcion": "PEDIDO COSACO",
    "Destino": "USB002",
    "Duplica": 0,
    "EditaNumero": 0,
    "FechaVencimiento": "2222-01-01T00:00:00",
    "ModeloControlFiscal": "",
    "NumeroDesde": 1,
    "NumeroHasta": 999999,
    "ProximoNumero": "7407437B53790666",
    "Renglones": 100,
    "Sucursal": 1,
    "TipoFormulario": 1,
    "Talonario": "",
    "TipoComprobante": "PED",
    "Exclusivo": 0,
    "CodigoCaja": "",
    "Manual": 0,
    "NumeroAutorizacion": "",
    "Llave1": "",
    "Llave2": "",
    "FechaAviso": "1800-01-01T00:00:00",
    "ValorFecha": 0,
    "DocumentoElectronico": 0,
    "MetodoControlDe": "L",
    "ImagenTipo": "I",
    "DestinoDeImpresion": "1",
    "ImportacionDeDatos": 0,
    "EnviaPorCorreo": 0,
    "CodigoDocumentoElectronico": 0,
    "SucursalDestino": 0,
    "UsaSistemaImpresion": 0,
    "RutaPdf": "S",
    "UtilizaBonoFiscal": 0,
    "GuardaCopiaPdf": 0,
    "TipoTalonario": "",
    "Observaciones": "NO_CONTROLA",
    "NumeracionPreimpresa": 0,
    "MetodoImpresionComprobantes": "",
    "ConCbuInformado": 0,
    "Recibo": 0,
    "UsaUsb": 0,
    "ComprobanteCredito": 0,
    "PublicaComprobanteTangoTiendas": 0,
    "MetodoExportacion": 0,
    "TipoAutorizacion": "",
    "IdGVA43TalonarioCAEA": 0,
    "UsaDestinoImpresionEnPdf": 0
}

Descripción de los Campos 
IdGVA43: Identificador único del talonario.
CAI: Código de Autorización de Impresión del comprobante.
CFCopias: Cantidad de copias del comprobante.
Comprobante: Tipo de comprobante (e.g., FAC, CRE, REM).
ControlFiscal: Control fiscal del comprobante.
Descripcion: Descripción del talonario.
Destino: Destino del talonario.
Duplica: Indica si se duplica el talonario.
EditaNumero: Indica si se puede editar el número del talonario.
FechaVencimiento: Fecha de vencimiento del talonario.
ModeloControlFiscal: Modelo del control fiscal.
NumeroDesde: Número desde el cual empieza la numeración del talonario.
NumeroHasta: Número hasta el cual llega la numeración del talonario.
ProximoNumero: Próximo número en la secuencia del talonario.
Renglones: Cantidad de renglones del talonario.
Sucursal: Sucursal asociada al talonario.
TipoFormulario: Tipo de formulario utilizado.
Talonario: Tipo de talonario.
TipoComprobante: Tipo de comprobante (e.g., A, B, C).
Exclusivo: Indica si es exclusivo para cierto uso.
CodigoCaja: Código de caja asociado al talonario.
Manual: Indica si el talonario es manual.
NumeroAutorizacion: Número de autorización del comprobante.
Llave1: Llave primaria del registro.
Llave2: Llave secundaria del registro.
FechaAviso: Fecha de aviso del talonario.
ValorFecha: Valor de la fecha.
DocumentoElectronico: Indica si es un documento electrónico.
MetodoControlDe: Método de control del comprobante.
ImagenTipo: Tipo de imagen.
DestinoDeImpresion: Destino de impresión.
ImportacionDeDatos: Importación de datos.
EnviaPorCorreo: Indica si se envía por correo.
CodigoDocumentoElectronico: Código del documento electrónico.
SucursalDestino: Sucursal destino.
UsaSistemaImpresion: Indica si se usa un sistema de impresión.
RutaPdf: Ruta del archivo PDF.
UtilizaBonoFiscal: Indica si se utiliza bono fiscal.
GuardaCopiaPdf: Indica si se guarda una copia en PDF.
TipoTalonario: Tipo de talonario.
Observaciones: Observaciones adicionales.
NumeracionPreimpresa: Indica si la numeración está preimpresa.
MetodoImpresionComprobantes: Método de impresión de comprobantes.
ConCbuInformado: Indica si se tiene informado el CBU.
Recibo: Indica si es un recibo.
UsaUsb: Indica si se utiliza USB.
ComprobanteCredito: Indica si es un comprobante de crédito.
PublicaComprobanteTangoTiendas: Indica si se publica el comprobante en Tango Tiendas.
MetodoExportacion: ID del método de exportación.
TipoAutorizacion: Tipo de autorización.
IdGVA43TalonarioCAEA: Identificador del talonario CAEA.
UsaDestinoImpresionEnPdf: Indica si se utiliza la impresión de destino en PDF.
```
### Ejemplo de JSON para la API REST basado en `ProveedorDto`
```
{
  "CPostal": "1000",
  "CitiOpera": "Operación Principal",
  "CitiTipo": "Tipo A",
  "ClasSiap": "Categoría 1",
  "Clausula": "Cláusula especial para proveedores",
  "CodProvee": "PROV001",
  "CondCompr": "Contado",
  "CondIVA": "Responsable Inscripto",
  "Contacto": "Juan Pérez",
  "ContFiscal": "SI",
  "Domicilio": "Avenida Siempreviva 123, Piso 5, Oficina A",
  "Email": "juan.pere@empresa.com",
  "FechaAlta": "2023-04-15T10:30:00Z",
  "FechaAnt": "2022-12-31T23:59:59Z",
  "FechaInha": null,
  "FechaVto": "2024-12-31T23:59:59Z",
  "IdExterno": "EXT-12345",
  "IdInterno": "INT-67890",
  "IIL": 0.21,
  "IIS": 0.105,
  "IncIILis": false,
  "IncIVALi": false,
  "IVAL": 0.21,
  "IVAS": 0.105,
  "LetraHabi": "A",
  "LimCredit": 100000,
  "Localidad": "Buenos Aires",
  "MonCteHa": "ARS",
  "NCuit": "20-34567890-9",
  "NIngBrut": "12345678",
  "NIva": "98765432",
  "NomProvee": "Empresa Proveedora S.A.",
  "Observaciones": "Proveedor clave para el proyecto X",
  "Observac2": "Condiciones especiales de pago",
  "Orden": 1,
  "Provincia": "Buenos Aires",
  "RNI": false,
  "SaldoAnt": 1000,
  "SaldoCC": 500,
  "SaldoDoc": 200,
  "SaldoCUnidades": 10,
  "TForm": "Factura A",
  "Telefono1": "11-4444-5555",
  "Telefono2": "11-6666-7777",
  "Tipo": "Proveedor General",
  "TipoDoc": "CUIT",
  "FechaModi": "2023-05-10T15:00:00Z",
  "ExpSaldo": 1500,
  "Exporta": true,
  "NomFant": "Proveedor SA",
  "CodDeposi": "DEP001",
  "CodSector": "SECTOR1",
  "CodGasto": "GASTO1",
  "CodConiva": "CONIVA1",
  "CodCoexe": "COEXE1",
  "ListaXml": "LISTA.XML",
  "TalonarioXml": "TALONARIO.XML",
  "ArtFletes": "FLETE01",
  "ArtSeguro": "SEGURO01",
  "CodComFon": "COMFON01",
  "CodCtaDeb": "CTA_DEBITO",
  "CodCtaFon": "CTA_FONDO",
  "CodOperac": "OP001",
  "ProvElect": true,
  "SucurOri": "SUCURSAL01",
  "InfIVA": "Informacion adicional sobre IVA",
  "CFondoPM": "FONDO_PM",
  "DiasChPM": 30,
  "CFunicaPM": "UNICO_PM",
  "PagoChe": true,
  "EmailDe": "destino@ejemplo.com",
  "HabilPM": true,
  "Web": "https://www.proveedorsa.com",
  "CodRubro": "RUBRO01",
  "CtaPro": "CTA_PROVEEDOR",
  "CtoPro": "CONTRATO_PROVEEDOR",
  "CalcuRet": true,
  "NumAutoma": "AUT001",
  "TasienDeb": 1.2,
  "TasienCre": 0.8,
  "TasienFac": 1.1,
  "CodCPA01": "CPA01_COD",
  "Cbu": "0111222233334444555566",
  "OCObligatoria": true,
  "EmailOp": "operaciones@empresa.com",
  "EmailOC": "ordenescompra@empresa.com",
  "Rg3572EmpresaVinculadaProveedor": "SI",
  "Rg3572TipoOperacionHabitualProveedor": "VENTA",
  "Rg3685TipoOperacionCompras": "COMPRA",
  "Rg3685ComprobanteCompras": "FACTURA",
  "Rg3685GeneraInformacion": true,
  "EditaComprobanteReferenciaFacturaRemito": true,
  "DefectoComprobanteReferenciaFacturaRemito": "FACTURA",
  "EditaComprobanteReferenciaFactura": true,
  "DefectoComprobanteReferenciaFactura": "FACTURA",
  "EditaComprobanteReferenciaRemito": true,
  "DefectoComprobanteReferenciaRemito": "REMITO",
  "IngresaFacturaSinRemitoAsociado": true,
  "IngresaFletePorRenglon": true,
  "MonedaLimiteCreditoCte": "USD",
  "SaldoCCUnidades": 5,
  "SaldoAnteriorUnidades": 12,
  "Observaciones": "Observaciones adicionales",
  "DomicilioComercial": "Avenida Principal 123",
  "TelefonoMovil": "15-1111-2222",
  "PorcDesc": 5,
  "IdCPA01": "CPA01_ID",
  "TextoIB1": "Texto IB1",
  "TextoIB2": "Texto IB2",
  "TextoIB3": "Texto IB3",
  "TextoIB4": "Texto IB4",
  "Texto": "Texto adicional",
  "CBU2": "0111222233334444555567",
  "CBU3": "0111222233334444555568",
  "DescripcionCBU": "Cuenta corriente",
  "DescripcionCBU2": "Cuenta sueldo",
  "DescripcionCBU3": "Cuenta ahorro",
  "ConversorClausulaDiferenciaEstados": true,
  "RowVersion": "AQIDBA==",
  "CamposAdicionales": "{\"ContactoAlternativo\":\"María Gómez\",\"TelefonoMovil\":\"155555555\"}",
  "IdTipoDocumentoGV": "DNI",
  "IdCPA57": "CPA5701",
  "IdGVA151": "GVA15101",
  "IdCategoriaIVACondIVA": "CAT_IVA_1",
  "IdOperacionAFIPRG3685TipoOperacionCompras": "OP_COMPRA",
  "IdTipoComprobanteAFIPRG3685ComprobanteCompras": "FACT_A",
  "IdRG3572TipoOperacionHabitualProveedor": "VENTA_MAYORISTA",
  "IdIVAClasificacionSIAPClasSIAP": "CLAS_SIAP_1",
  "IdSBA01CFondoPM": "FONDO_PM_1",
  "IdSBA01CFunicaPM": "UNICO_PM_1",
  "IdCondicionCompra": "COND_COMPRA_1",
  "IdSucurOri": "SUCURSAL_ORIGEN",
  "CMVigenciaCoeficiente": 1.1,
  "IdSucursalDestino": "SUCURSAL_DESTINO",
  "Habilitado": true
}

Descripción de los Campos 
CPostal: Código postal del proveedor.
CitiOpera: Operación de Citi.
CitiTipo: Tipo de Citi.
ClasSiap: Clasificación SIAP.
Clausula: Cláusula específica.
CodProvee: Código del proveedor.
CondCompr: Condición de compra.
CondIVA: Condición ante el IVA.
Contacto: Persona de contacto del proveedor.
ContFiscal: Control fiscal del proveedor.
Domicilio: Dirección física del proveedor.
Email: Correo electrónico del proveedor.
FechaAlta: Fecha de alta del proveedor.
FechaAnt: Fecha anterior registrada.
FechaInha: Fecha de inhabilitación del proveedor.
FechaVto: Fecha de vencimiento.
IdExterno: Identificador externo del proveedor.
IdInterno: Identificador interno del proveedor.
IIL: Impuesto Interno Libre.
IIS: Impuesto Interno Sobre.
IncIILis: Inclusión en lista de Impuesto Interno Libre.
IncIVALi: Inclusión en lista de IVA Libre.
IVAL: IVA Libre.
IVAS: IVA Sobre.
LetraHabi: Letra habilitada para el proveedor.
LimCredit: Límite de crédito asignado al proveedor.
Localidad: Localidad del proveedor.
MonCteHa: Moneda de cuenta habilitada.
NCuit: Número de CUIT del proveedor.
NIngBrut: Número de ingresos brutos.
NIva: Número de IVA.
NomProvee: Nombre del proveedor.
Observacio: Observaciones adicionales.
Observac2: Segunda observación adicional.
Orden: Orden del proveedor.
Provincia: Provincia donde se ubica el proveedor.
RNI: Responsable no inscripto.
SaldoAnt: Saldo anterior.
SaldoCC: Saldo en cuenta corriente.
SaldoDoc: Saldo del documento.
SaldoCUnidades: Saldo en unidades.
TForm: Tipo de formulario utilizado.
Telefono1: Primer número de teléfono.
Telefono2: Segundo número de teléfono.
Tipo: Tipo de proveedor.
TipoDoc: Tipo de documento del proveedor.
FechaModi: Fecha de la última modificación.
ExpSaldo: Saldo exportado.
Exporta: Indica si el proveedor exporta.
NomFant: Nombre de fantasía del proveedor.
CodDeposi: Código del depósito asociado.
CodSector: Código del sector del proveedor.
CodGasto: Código de gasto asociado al proveedor.
CodConiva: Código de condición frente al IVA.
CodCoexe: Código de condición de exención.
ListaXml: Lista XML asociada al proveedor.
TalonarioXml: Talonario XML asociado.
ArtFletes: Artículo de fletes asociado.
ArtSeguro: Artículo de seguro asociado.
CodComFon: Código de comisión de fondo.
CodCtaDeb: Código de cuenta de débito.
CodCtaFon: Código de cuenta de fondo.
CodOperac: Código de operación del proveedor.
ProvElect: Indica si es un proveedor electrónico.
SucurOri: Sucursal de origen.
InfIVA: Información del IVA.
CFondoPM: Código de fondo para PM.
DiasChPM: Días de cheque para PM.
CFunicaPM: Código único para PM.
PagoChe: Pago con cheque.
EmailDe: Email de destino.
HabilPM: Indica si está habilitado para PM.
Web: Sitio web del proveedor.
CodRubro: Código de rubro del proveedor.
CtaPro: Cuenta del proveedor.
CtoPro: Contrato del proveedor.
CalcuRet: Indica si se calcula retención.
NumAutoma: Número automático.
TasienDeb: Tasa de asiento de débito.
TasienCre: Tasa de asiento de crédito.
TasienFac: Tasa de asiento de factura.
CodCPA01: Código CPA01.
Cbu: Clave Bancaria Uniforme del proveedor.
OCObligatoria: Indica si la orden de compra es obligatoria.
EmailOp: Email de operación.
EmailOC: Email para orden de compra.
Rg3572EmpresaVinculadaProveedor: Empresa vinculada al proveedor según RG 3572.
Rg3572TipoOperacionHabitualProveedor: Tipo de operación habitual del proveedor según RG 3572.
Rg3685TipoOperacionCompras: Tipo de operación de compras según RG 3685.
Rg3685ComprobanteCompras: Comprobante de compras según RG 3685.
Rg3685GeneraInformacion: Indica si se genera información según RG 3685.
EditaComprobanteReferenciaFacturaRemito: Indica si se puede editar el comprobante de referencia factura/remito.
DefectoComprobanteReferenciaFacturaRemito: Indica el defecto en el comprobante de referencia factura/remito.
EditaComprobanteReferenciaFactura: Indica si se puede editar el comprobante de referencia factura.
DefectoComprobanteReferenciaFactura: Indica el defecto en el comprobante de referencia factura.
EditaComprobanteReferenciaRemito: Indica si se puede editar el comprobante de referencia remito.
DefectoComprobanteReferenciaRemito: Indica el defecto en el comprobante de referencia remito.
IngresaFacturaSinRemitoAsociado: Indica si se puede ingresar una factura sin remito asociado.
IngresaFletePorRenglon: Indica si se ingresa flete por renglón.
MonedaLimiteCreditoCte: Moneda límite de crédito en cuenta corriente.
SaldoCCUnidades: Saldo en unidades en cuenta corriente.
SaldoAnteriorUnidades: Saldo anterior en unidades.
Observaciones: Observaciones adicionales.
DomicilioComercial: Domicilio comercial del proveedor.
TelefonoMovil: Número de teléfono móvil.
PorcDesc: Porcentaje de descuento.
IdCPA01: Identificador CPA01.
TextoIB1: Texto adicional de Ingresos Brutos 1.
TextoIB2: Texto adicional de Ingresos Brutos 2.
TextoIB3: Texto adicional de Ingresos Brutos 3.
TextoIB4: Texto adicional de Ingresos Brutos 4.
Texto: Texto adicional.
Cbu2: Segunda Clave Bancaria Uniforme del proveedor.
Cbu3: Tercera Clave Bancaria Uniforme del proveedor.
DescripcionCbu: Descripción del CBU.
DescripcionCbu2: Descripción del CBU 2.
DescripcionCbu3: Descripción del CBU 3.
ConversorClausulaDiferenciaEstados: Conversor de cláusula para diferencia de estados.
RowVersion: Versión de la fila.
CamposAdicionales: Campos adicionales del proveedor.
IdTipoDocumentoGV: Identificador del tipo de documento GV.
IdCPA57: Identificador CPA57.
IdGVA151: Identificador de la tabla GVA151.
IdCategoriaIVACondIVA: Identificador de la categoría de IVA y condición de IVA.
IdOperacionAFIPRG3685TipoOperacionCompras: Identificador de operación AFIP RG3685.
IdTipoComprobanteAFIPRG3685ComprobanteCompras: Identificador de tipo de comprobante AFIP RG3685.
IdRG3572TipoOperacionHabitualProveedor: Identificador de operación habitual RG3572.
IdIVAClasificacionSIAPClasSIAP: Identificador de clasificación SIAP.
IdSBA01CFondoPM: Identificador de fondo PM.
IdSBA01CFunicaPM: Identificador único PM.
IdCondicionCompra: Identificador de condición de compra.
IdSucurOri: Identificador de la sucursal de origen.
CMVigenciaCoeficiente: Coeficiente de vigencia.
IdSucursalDestino: Identificador de la sucursal de destino.
Habilitado: Indica si el proveedor está habilitado.
```

