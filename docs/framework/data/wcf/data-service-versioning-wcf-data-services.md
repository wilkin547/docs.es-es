---
title: Control de versiones del servicio de datos (Data Services de Microsoft WCF)
ms.date: 03/30/2017
helpviewer_keywords:
- versioning, WCF Data Services
- versioning [WCF Data Services]
- WCF Data Services, versioning
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
ms.openlocfilehash: 0d77f54b5ef20db81c3c20f486ac7314f73aece8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="data-service-versioning-wcf-data-services"></a>Control de versiones del servicio de datos (Data Services de Microsoft WCF)
El [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] le permite crear servicios de datos para que los clientes pueden tener acceso a datos como recursos usando URI que se basan en un modelo de datos. [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] también admite la definición de operaciones de servicio. Después de la implementación inicial y de haber transcurrido potencialmente varias horas durante su duración, estos servicios de datos pueden necesitar ser cambiados debido a diversas razones, como cambios en las necesidades comerciales, requisitos de tecnología de la información o para resolver otros problemas. Al realizar cambios en un servicio de datos existente, debe considerar si va a definir una nueva versión de su servicio de datos y cómo minimizar mejor el impacto en las aplicaciones cliente existentes. En este tema se proporciona orientación sobre cuándo y cómo crear una nueva versión de un servicio de datos. También describe cómo administra [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] un intercambio entre clientes y servicios de datos que admite diferentes versiones del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
## <a name="versioning-a-wcf-data-service"></a>Control de versiones de WCF Data Services  
 Una vez implementado un servicio de datos y usados los datos, los cambios realizados al servicio de datos tienen el potencial para producir problemas de compatibilidad con las aplicaciones cliente existentes. Sin embargo, como las necesidades del negocio totales del servicio requieren a menudo cambios, debe considerar cuándo y cómo crear una nueva versión de su servicio de datos con el menor impacto para las aplicaciones cliente.  
  
### <a name="data-model-changes-that-recommend-a-new-data-service-version"></a>Cambios del modelo de datos que recomiendan una nueva versión del servicio de datos  
 Al considerar si se va a publicar una nueva versión de un servicio de datos, es importante entender cómo los diferentes tipos de cambios pueden afectar a las aplicaciones cliente. Los cambios de un servicio de datos que podrían requerir crear una nueva versión de un servicio de datos se pueden dividir en las siguientes dos categorías:  
  
-   Los cambios del contrato de servicio —que incluyen actualizaciones de las operaciones de servicio, cambios de la accesibilidad de conjuntos de entidades (fuentes), cambios de versiones y otros cambios de los comportamientos del servicio.  
  
-   Los cambios del contrato de datos —que incluyen cambios del modelo de datos, formatos de fuente o personalización de la fuente.  
  
 La tabla siguiente detalla para qué clases de cambios debe considerar la posibilidad de publicar una nueva versión del servicio de datos:  
  
|Tipo de cambio|Requiere una nueva versión|No se necesita una nueva versión|  
|--------------------|----------------------------|----------------------------|  
|Operaciones de servicio|-Agregar nuevo parámetro<br />-Cambiar tipo de valor devuelto<br />-Quitar la operación de servicio|-Eliminar parámetro existente<br />-Agregar nueva operación de servicio|  
|Comportamientos de servicio|-Deshabilitar las solicitudes de recuento<br />-Deshabilitar la compatibilidad de la proyección<br />-Aumentar la versión de servicio de datos necesaria|-Habilitar las solicitudes de recuento<br />-Habilitar la compatibilidad de la proyección<br />-Disminuir la versión del servicio de datos necesarios|  
|Permisos del conjunto de entidades|-Restringir permisos del conjunto de entidades<br />-Cambiar el código de respuesta (nuevo primer valor de dígito) <sup>1</sup>|-Relaje los permisos del conjunto de entidades<br />-Cambiar el código de respuesta (mismo primer valor de dígito)|  
|Propiedades de entidad|-Quitar propiedad o relación existente<br />-Agregar una propiedad que no aceptan valores null<br />-Cambiar la propiedad existente|-Agregar una propiedad que acepta valores NULL<sup>2</sup>|  
|Conjuntos de entidades|-Quitar el conjunto de entidades|-Agregar el tipo derivado<br />-Cambie el tipo base<br />-Agregar conjunto de entidades|  
|Personalización de fuentes|-Cambiar la asignación de propiedad de entidad||  
  
 <sup>1</sup> Esto puede depender de qué tan estricta una aplicación cliente se basa en recibir un código de error específico.  
  
 <sup>2</sup> puede establecer la <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> propiedad `true` para que el cliente omita cualquier nueva propiedad enviada por el servicio de datos que no estén definidos en el cliente. Sin embargo, cuando se realizan inserciones, las propiedades no incluidas por el cliente en la solicitud POST se establecen en sus valores predeterminados. Para las actualizaciones, cualquier dato existente en una propiedad desconocida para el cliente podría sobrescribirse con los valores predeterminados. En este caso, debería enviar la actualización como una solicitud MERGE, que es el valor predeterminado. Para obtener más información, consulte [administrar el contexto de servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
### <a name="how-to-version-a-data-service"></a>Cómo controlar las versiones de un servicio de datos  
 Cuando se requiere, una nueva versión del servicio de datos se define creando una nueva instancia del servicio con un contrato de servicio o un modelo de datos actualizado. A continuación, este nuevo servicio se expone usando un nuevo extremo de URI, que lo diferencia de la versión anterior. Por ejemplo:  
  
-   La versión anterior: `http://services.odata.org/Northwind/v1/Northwind.svc/`  
  
-   Nueva versión: `http://services.odata.org/Northwind/v2/Northwind.svc/`  
  
 Al actualizar un servicio de datos, los clientes necesitarán también estar actualizados según los nuevos metadatos del servicio de datos y usar el nuevo URI raíz. Cuando sea posible, debe mantener la versión anterior del servicio de datos para admitir clientes que todavía no se hayan actualizado para usar la nueva versión. Se pueden quitar las versiones anteriores de un servicio de datos cuando ya no se necesitan. Debe considerar la posibilidad de mantener el URI del extremo del servicio de datos en un archivo de configuración externo.  
  
## <a name="odata-protocol-versions"></a>Versiones del protocolo OData  
 Como las nuevas versiones de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] están publicadas, las aplicaciones cliente que no esté utilizando la misma versión de la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocolo que es compatible con el servicio de datos. Una aplicación cliente anterior puede tener acceso a un servicio de datos que admita una versión más reciente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Una aplicación cliente también esté usando una versión más reciente de la [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] biblioteca de cliente, que es compatible con una versión más reciente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de servicio de datos que se tiene acceso.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] aprovecha la compatibilidad proporcionada por [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] para administrar estos escenarios de control de versiones. También hay compatibilidad para generar y utilizar los metadatos del modelo de datos para crear las clases de servicio de datos de cliente cuando el cliente usa una versión diferente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que el servicio de datos usa. Para obtener más información, consulte [OData: control de versiones de protocolo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
### <a name="version-negotiation"></a>Negociación de las versiones  
 El servicio de datos puede configurarse para definir la versión más reciente de la [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocolo que se usará en el servicio, independientemente de la versión solicitada por el cliente. Puede hacerlo mediante la especificación de un <xref:System.Data.Services.Common.DataServiceProtocolVersion> valor para el <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> propiedad de la <xref:System.Data.Services.DataServiceBehavior> utilizado por el servicio de datos. Para obtener más información, consulte [configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Cuando una aplicación usa las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para tener acceso a un servicio de datos, las bibliotecas establecen automáticamente estos encabezados en los valores correctos, en función de la versión de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y de las características que se usan en la aplicación. De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] utiliza la versión más antigua de protocolo que admite la operación solicitada.  
  
 En la siguiente tabla se detallan las versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] que incluyen compatibilidad con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para versiones específicas del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
|Versión del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|Compatibilidad introducida en…|  
|-----------------------------------------------------------------------------------|----------------------------|  
|Versión 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Service Pack 1 (SP1)<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versión 3|  
|Versión 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-Una actualización [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1. Puede descargar e instalar la actualización desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=158125).<br />-   [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] versión 4|  
|Versión 3|-Se puede descargar e instalar una versión preliminar que admite [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] versión 3 de la [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkId=203885).|  
  
### <a name="metadata-versions"></a>Versiones de metadatos  
 De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usa la versión 1.1 de CSDL para representar un modelo de datos. Este siempre es el caso para los modelos de datos basados en un proveedor de reflexión o en un proveedor del servicio de datos personalizados. No obstante, cuando se define un modelo de datos mediante [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], la versión devuelta de CSDL es la misma que la que usa [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]. La versión de CSDL se determina por el espacio de nombres de la [elemento Schema](http://msdn.microsoft.com/library/396074d8-f99c-4f50-a073-68bce848224f). Para obtener más información, vea la especificación [ \[MC-CSDL\]: formato de archivo de definición de esquemas conceptuales](http://go.microsoft.com/fwlink/?LinkId=159072).  
  
 El elemento `DataServices` de los metadatos devueltos también contiene un atributo `DataServiceVersion`, que tiene el mismo valor que el encabezado `DataServiceVersion` del mensaje de respuesta. Las aplicaciones cliente, como el **Agregar referencia de servicio** cuadro de diálogo de Visual Studio, utilice esta información para generar los servicios de datos de cliente, las clases que funcionan correctamente con la versión de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] que hospede el servicio de datos. Para obtener más información, consulte [OData: control de versiones de protocolo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
## <a name="see-also"></a>Vea también  
 [Proveedores de Data Services](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [Definir Servicios de datos de WCF](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
