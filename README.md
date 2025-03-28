<a name="inicio"></a>
Arison WMS | TMS - API REST Integración
=======

- [Generalidades](#generalidades)
  - [Antes de empezar](#AntesDeEmpezar)
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
- [Datos JSON](#datosjson)
  - [ArticuloDto](#ArticuloDto)
  - [ClienteDto](#ClienteDto)
  - [CondicionDeVentaDto](#CondicionDeVentaDto)
  - [CotizacionDto](#CotizacionDto)
  - [DepositoDto](#DepositoDto)
  - [EscalaDto](#EscalaDto)
  - [ListaDePreciosDto](#ListaDePreciosDto)
  - [MonedaDto](#MonedaDto)
  - [MovimientoStockDto](#MovimientoStockDto)
  - [OrdenesDeCompraEncabezadosDto](#OrdenesDeCompraEncabezadosDto)
  - [OrdenesDeCompraRenglonesDto](#OrdenesDeCompraRenglonesDto)
  - [ProveedorDto](#ProveedorDto)
  - [RequerimientoVentaDto](#RequerimientoVentaDto)
  - [TalonariosDeOrdenesDto](#TalonariosDeOrdenesDto)
  - [TalonariosDeVentasDto](#TalonariosDeVentasDto)
  - [TransporteDto](#TransporteDto)
  - [ValoresEscalaDto](#ValoresEscalaDto)
  - [VendedoresDto](#VendedoresDto)
- [Requerimientos de Hardware](#requerimientoshardware)
  - [Servidor](#Servidor)
  - [Estación de trabajo](#Cliente)
  - [Dispositivos Móviles](#Moviles)
    - [Colectoras de datos](#Colectoras)
    - [Celulares](#Celulares)
    - [Lectoras](#Lectoras)
    
    

<a name="generalidades"></a>

## Generalidades

<a name="AntesDeEmpezar"></a>
### Antes de empezar
Arison se integra fácilmente a cualquier sistema preexistente, ya sea por medio de nuestra API Rest, o cualquier otro método de integración, como importación de datos desde .CSV, .XML, .TXT, .XLS, intercambios por FTP, SQL Server, y muchos otros más.  
En el presente documento se listarán los métodos estándar de nuestra API Rest.  
Para conocer todas las posibilidades, no dude en contactarnos a info@arison.ar.

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

### Ejemplo de JSON para la API REST basado en `ClienteDto`

```json
{
  "CodigoCliente": "CLI001",
  "RazonSocial": "Cliente Ejemplo",
  "GenerarPasswordEntrega": 1,
  "Clase": "A",
  "TipoCliente": "DISTRIBUIDOR",
  "TiempoDescarga": 30,
  "Empresa": "E",
  "CPostal": "1234",
  "NCuit": "30-12345678-9",
  "Domicilio": "Dirección Ejemplo",
  "Email": "cliente@ejemplo.com",
  "Localidad": "Localidad Ejemplo",
  "Observacion": "Observación Ejemplo",
  "Habilitado": 1,
  "CodZona": "Z1",
  "CodProvincia": "BA",
  "CodVendedor": "V1",
  "CodTransporte": "TRA001",
  "CondVenta": "CC",
  "Filler1": "Filler1 Ejemplo",
  "Filler2": 123.45,
  "PorcBonif": 10.25
}
CodigoCliente: Código identificatorio del cliente (Obligatorio). Caracteres permitidos: 6. Tipo Texto.
RazonSocial: Razón social el cliente. Caracteres permitidos: 60. Tipo Texto.
GenerarPasswordEntrega: Generar código de entrega (Uso en módulo ruteador). Valores permitidos: Enteros positivos. Ejemplo: 1
Clase: Clase del cliente. Caracteres permitidos: 15. Tipo Texto.
TipoCliente: Categorización del cliente. Ejemplo: DISTRIBUIDOR, INDUSTRIA, COMERCIO. Caracteres permitidos: 15. Tipo Texto.
TiempoDescarga: Tiempo en minutos de descarga de entregas del cliente. Ejemplo: 2 minutos (Uso en módulo ruteador). Valores permitidos: Enteros positivos. Ejemplo: 1
Empresa: Empresa. (OBLIGATORIO). Caracteres permitidos: 1. Tipo Texto.
CPostal: Código postal del cliente. Caracteres permitidos: 8. Tipo Texto.
NCuit: CUIT o documento identificatorio del cliente. Caracteres permitidos: 20. Tipo Texto.
Domicilio: Domicilio del cliente. Caracteres permitidos: 30. Tipo Texto.
Email: Correo electrónico del cliente. Caracteres permitidos: 255. Tipo Texto.
Localidad: Localidad del cliente. Caracteres permitidos: 20. Tipo Texto.
Observacion: Observaciones adicionales. Caracteres permitidos: 60. Tipo Texto.
Habilitado: Indica si el cliente está habilitado. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
CodZona: Código de Zona. Caracteres permitidos: 2. Tipo Texto.
CodProvincia: Código de Provincia del cliente. Caracteres permitidos: 2. Tipo Texto.
CodVendedor: Código del vendedor. Caracteres permitidos: 2. Tipo Texto.
CodTransporte: Código del camión/transporte. Caracteres permitidos: 10. Tipo Texto.
CondVenta: Condición de venta del cliente. Caracteres permitidos: 2. Tipo Texto.
Filler1: Campo de uso interno.
Filler2: Campo de uso interno.
PorcBonif: Porentaje de bonificación. Valores permitidos: Decimal positivo con hasta 2 decimales | Ejemplo: 10.25
```

[<sub>Volver</sub>](#inicio)

<a name="ArticuloDto"></a>

### Ejemplo de JSON para la API REST basado en `ArticuloDto`


```json
{
  "CodigoArticulo": "123 ALE00",
  "Descripcion": "Descripción Ejemplo",
  "DescripcionAdicional": "Descripción Adicional Ejemplo",
  "Equivalencia": 50.500000,
  "Perfil": "A",
  "PtoPedido": 25.250000,
  "Sinonimo": "Sinónimo Ejemplo",
  "Stock": 1,
  "UsaPartida": 0,
  "Usuario": "Usuario Ejemplo",
  "Terminal": "Terminal Ejemplo",
  "Observaciones": "Observaciones Ejemplo",
  "CodigoBarra": "1234567890123",
  "IdMedidaStock": 4,
  "DescargaNegativoStock": 1,
  "Base": "Base Ejemplo",
  "UsaSerie": 0,
  "UsaScrap": 1,
  "UsaEsc": 0,
  "Virtual": 1,
  "GenOf": 1,
  "Profundidad": 10.0025,
  "Altura": 10.0025,
  "Ancho": 10.0025,
  "CodigoDeposito": "FF",
  "DepositoOrigen": "AA",
  "Observacio": "Observación Ejemplo",
  "Comercial": 1,
  "Filler1": "Filler1 Ejemplo",
  "Filler2": 123.456,
  "DiasVto": 30,
  "PeEspec": 2.500000,
  "DepCalida": "CC",
  "EstadoEla": "ELA",
  "EstadoVta": "VTA",
  "CoefRendi": 1.250000,
  "PermiteSobreVenta": 0,
  "DiasPreparacion": 7,
  "DepositoProveedor": "PP",
  "CodigoZona": 1,
  "Peso": 5.000000,
  "IdMedidaPeso": 2,
  "Volumen": 0.500000,
  "IdMedidaVolumen": 3,
  "DiasAlVencimiento": 60,
  "Rnpa": "RNPA Ejemplo",
  "CamposAdicionales": "{}"
}
Documentación de los campos del DTO ArticuloDto:

CodigoArticulo: Código del artículo. (OBLIGATORIO). Caracteres permitidos: 15. Ejemplo "123 ALE00".
Descripcion: Descripción principal del artículo. Caracteres permitidos: 30. Ejemplo "Movimiento de stock".
DescripcionAdicional: Descripción adicional del artículo. Caracteres permitidos: 20. Ejemplo "Movimiento de stock".
Equivalencia: Equivalencia del artículo. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 50.500000
Perfil: Tipo de artículo. Caracteres permitidos: 1 | C: Compra, V: Venta, A: Ambos, N: Inhabilitado
PtoPedido: Cantidad en la que se dispara un requerimiento de producción o compras. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 50.500000
Sinonimo: Sinónimo para identificar el artículo. Caracteres permitidos: 15. Tipo Texto
Stock: Permite stock. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
UsaPartida: Utiliza partida. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
Usuario: Usuario que da el alta a el artículo.(OBLIGATORIO). Caracteres permitidos: 120. Tipo Texto
Terminal: Terminal/Dispositivo.(OBLIGATORIO). Caracteres permitidos: 255. Tipo Texto
Observaciones: Observaciones adicionales. Caracteres permitidos: 255. Tipo Texto
CodigoBarra: Código de barra del articulo. Caracteres permitidos: 25. Tipo Texto
IdMedidaStock: Id de Medida (Ejemplo: Kg(4), Sin Medida(0)). (OBLIGATORIO). Valores permitidos: Enteros positivos. Ejemplo: 1
DescargaNegativoStock: Permite Descarga negativa en stock. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
Base: Código base del artículo. Caracteres permitidos: 15. Tipo Texto
UsaSerie: Utiliza serie. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
UsaScrap: Utiliza scrap . Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
UsaEsc: Utiliza escalar. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
Virtual: Permite virtual (OBLIGATORIO). Valores permitidos: Entero Ejemplo: 1 | 0
GenOf: Permite Generar Orden de Trabajo. (OBLIGATORIO). Valores permitidos: Entero Ejemplo: 1 | 0
Profundidad: Longitud expresada en mm. (OBLIGATORIO). Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
Altura: Altura. (OBLIGATORIO). Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
Ancho: Ancho. (OBLIGATORIO). Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
CodigoDeposito: Código Depósito. Caracteres permitidos: 2. Tipo Texto
DepositoOrigen: Depósito Origen. Caracteres permitidos: 2. Tipo Texto
Observacio: Observaciones. Caracteres permitidos: 255. Tipo Texto
Comercial: Permite Comercial. (OBLIGATORIO). Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
Filler1: campo de uso interno.Texto (OBLIGATORIO)
Filler2: campo de uso interno.Decimal (OBLIGATORIO)
DiasVto: Días Vencimiento.(OBLIGATORIO). Valores permitidos: Enteros positivos. Ejemplo: 1
PeEspec: Peso específico. (OBLIGATORIO). Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
DepCalida: Depósito Calidad. (OBLIGATORIO). Caracteres permitidos: 2. Tipo Texto
EstadoEla: EstadoEla. (OBLIGATORIO). Caracteres permitidos: 3. Tipo Texto
EstadoVta: Estado Venta. (OBLIGATORIO). Caracteres permitidos: 3. Tipo Texto
CoefRendi: Coeficiente Rendimiento ?. (OBLIGATORIO) Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
PermiteSobreVenta: Permite stock negativo del artículo. Valores permitidos: Entero Ejemplo: 1:Sí | 0:No
DiasPreparacion: Días de preparación del artículo. Valores permitidos: Enteros positivos. Ejemplo: 1
DepositoProveedor: Depósito Proveedor. Caracteres permitidos: 2. Tipo Texto
CodigoZona: Código de zona donde se guarda el artículo. Valores permitidos: Enteros positivos. Ejemplo: 1
Peso: Peso del artículo. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
IdMedidaPeso: Id de la medida del peso del artículo. Valores permitidos: Enteros positivos. Ejemplo: 1
Volumen: Volumen del artículo. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025
IdMedidaVolumen: Id de la medida del volumen del artículo. Valores permitidos: Enteros positivos. Ejemplo: 1
DiasAlVencimiento: Días hasta el vencimiento del artículo. Valores permitidos: Enteros positivos. Ejemplo: 1
Rnpa: Certificado Registro Nacional de Productos Alimenticios. Caracteres permitidos: 100. Tipo Texto.
CamposAdicionales: Campos adicionales al producto como escala (Formato JSON). Caracteres permitidos: 255. Tipo Texto.
```

[<sub>Volver</sub>](#inicio)

<a name= "CondicionDeVentaDto"></a>
## Ejemplo de Json basado en `CondicionDeVentaDto`

```json
{
  "CondVta": 1,
  "Filler": "Valor de relleno",
  "DescCond": "Descripción de la condición de venta",
  "NroDeList": 1,
  "Observaciones": "Observaciones de la condición de venta",
  "GeneraFechasAlternativas": "S",
  "FechaVigDesde": "2024-03-15T00:00:00",
  "FechaVigHasta": "2024-12-31T23:59:59"
}

CondVta: Identificador condición de venta. Valores permitidos: Enteros positivos. Ejemplo: 1.
Filler: Campo de uso interno. Texto (OBLIGATORIO).
DescCond: Descripción Condición de venta. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Contado".
NroDeList: Número de lista de condición de venta. Valores permitidos: Enteros positivos. Ejemplo: 1.
Observaciones: Observaciones. Caracteres permitidos: 255. Tipo Texto. Ejemplo: "Condición especial para clientes mayoristas".
GeneraFechasAlternativas: Genera fechas alternativas para condición de ventas. Caracteres permitidos: 1. Tipo Texto. Ejemplo: "S".
FechaVigDesde: Fecha vigente desde. Ejemplo: "2024-01-01T00:00:00".
FechaVigHasta: Fecha vigente hasta. Ejemplo: "2024-12-31T23:59:59".
```
[<sub>Volver</sub>](#inicio)

<a name= "CotizacionDto"></a>
## Ejemplo de Json basado en `CotizacionDto`
```json
{
  "IdMoneda": 1,
  "FechaHora": "2024-03-15T10:30:00",
  "Cotizacion": 120.50
}

IdMoneda: Identificador de moneda. Valores permitidos: Enteros positivos. Ejemplo: 1. (OBLIGATORIO)
FechaHora: Fecha y Hora de cotización. Ejemplo: "2024-03-15T10:30:00".
Cotizacion: Precio cotización. Valores permitidos: Decimal positivo con hasta 6 decimales. Ejemplo: 120.50.
```
[<sub>Volver</sub>](#inicio)

<a name= "EscalaDto"></a>
## Ejemplo de Json basado en `EscalaDto`
```json
{
  "CodEscala": "A1",
  "Descripcion": "Escala de precios mayoristas",
  "NroEscala": 1,
  "Observaciones": "Esta escala aplica para clientes con volumen de compra superior a 100 unidades."
}

CodEscala: Código identificatorio de la Escala (Obligatorio). Caracteres permitidos: 2. Tipo Texto. Ejemplo: "A1".
Descripcion: Descripción de la escala. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Escala de precios minoristas".
NroEscala: Número de escala. Valores permitidos: Enteros positivos. Ejemplo: 1.
Observaciones: Observaciones adicionales. Caracteres permitidos: 1000. Tipo Texto. Ejemplo: "Aplica para todos los productos de la categoría X.".
```
[<sub>Volver</sub>](#inicio)

<a name= "ListaDePreciosDto"></a>
## Ejemplo de Json basado en `ListaDePreciosDto`
```json
{
  "Filler": "Valor de relleno",
  "Decimales": 2,
  "FechaDesde": "2024-01-01T00:00:00",
  "FechaHasta": "2024-12-31T23:59:59",
  "Habilitada": 1,
  "IncluyeImp": 0,
  "IncluyeIva": 1,
  "MonCte": 1,
  "NombreList": "Lista Mayorista",
  "NroList": 1,
  "Observacion": "Lista de precios para clientes mayoristas con descuentos especiales."
}

Filler: Campo de uso interno. Texto.
Decimales: Cantidad de decimales. Valores permitidos: Enteros positivos. Ejemplo: 2.
FechaDesde: Fecha vigente de lista de precio Desde. Ejemplo: "2024-01-01T00:00:00".
FechaHasta: Fecha vigente de lista de precio Hasta. Ejemplo: "2024-12-31T23:59:59".
Habilitada: Lista de precios habilitada. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
IncluyeImp: Incluye impuesto. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
IncluyeIva: Incluye IVA. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
MonCte: Utiliza moneda corriente. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
NombreList: Descripción de lista de precios. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Lista Minorista".
NroList: Número identificador de lista. (OBLIGATORIO). Valores permitidos: Enteros positivos. Ejemplo: 1.
Observacion: Observaciones adicionales. Caracteres permitidos: -. Tipo Texto. Ejemplo: "Lista de precios para ventas al público en general.".
```
[<sub>Volver</sub>](#inicio)

<a name= "MonedaDto"></a>
## Ejemplo de Json basado en `MonedaDto`
```json
{
  "IdMoneda": 1,
  "CodMoneda": "USD",
  "DescMoneda": "Dólar Estadounidense",
  "SimboloMoneda": "$",
  "TipoMoneda": "Extranjera",
  "CantDecMoneda": 2,
  "Observaciones": "Moneda utilizada para transacciones internacionales."
}

IdMoneda: Identificador de tabla moneda. Valores permitidos: Enteros positivos. Ejemplo: 1.
CodMoneda: Código de moneda. (OBLIGATORIO). Caracteres permitidos: -. Tipo Texto. Ejemplo: "USD".
DescMoneda: Descripción de moneda. Caracteres permitidos: -. Tipo Texto. Ejemplo: "Dólar Estadounidense".
SimboloMoneda: Símbolo de moneda. (OBLIGATORIO). Caracteres permitidos: 3. Tipo Texto. Ejemplo: "$".
TipoMoneda: Tipo de moneda. Caracteres permitidos: -. Tipo Texto. Ejemplo: "Extranjera".
CantDecMoneda: Cantidad de decimales en moneda. Valores permitidos: Enteros positivos. Ejemplo: 2.
Observaciones: Observaciones adicionales. Caracteres permitidos: 1000. Tipo Texto. Ejemplo: "Moneda utilizada para transacciones internacionales.".
```
[<sub>Volver</sub>](#inicio)

<a name= "OrdenesDeCompraEncabezadosDto"></a>
## Ejemplo de Json basado en `OrdenesDeCompraEncabezadosDto`
```json
{
  "Id_OrdenCompra": 1,
  "Filler": "Valor de relleno",
  "CodProveedor": "PROV01",
  "Talonario": 1,
  "NroOrdenCompra": "OC-20240315-001",
  "FechaGen": "2024-03-15T10:00:00",
  "FechaVig": "2024-03-31T23:59:59",
  "Leyenda1": "Entrega en 7 días",
  "Leyenda2": "Pago a 30 días",
  "Leyenda3": "Descuento del 5%",
  "Leyenda4": "",
  "Leyenda5": "",
  "Observaciones": "Orden de compra para repuestos de maquinaria.",
  "Cierre": 0,
  "Cumplido": 0
}

Id_OrdenCompra: Identificador de la orden de compra. (OBLIGATORIO). Valores permitidos: Enteros positivos. Ejemplo: 1.
Filler: Campo de uso interno. Texto.
CodProveedor: Código de proveedor. (OBLIGATORIO). Caracteres permitidos: 6. Tipo Texto. Ejemplo: "PROV01".
Talonario: Número talonario. Valores permitidos: Enteros positivos. Ejemplo: 1.
NroOrdenCompra: Número orden de compra. (OBLIGATORIO). Caracteres permitidos: 14. Tipo Texto. Ejemplo: "OC-20240315-001".
FechaGen: Fecha de creación de orden de compra. Ejemplo: "2024-03-15T10:00:00".
FechaVig: Fecha vigente de orden de compra. Ejemplo: "2024-03-31T23:59:59".
Leyenda1: Comentarios / Leyenda. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Entrega urgente".
Leyenda2: Comentarios / Leyenda. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Pago con cheque".
Leyenda3: Comentarios / Leyenda. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Sin cargo de envío".
Leyenda4: Comentarios / Leyenda. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "".
Leyenda5: Comentarios / Leyenda. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "".
Observaciones: Observaciones de orden de compra. Caracteres permitidos: -. Tipo Texto. Ejemplo: "Orden de compra para materiales de construcción.".
Cierre: Orden en estado cerrada. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
Cumplido: Orden en estado cumplida. Valores permitidos: Entero. Ejemplo: 1: Sí | 0: No.
```
[<sub>Volver</sub>](#inicio)

<a name= "OrdenesDeCompraRenglonesDto"></a>
## Ejemplo de Json basado en `OrdenesDeCompraRenglonesDto`
```json
{
  "IdOcRenglones": 1,
  "IdOcEncabezado": 1,
  "Talonario": 1,
  "NroOrdenCo": "OC-20240315-001",
  "NroRenglonOc": 1,
  "Filler": "Valor de relleno",
  "CodDeposi": "DP",
  "CodArticu": "ART001",
  "CantPedida": 10.50,
  "CantPendiente": 10.50,
  "CantRecibida": 0.00,
  "Cierre": 0
}

IdOcRenglones: Identificador de renglones ordenes de compra. (OBLIGATORIO). Valores permitidos: Enteros positivos. Ejemplo: 1.
IdOcEncabezado: Identificador del encabezado de ordenes de compra. Valores permitidos: Enteros positivos. Ejemplo: 1.
Talonario: Número talonario. Valores permitidos: Enteros positivos. Ejemplo: 1.
NroOrdenCo: Número orden de compra. (OBLIGATORIO). Caracteres permitidos: 14. Tipo Texto. Ejemplo: "OC-20240315-001".
NroRenglonOc: Número de renglón de orden de compra. Valores permitidos: Enteros positivos. Ejemplo: 1.
Filler: Comentarios.
CodDeposi: Código de depósito para orden de compra. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "DP".
CodArticu: Código de artículo para orden de compra. Caracteres permitidos: 15. Tipo Texto. Ejemplo: "ART001".
CantPedida: Cantidad de stock solicitada para orden de compra. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
CantPendiente: Cantidad pendiente por cumplir de cantidad pedida de la orden. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
CantRecibida: Cantidad real recibida de la orden de compra. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
Cierre: Aplica cierre de orden de compra. Valores permitidos: Entero Ejemplo: 1: Sí | 0: No.
```
[<sub>Volver</sub>](#inicio)

<a name= "RequerimientoVentaDto"></a>
## Ejemplo de Json basado en `RequerimientoVentaDto`
```json
{
  "Empresa": "M",
  "CodCd": "CD",
  "CodDeposito": "DP",
  "IdTabla": 1,
  "TablaOrigen": "PED",
  "CodEstado": 1,
  "Estado": "Pendiente",
  "CantPedid": 10.50,
  "CantADes": 10.50,
  "CantPenD": 0.00,
  "CodArticu": "ART001",
  "NRenglon": 1,
  "NroPedido": "PED-20240315-001",
  "TalonPed": 1,
  "CodRequisisor": "CLI001",
  "NombreRequisisor": "Cliente Ejemplo",
  "FechaPedi": "2024-03-15T10:00:00",
  "FechaEntr": "2024-03-20T10:00:00",
  "FechaApru": null,
  "Clase": "A",
  "Descripcion": "Artículo Ejemplo",
  "DescAdic": "Descripción adicional",
  "DescCond": "Condición de venta",
  "Transporte": "Transporte Ejemplo",
  "Localidad": "Localidad Ejemplo",
  "Direccion": "Dirección Ejemplo",
  "Provincia": "Provincia Ejemplo",
  "Leyenda1": "Leyenda 1",
  "Leyenda2": "Leyenda 2",
  "Leyenda3": "Leyenda 3",
  "Leyenda4": "Leyenda 4",
  "Leyenda5": "Leyenda 5",
  "TipoCliente": "FINAL",
  "Vendedor": "Vendedor Ejemplo",
  "UnidadMedidaSeleccionada": "U",
  "EquivaleV": 1.00,
  "TCompAsoc": "FAC",
  "NCompAsoc": "FAC-20240315-001",
  "Precio": 100.00,
  "MonCte": 1,
  "CodTransp": "TRA001",
  "IdDireccionEntrega": 1,
  "DepoProveedor": "DP",
  "Comentario": "Comentario adicional",
  "NroOComp": "OC-20240315-001",
  "TotalPed": 105.00,
  "IdUsuario": 1,
  "Terminal": "Terminal Ejemplo",
  "CodVended": "VEND001",
  "CondVenta": 1,
  "NLista": 1
}

IdRequerimientoDeVenta: Identificador de requerimiento. Valores permitidos: Enteros positivos. Ejemplo: 1.
Empresa: 'M' para db maestra / 'B' para db alternativa. Caracteres permitidos: 1. Tipo Texto. Ejemplo: "M".
CodCd: Centro de distribución que atenderá la demanda. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "CD".
CodDeposito: Código de depósito seleccionado para abastecer la demanda. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "DP".
IdTabla: Identificador único de la tabla de origen. Valores permitidos: Enteros positivos. Ejemplo: 1.
TablaOrigen: Nombre de la tabla de origen. Caracteres permitidos: 5. Tipo Texto. Ejemplo: "PED".
CodEstado: Código que representa el estado del pedido. Valores permitidos: Enteros positivos. Ejemplo: 1.
Estado: Descripción del estado del pedido. Caracteres permitidos: 11. Tipo Texto. Ejemplo: "Pendiente".
CantPedid: Cantidad pedida originalmente en el pedido. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
CantADes: Cantidad habilitada para recolectarse. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
CantPenD: Cantidad no remitida aún. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
CodArticu: Código único del artículo solicitado. Caracteres permitidos: 15. Tipo Texto. Ejemplo: "ART001".
NRenglon: Número del renglón del requerimiento dentro del pedido. Valores permitidos: Enteros positivos. Ejemplo: 1.
NroPedido: Número de identificación del pedido. Caracteres permitidos: 14. Tipo Texto. Ejemplo: "PED-20240315-001".
TalonPed: Código del talonario asociado al pedido. Valores permitidos: Enteros positivos. Ejemplo: 1.
CodRequisisor: Código del cliente o requisitor que solicitó el pedido. Caracteres permitidos: 6. Tipo Texto. Ejemplo: "CLI001".
NombreRequisisor: Nombre de cliente/requisisor. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Cliente Ejemplo".
FechaPedi: Fecha de ingreso del pedido. Ejemplo: "2024-03-15T10:00:00".
FechaEntr: Fecha solicitada para la entrega del pedido. Ejemplo: "2024-03-20T10:00:00".
FechaApru: Fecha de aprobación del pedido (puede ser nula). Ejemplo: null.
Clase: Categoría de cliente (A,B,C). Caracteres permitidos: 1. Tipo Texto. Ejemplo: "A".
Descripcion: Descripción del artículo solicitado. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Artículo Ejemplo".
DescAdic: Descripción adicional del artículo. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Descripción adicional".
DescCond: Descripción de la condición de venta (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Condición de venta".
Transporte: Datos de la entrega. Nombre del transporte (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Transporte Ejemplo".
Localidad: Datos de la entrega. Localidad de la dirección (OBLIGATORIO remisión). Caracteres permitidos: 100. Tipo Texto. Ejemplo: "Localidad Ejemplo".
Direccion: Datos de la entrega. Dirección de entrega (OBLIGATORIO remisión). Caracteres permitidos: 200. Tipo Texto. Ejemplo: "Dirección Ejemplo".
Provincia: Datos de la entrega. Provincia de la dirección de entrega (OBLIGATORIO remisión). Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Provincia Ejemplo".
Leyenda1: Primera leyendas a imprimir (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Leyenda 1".
Leyenda2: Segunda leyendas a imprimir (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Leyenda 2".
Leyenda3: Tercera leyendas a imprimir (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Leyenda 3".
Leyenda4: Cuarta leyendas a imprimir (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Leyenda 4".
Leyenda5: Quinta leyendas a imprimir (OBLIGATORIO remisión). Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Leyenda 5".
TipoCliente: Categorización del cliente (FINAL, FRANQUICIA, DISTRIBUIDOR, etc.). Caracteres permitidos: 18. Tipo Texto. Ejemplo: "FINAL".
Vendedor: Nombre del vendedor asociado al pedido. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Vendedor Ejemplo".
UnidadMedidaSeleccionada: Unidad de medida utilizada para expresar la cantidad del artículo. Caracteres permitidos: 1 (V/S). Tipo Texto. Ejemplo: "U".
EquivaleV: Equivalencia entre unidades de medida y bultos. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
TCompAsoc: Tipo de comprobante asociado al pedido. Caracteres permitidos: 3. Tipo Texto. Ejemplo: "FAC".
NCompAsoc: Número de comprobante asociado. Caracteres permitidos: 13. Tipo Texto. Ejemplo: "FAC-20240315-001".
Precio: Precio unitario del artículo (puede ser nulo). Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
MonCte: Moneda corriente utilizada en el pedido. Valores permitidos: Enteros positivos. Ejemplo: 1.
CodTransp: Datos de la entrega. Código del transporte (OBLIGATORIO remisión). Caracteres permitidos: 10. Tipo Texto. Ejemplo: "TRA001".
IdDireccionEntrega: Identificador único de la dirección de entrega (OBLIGATORIO para remisión). Ejemplo: 1.
DepoProveedor: Código del depósito que abastece la demanda. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "DP".
Comentario: Comentario adicional. Caracteres permitidos: 100. Tipo Texto. Ejemplo: "Comentario adicional".
NroOComp: ????????. Caracteres permitidos: 14. Tipo Texto. Ejemplo: "OC-20240315-001".
TotalPed: Cantidad total solicitada. Valores permitidos: Decimal positivo con hasta 6 decimales | Ejemplo: 10.0025.
IdUsuario: Identificador de usuario. Valores permitidos: Enteros positivos. Ejemplo: 1.
Terminal: Dispositivo logueado. Caracteres permitidos: 100. Tipo Texto. Ejemplo: "Terminal Ejemplo".
CodVended: Código del vendedor. Ejemplo: "VEND001".
CondVenta: Condición de venta. Valores permitidos: Enteros positivos. Ejemplo: 1.
NLista: Número de lista. Valores permitidos: Enteros positivos. Ejemplo: 1.
```
[<sub>Volver</sub>](#inicio)

<a name= "TalonariosDeOrdenesDto"></a>
## Ejemplo de Json basado en `TalonariosDeOrdenesDto`
```json
{
  "NroTalonario": 1,
  "DescTalonario": "Talonario Ejemplo",
  "Tipo": "TA",
  "CodComp": "FAC",
  "NroSuc": 1,
  "PrNroHab": 1,
  "UlNroHab": 100,
  "PrxNroUt": 2,
  "IdUsuario": 1,
  "Filler1": "Filler Ejemplo",
  "Filler2": 123.456,
  "MonCte": 1,
  "CodMoneda": "ARS"
}

NroTalonario: Número del talonario. Valores permitidos: Enteros positivos. Ejemplo: 1.
DescTalonario: Descripción del talonario. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Talonario Ejemplo".
Tipo: Tipo de talonario. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "TA".
CodComp: Código de comprobante. Caracteres permitidos: 3. Tipo Texto. Ejemplo: "FAC".
NroSuc: Número de sucursal. Valores permitidos: Enteros positivos. Ejemplo: 1.
PrNroHab: Primer número habilitado. Valores permitidos: Enteros positivos. Ejemplo: 1.
UlNroHab: Último número habilitado. Valores permitidos: Enteros positivos. Ejemplo: 100.
PrxNroUt: Próximo número habilitado. Valores permitidos: Enteros positivos. Ejemplo: 2.
IdUsuario: Identificador de usuario. Valores permitidos: Enteros positivos. Ejemplo: 1.
Filler1: Campo de uso interno. Tipo texto.
Filler2: Campo de uso interno. Tipo Decimal.
MonCte: Moneda corriente. Valores permitidos: Enteros positivos. Ejemplo: 1.
CodMoneda: Código de moneda. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "ARS".

```
[<sub>Volver</sub>](#inicio)

<a name= "TalonariosDeVentasDto"></a>
## Ejemplo de Json basado en `TalonariosDeVentasDto`
```json
{
  "Talonario": 1,
  "Empresa": "M",
  "Filler": "Filler Ejemplo",
  "Descripcion": "Talonario de Ventas Ejemplo",
  "NroDesde": "00000001",
  "NroHasta": "00000100",
  "Proximo": "00000002",
  "Renglones": 10,
  "Sucursal": "SUC01",
  "Observaciones": "Observaciones Ejemplo",
  "Comprob": "FAC"
}

Talonario: Código de talonario de ventas. Valores permitidos: Enteros positivos. Ejemplo: 1.
Empresa: Nombre de la empresa. Caracteres permitidos: 1. Tipo Texto. Ejemplo: "M".
Filler: Campo de uso interno. Tipo texto.
Descripcion: Descripción del talonario. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Talonario de Ventas Ejemplo".
NroDesde: Número desde el cual empieza la numeración del talonario. Caracteres permitidos: 8. Tipo Texto. Ejemplo: "00000001".
NroHasta: Número hasta el cual llega la numeración del talonario. Caracteres permitidos: 8. Tipo Texto. Ejemplo: "00000100".
Proximo: Próximo número en la secuencia del talonario. Caracteres permitidos: 16. Tipo Texto. Ejemplo: "00000002".
Renglones: Cantidad de renglones del talonario. Valores permitidos: Enteros positivos. Ejemplo: 10.
Sucursal: Sucursal asociada al talonario. Caracteres permitidos: 5. Tipo Texto. Ejemplo: "SUC01".
Observaciones: Observaciones adicionales. Tipo Texto. Ejemplo: "Observaciones Ejemplo".
Comprob: Tipo de comprobante. Caracteres permitidos: 3. Tipo Texto. Ejemplo: "FAC".
```
[<sub>Volver</sub>](#inicio)

<a name= "ValoresEscalaDto"></a>
## Ejemplo de Json basado en `ValoresEscalaDto`
```json
{
  "CodEscala": "ES",
  "CodValor": "VAL001",
  "Descripcion": "Valor 1",
  "Habilitado": 1
}

CodEscala: Código identificatorio de la escala. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "ES".
CodValor: Código identificatorio del valor de la escala. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "VAL001".
Descripcion: Descripción del valor. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Valor 1".
Habilitado: Define si el valor de la escala está habilitado. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
```
[<sub>Volver</sub>](#inicio)

<a name= "VendedoresDto"></a>
## Ejemplo de Json basado en `VendedoresDto`
```json
{
  "Codigo": "VEND001",
  "Nombre": "Vendedor Ejemplo",
  "Inhabilitado": 0,
  "TipoDoc": "DNI",
  "NumeroDoc": "12345678",
  "Telefono": "123-456-7890",
  "EMail": "vendedor@ejemplo.com",
  "Observaciones": "Observaciones Ejemplo"
}

Codigo: Código del vendedor. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "VEND001".
Nombre: Nombre del vendedor. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Vendedor Ejemplo".
Inhabilitado: Indica si el vendedor está inhabilitado. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 0.
TipoDoc: Tipo de documento. Caracteres permitidos: 4. Tipo Texto. Ejemplo: "DNI".
NumeroDoc: Número de documento. Caracteres permitidos: 11. Tipo Texto. Ejemplo: "12345678".
Telefono: Teléfono. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "123-456-7890".
EMail: Correo electrónico. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "vendedor@ejemplo.com".
Observaciones: Observaciones adicionales. Tipo Texto. Ejemplo: "Observaciones Ejemplo".
```
[<sub>Volver</sub>](#inicio)


<a name="DepositoDto"></a>

### Ejemplo de JSON para la API REST basado en `DepositoDto`
```json
{
  "CodigoDeposito": "DP",
  "Direccion": "Dirección Ejemplo",
  "Nombre": "Depósito Ejemplo",
  "Habilitado": 1,
  "Observaciones": "Observaciones Ejemplo",
  "DescDim1": "Dim 1",
  "DescDim2": "Dim 2",
  "DescDim3": "Dim 3",
  "DescDim4": "Dim 4",
  "DescDim5": "Dim 5",
  "IdUsuario": 1,
  "Filler1": "Filler Ejemplo",
  "Filler2": 123.456,
  "UsaStockUbicacion": 1,
  "UsaIDPallet": 1,
  "CodigoDepositoTDI": "TDI",
  "RecuentaInventario": 1,
  "PidePalletOrigenEnPuk": 1,
  "PidePalletDestinoEnPuk": 1,
  "UsaZonas": 1,
  "LecturaEnPicking": "LECT1",
  "LecturaEnAlmacenaje": "LECT2",
  "PickingMultiPallet": 1,
  "AlmacenajeMultiPallet": 1,
  "VerificaStockEnEstiba": 1,
  "FractionsEnable": 1,
  "IdUbicacionNoHallados": 1,
  "IdUbicacionPivot": 2,
  "PermiteTransferenciaAUbicacion": 1,
  "EsDepositoDetallado": 1,
  "IdUbicacionCuarentena": 3,
  "CodigoCentroDistribucion": "CD",
  "DiasAlVencimiento": 30,
  "DepositoDeTerceros": 0
}
CodigoDeposito: Código del depósito. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "DP".
Direccion: Dirección del depósito. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Dirección Ejemplo".
Nombre: Nombre del depósito. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Depósito Ejemplo".
Habilitado: Habilita el depósito. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
Observaciones: Observaciones del depósito. Tipo Texto. Ejemplo: "Observaciones Ejemplo".
DescDim1: Descripción de la primera dimensión. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Dim 1".
DescDim2: Descripción de la segunda dimensión. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Dim 2".
DescDim3: Descripción de la tercera dimensión. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Dim 3".
DescDim4: Descripción de la cuarta dimensión. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Dim 4".
DescDim5: Descripción de la quinta dimensión. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "Dim 5".
IdUsuario: Identificador de usuario logueado. Valores permitidos: Enteros positivos. Ejemplo: 1.
Filler1: Campo de uso interno (texto).
Filler2: Campo de uso interno (decimal).
UsaStockUbicacion: Indica si se utiliza stock por ubicación. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
UsaIDPallet: Indica si se utiliza ID de pallet. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
CodigoDepositoTDI: Código de depósito para TDI. Caracteres permitidos: 15. Tipo Texto. Ejemplo: "TDI".
RecuentaInventario: Indica si se realiza recuento de inventario. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
PidePalletOrigenEnPuk: Indica si se pide pallet de origen en PUK. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
PidePalletDestinoEnPuk: Indica si se pide pallet de destino en PUK. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
UsaZonas: Indica si el depósito utiliza zonas. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
LecturaEnPicking: Indica si se requiere lectura en picking. Caracteres permitidos: 6. Tipo Texto. Ejemplo: "LECT1".
LecturaEnAlmacenaje: Indica si se requiere lectura en almacenaje. Caracteres permitidos: 6. Tipo Texto. Ejemplo: "LECT2".
PickingMultiPallet: Indica si se permite picking multi-pallet. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
AlmacenajeMultiPallet: Indica si se permite almacenaje multi-pallet. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
VerificaStockEnEstiba: Indica si se verifica stock en estiba. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
FractionsEnable: Indica si se habilita el uso de fracciones. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
IdUbicacionNoHallados: ID de ubicación para productos no hallados. Valores permitidos: Enteros positivos. Ejemplo: 1.
IdUbicacionPivot: ID de ubicación pivote. Valores permitidos: Enteros positivos. Ejemplo: 2.
PermiteTransferenciaAUbicacion: Indica si se permite transferencia a ubicación. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
EsDepositoDetallado: Indica si es un depósito detallado. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
IdUbicacionCuarentena: ID de ubicación de cuarentena. Valores permitidos: Enteros positivos. Ejemplo: 3.
CodigoCentroDistribucion: Código del Centro de Distribución (CD). Caracteres permitidos: 2. Tipo Texto. Ejemplo: "CD".
DiasAlVencimiento: Días al vencimiento de los productos en el depósito. Valores permitidos: Enteros positivos. Ejemplo: 30.
DepositoDeTerceros: Indica si el depósito pertenece a un tercero. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 0.
```

[<sub>Volver</sub>](#inicio)


<a name="TransporteDto"></a>

### Ejemplo de JSON para la API REST basado en `TransporteDto`
```json
{
  "CodigoTransporte": "TRA001",
  "CUITTransporte": "30-12345678-9",
  "DomicilioTransporte": "Dirección Ejemplo",
  "NombreTransporte": "Transporte Ejemplo",
  "CodigoPostal": "1234",
  "Localidad": "Localidad Ejemplo",
  "CodigoProvincia": "BA",
  "Telefono": "123-456-7890",
  "Email": "transporte@ejemplo.com",
  "Observaciones": "Observaciones Ejemplo"
}
CodigoTransporte: Código único que identifica al transporte. Caracteres permitidos: 10. Tipo Texto. Ejemplo: "TRA001".
CUITTransporte: CUIT del transporte. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "30-12345678-9".
DomicilioTransporte: Dirección del transporte. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Dirección Ejemplo".
NombreTransporte: Nombre del transporte. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Transporte Ejemplo".
CodigoPostal: Código postal del transporte. Caracteres permitidos: 8. Tipo Texto. Ejemplo: "1234".
Localidad: Localidad donde está ubicado el transporte. Caracteres permitidos: 50. Tipo Texto. Ejemplo: "Localidad Ejemplo".
CodigoProvincia: Código de la provincia donde está ubicado el transporte. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "BA".
Telefono: Número de teléfono del transporte. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "123-456-7890".
Email: Correo electrónico del transporte. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "transporte@ejemplo.com".
Observaciones: Observaciones adicionales sobre el transporte. Tipo Texto. Ejemplo: "Observaciones Ejemplo".
```

[<sub>Volver</sub>](#inicio)

<a name="ProveedorDto"></a>

### Ejemplo de JSON para la API REST basado en `ProveedorDto`
```json
{
  "CodProvee": "PROV01",
  "CPostal": "1234",
  "Domicilio": "Dirección Ejemplo",
  "Email": "proveedor@ejemplo.com",
  "Localidad": "Localidad Ejemplo",
  "NCuit": "30-12345678-9",
  "NomProvee": "Proveedor Ejemplo",
  "Observacion": "Observación Ejemplo",
  "ObservacionAdic": "Observación Adicional Ejemplo",
  "Telefono1": "123-456-7890",
  "Telefono2": "987-654-3210",
  "Habilitado": 1
}
CodProvee: Código del proveedor. Caracteres permitidos: 6. Tipo Texto. Ejemplo: "PROV01".
CPostal: Código postal del proveedor. Caracteres permitidos: 8. Tipo Texto. Ejemplo: "1234".
Domicilio: Dirección física del proveedor. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "Dirección Ejemplo".
Email: Correo electrónico del proveedor. Caracteres permitidos: 255. Tipo Texto. Ejemplo: "proveedor@ejemplo.com".
Localidad: Localidad del proveedor. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Localidad Ejemplo".
NCuit: Número de CUIT del proveedor. Caracteres permitidos: 15. Tipo Texto. Ejemplo: "30-12345678-9".
NomProvee: Nombre del proveedor. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Proveedor Ejemplo".
Observacion: Observaciones adicionales. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Observación Ejemplo".
ObservacionAdic: Segunda observación adicional. Caracteres permitidos: 60. Tipo Texto. Ejemplo: "Observación Adicional Ejemplo".
Telefono1: Primer número de teléfono. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "123-456-7890".
Telefono2: Segundo número de teléfono. Caracteres permitidos: 30. Tipo Texto. Ejemplo: "987-654-3210".
Habilitado: Indica si el proveedor está habilitado. Valores permitidos: 1 (Sí) o 0 (No). Ejemplo: 1.
```

[<sub>Volver</sub>](#inicio)

<a name="MovimientoStockDto"></a>

### Ejemplo de JSON para la API REST basado en `MovimientoStockDto`

```json
{
  "CodArticu": "123456 ALE00",
  "Cantidad": 50.500000,
  "CodDeposito": "FF",
  "CodProveedor": "XXX123",
  "NumeroPartida": "AR123456",
  "FechaVencimiento": "2025-12-31T12:00:00",
  "Observacion": "Movimiento de stock",
  "IdUsuario": 1,
  "Guid": "550e8400-e29b-41d4-a716-446655440000",
  "TipoMovimiento": "E",
  "TipoComprobanteInt": "FA",
  "NumeroComprobanteInt": "000123",
  "IdUbi": 20,
  "TipoComprobanteRef": 11,
  "NumeroComprobanteRef": "00054321",
  "RengCompRef": 1,
  "Idp": 789,
  "Dispositivo": "PC-001",
  "TipoRechazo": 0,
  "T_Comp": "ING"
}

CodArticu: Código del artículo relacionado con el movimiento de stock. Caracteres permitidos: 15. Tipo Texto. Ejemplo: "123456 ALE00".
Cantidad: Cantidad del artículo en el movimiento. Tipo Decimal (16,6). Ejemplo: 50.500000.
CodDeposito: Código del depósito donde se realiza el movimiento. Caracteres permitidos: 2. Tipo Texto. Ejemplo: "FF".
CodProveedor: Código del proveedor relacionado con el movimiento. Caracteres permitidos: 6. Tipo Texto. Ejemplo: "XXX123".
NumeroPartida: Número de partida asociado al artículo en el movimiento. Caracteres permitidos: 25. Tipo Texto. Ejemplo: "AR123456".
FechaVencimiento: Fecha de vencimiento del artículo (si aplica). Formato: "yyyy-MM-ddTHH:mm:ss". Ejemplo: "2025-12-31T12:00:00".
Observacion: Observación del movimiento. Caracteres permitidos: 20. Tipo Texto. Ejemplo: "Movimiento de stock".
IdUsuario: Identificador del usuario que realiza el movimiento. Tipo Entero. Ejemplo: 1.
Guid: Identificador único del movimiento. Tipo GUID. Ejemplo: "550e8400-e29b-41d4-a716-446655440000".
TipoMovimiento: Tipo de movimiento (entrada/salida). Caracteres permitidos: 1. Ejemplo: 'E' (Entrada) o 'S' (Salida).
TipoComprobanteInt: Tipo de comprobante interno asociado al movimiento. Caracteres permitidos: 2. Ejemplo: "FA".
NumeroComprobanteInt: Número de comprobante interno asociado al movimiento. Caracteres permitidos: 6. Ejemplo: "000123".
IdUbi: Identificador de la ubicación. Tipo Entero. Ejemplo: 20.
TipoComprobanteRef: Tipo de comprobante de referencia asociado al movimiento. Tipo Entero. Ejemplo: 11.
NumeroComprobanteRef: Número de comprobante de referencia asociado al movimiento. Caracteres permitidos: 14. Tipo Texto. Ejemplo: "00054321".
RengCompRef: Renglón del comprobante interno asociado al movimiento. Tipo Entero. Ejemplo: 1.
Idp: Identificador del pallet (IDP). Tipo Entero. Ejemplo: 789.
Dispositivo: Dispositivo desde el que se realiza el movimiento. Caracteres permitidos: 100. Tipo Texto. Ejemplo: "PC-001".
TipoRechazo: Tipo de rechazo del movimiento. Tipo Entero. Ejemplo: 0 (Sin rechazo).
T_Comp: Tipo de comprobante. Caracteres permitidos: 3. Ejemplo: "EGR" (Egreso) o "ING" (Ingreso).

```
[<sub>Volver</sub>](#inicio)

<a name="requerimientoshardware"></a>

# Requerimientos de Hardware

<a name="Servidor"></a>

  ## Requerimientos de Servidor:
    # Sistema Operativo:

-       Windows Server 2017 (Versión 14) o superior (recomendado)
      Windows 10 (para instalaciones de bajo volumen o pruebas)

    # Procesador:

      Procesador Intel o AMD de 64 bits (se recomienda mínimo un Quad-Core)

    # Memoria RAM:

      8 GB como mínimo para instalaciones pequeñas
      16 GB o más para instalaciones con mayor carga de usuarios o procesamiento

    # Almacenamiento:

    Disco duro con al menos 100 GB de espacio libre, preferentemente en unidades SSD para mejor rendimiento.
    La cantidad de espacio requerido puede variar según la cantidad de datos que maneje el sistema.

    # Base de Datos:
    
    SQL Server 2017 (Versión 14) o superior.
    Se recomienda contar con una versión estándar o enterprise para empresas medianas o grandes.
    Puede utilizarse la versión express en bases de datos pequeñas.
    
    # Red:
    
    Conexión de red a 1 Gbps o superior.
    Acceso seguro desde las estaciones de trabajo al servidor a través de una red local (LAN) o VPN.
    
    # Software adicional:
    
    .NET Framework 4.7.2 o superior.
    Internet Information Services (IIS) si se utilizarán módulos web.

  <a name="Cliente"></a>

  [<sub>Volver</sub>](#inicio)

    
  ## Requerimientos de Estación de Trabajo (Clientes):
    
    # Sistema Operativo:
    
    Windows 10 o superior.
    
    # Procesador:
    
    Intel Core i3 o superior.
    
    # Memoria RAM:
    
    Mínimo 4 GB de RAM.
    
    # Almacenamiento:
    
    Al menos 10 GB de espacio libre para la instalación del cliente y sus dependencias.
    
    # Software adicional:
    
    Microsoft Office (si se utilizan integraciones, como la generación de reportes, documentos, o importaciones propias de la gestión).
    Internet Explorer 11 o superior.


[<sub>Volver</sub>](#inicio)

<a name="Moviles"></a>

# Dispositivos Móviles

<a name="Colectoras"></a>
  
  ## Colectoras de datos

### Sistema operativo: 
  Android versión 7 o superior

### Tamaño de pantalla:
  5.5 pulgadas o superior

<a name="Celulares"></a>
  
  ## Celulares

Estos dispositivos serán utilizados en con la aplicación TMS para choferes, y tienen los mismos requisitos que las colectoras de datos.
También pueden utilizarse conjuntamente con lectoras de datos, en reemplazo de las colectoras de datos.

<a name="Lectoras"></a>
  
  ## Lectoras

### Tipo de lectura:
  Lectura 2D

### Resistencia a golpes y polvo:
  IP68 o superior
  
  [<sub>Volver</sub>](#inicio)


