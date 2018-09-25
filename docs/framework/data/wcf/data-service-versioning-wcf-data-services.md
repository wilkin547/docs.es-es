---
title: Control de versiones del servicio de datos (Data Services de Microsoft WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: 9a92346267012d3651d04648b357bbf530097e34
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47073260"
---
# <a name="data-service-versioning-wcf-data-services"></a>Control de versiones del servicio de datos (Data Services de Microsoft WCF)
El [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] le permite crear servicios de datos para que los clientes pueden tener acceso a datos como recursos usando URI que se basan en un modelo de datos. OData también admite la definición de operaciones de servicio. Después de la implementación inicial y de haber transcurrido potencialmente varias horas durante su duración, estos servicios de datos pueden necesitar ser cambiados debido a diversas razones, como cambios en las necesidades comerciales, requisitos de tecnología de la información o para resolver otros problemas. Al realizar cambios en un servicio de datos existente, debe considerar si va a definir una nueva versión de su servicio de datos y cómo minimizar mejor el impacto en las aplicaciones cliente existentes. En este tema se proporciona orientación sobre cuándo y cómo crear una nueva versión de un servicio de datos. También se describe cómo WCF Data Services administra el intercambio entre clientes y servicios de datos que admiten diferentes versiones del Protocolo OData.

## <a name="versioning-a-wcf-data-service"></a>Control de versiones de WCF Data Services
 Una vez implementado un servicio de datos y usados los datos, los cambios realizados al servicio de datos tienen el potencial para producir problemas de compatibilidad con las aplicaciones cliente existentes. Sin embargo, como las necesidades del negocio totales del servicio requieren a menudo cambios, debe considerar cuándo y cómo crear una nueva versión de su servicio de datos con el menor impacto para las aplicaciones cliente.

### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Cambios del modelo de datos que recomiendan una nueva versión del servicio de datos
 Al considerar si se va a publicar una nueva versión de un servicio de datos, es importante entender cómo los diferentes tipos de cambios pueden afectar a las aplicaciones cliente. Los cambios de un servicio de datos que podrían requerir crear una nueva versión de un servicio de datos se pueden dividir en las siguientes dos categorías:

-   Los cambios del contrato de servicio —que incluyen actualizaciones de las operaciones de servicio, cambios de la accesibilidad de conjuntos de entidades (fuentes), cambios de versiones y otros cambios de los comportamientos del servicio.

-   Los cambios del contrato de datos —que incluyen cambios del modelo de datos, formatos de fuente o personalización de la fuente.

 La tabla siguiente detalla para qué clases de cambios debe considerar la posibilidad de publicar una nueva versión del servicio de datos:

|Tipo de cambio|Requiere una nueva versión|No se necesita una nueva versión|
|--------------------|----------------------------|----------------------------|
|Operaciones de servicio|-Agregar nuevo parámetro<br />-Cambiar tipo de valor devuelto<br />-Quite de la operación de servicio|-Eliminar parámetro existente<br />-Agregar nueva operación de servicio|
|Comportamientos de servicio|-Deshabilitar las solicitudes de recuento<br />-Deshabilitar la compatibilidad de la proyección<br />-Incrementar la versión del servicio de datos necesaria|-Habilitar solicitudes de recuento<br />-Habilitar la compatibilidad de la proyección<br />-Reducir la versión del servicio de datos necesaria|
|Permisos del conjunto de entidades|-Restringir los permisos del conjunto de entidades<br />-Cambiar el código de respuesta (nuevo primer valor de dígito) <sup>1</sup>|-Relaje los permisos del conjunto de entidades<br />-Cambiar el código de respuesta (mismo primer valor de dígito)|
|Propiedades de entidad|-Quitar propiedad o relación existente<br />-Agregar una propiedad que no aceptan valores null<br />-Cambiar la propiedad existente|-Agregar una propiedad que acepta valores NULL<sup>2</sup>|
|Conjuntos de entidades|-Quite el conjunto de entidades|-Agregar el tipo derivado<br />-Cambiar el tipo base<br />-Agregar conjunto de entidades|
|Personalización de fuentes|-Cambiar la asignación de propiedad de entidad||

 <sup>1</sup> Esto puede depender sea estrictamente necesario una aplicación cliente se basa en la recepción de un código de error específico.

 <sup>2</sup> puede establecer el <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> propiedad `true` para que el cliente omita cualquier nueva propiedad enviada por el servicio de datos que no estén definidos en el cliente. Sin embargo, cuando se realizan inserciones, las propiedades no incluidas por el cliente en la solicitud POST se establecen en sus valores predeterminados. Para las actualizaciones, cualquier dato existente en una propiedad desconocida para el cliente podría sobrescribirse con los valores predeterminados. En este caso, debería enviar la actualización como una solicitud MERGE, que es el valor predeterminado. Para obtener más información, consulte [administrar el contexto de servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).

### <a name="how-to-version-a-data-service"></a>Cómo controlar las versiones de un servicio de datos
 Cuando se requiere, una nueva versión del servicio de datos se define creando una nueva instancia del servicio con un contrato de servicio o un modelo de datos actualizado. A continuación, este nuevo servicio se expone usando un nuevo extremo de URI, que lo diferencia de la versión anterior. Por ejemplo:

-   La versión anterior: `http://services.odata.org/Northwind/v1/Northwind.svc/`

-   Nueva versión: `http://services.odata.org/Northwind/v2/Northwind.svc/`

 Al actualizar un servicio de datos, los clientes necesitarán también estar actualizados según los nuevos metadatos del servicio de datos y usar el nuevo URI raíz. Cuando sea posible, debe mantener la versión anterior del servicio de datos para admitir clientes que todavía no se hayan actualizado para usar la nueva versión. Se pueden quitar las versiones anteriores de un servicio de datos cuando ya no se necesitan. Debe considerar la posibilidad de mantener el URI del extremo del servicio de datos en un archivo de configuración externo.

## <a name="odata-protocol-versions"></a>Versiones del protocolo OData
 Medida que se publican nuevas versiones de OData, las aplicaciones cliente no se usen la misma versión del Protocolo OData que es compatible con el servicio de datos. Una aplicación cliente antigua puede tener acceso a un servicio de datos que admite una versión más reciente de OData. Una aplicación cliente también puede estar usando una versión más reciente de la biblioteca de cliente de WCF Data Services, que es compatible con una versión más reciente de OData de servicio de datos que se tiene acceso.

 WCF Data Services aprovecha la compatibilidad proporcionada por OData para administrar tales escenarios de control de versiones. También hay compatibilidad para generar y utilizar los metadatos del modelo de datos para crear clases de servicio de datos de cliente cuando el cliente usa una versión diferente de OData que los datos usa el servicio. Para obtener más información, consulte [OData: Protocol Versioning](https://go.microsoft.com/fwlink/?LinkId=186071).

### <a name="version-negotiation"></a>Negociación de las versiones
 El servicio de datos puede configurarse para definir la versión más alta del Protocolo OData que se usará el servicio, independientemente de la versión solicitada por el cliente. Puede hacerlo especificando un <xref:System.Data.Services.Common.DataServiceProtocolVersion> valor para el <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> propiedad de la <xref:System.Data.Services.DataServiceBehavior> utilizado por el servicio de datos. Para obtener más información, consulte [configurando el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).

 Cuando una aplicación utiliza las bibliotecas de cliente de WCF Data Services para tener acceso a un servicio de datos, las bibliotecas establecen automáticamente estos encabezados en los valores correctos, según la versión de OData y las características que se usan en la aplicación. De forma predeterminada, WCF Data Services usa la versión más antigua de protocolo que admite la operación solicitada.

 La siguiente tabla detallan las versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] que incluyen compatibilidad con WCF Data Services para versiones específicas del Protocolo OData.

|Versión de Protocolo OData|Compatibilidad introducida en…|
|-----------------------------------------------------------------------------------|----------------------------|
|Versión 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Service Pack 1 (SP1)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versión 3|
|Versión 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-Una actualización de [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1. Puede descargar e instalar la actualización desde el [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=158125).<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versión 4|
|Versión 3|-Puede descargar e instalar una versión preliminar que admite la versión 3 de OData desde la [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=203885).|

### <a name="metadata-versions"></a>Versiones de metadatos
 De forma predeterminada, WCF Data Services usa la versión 1.1 de CSDL para representar un modelo de datos. Este siempre es el caso para los modelos de datos basados en un proveedor de reflexión o en un proveedor del servicio de datos personalizados. No obstante, cuando se define un modelo de datos mediante [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], la versión devuelta de CSDL es la misma que la que usa [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. La versión de CSDL viene determinada por el espacio de nombres de los [elemento de esquema](https://msdn.microsoft.com/library/396074d8-f99c-4f50-a073-68bce848224f). Para obtener más información, vea la especificación [ \[MC-CSDL\]: formato de archivo de definición de esquemas conceptuales](https://go.microsoft.com/fwlink/?LinkId=159072).

 El elemento `DataServices` de los metadatos devueltos también contiene un atributo `DataServiceVersion`, que tiene el mismo valor que el encabezado `DataServiceVersion` del mensaje de respuesta. Las aplicaciones cliente, como el **Add Service Reference** cuadro de diálogo en Visual Studio, use esta información para generar clases de servicio de datos de cliente que funcionan correctamente con la versión de WCF Data Services que hospedan el servicio de datos. Para obtener más información, consulte [OData: Protocol Versioning](https://go.microsoft.com/fwlink/?LinkId=186071).

## <a name="see-also"></a>Vea también

- [Proveedores de Data Services](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
