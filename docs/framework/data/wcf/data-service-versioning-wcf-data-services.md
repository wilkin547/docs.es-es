---
title: "Control de versiones del servicio de datos (Servicios de datos de Microsoft WCF) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "control de versiones [WCF Data Services]"
  - "control de versiones, Servicios de datos de Microsoft WCF"
  - "Servicios de datos de Microsoft WCF, control de versiones"
ms.assetid: e3e899cc-7f25-4f67-958f-063f01f79766
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Control de versiones del servicio de datos (Servicios de datos de Microsoft WCF)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] le permite crear servicios de datos para que los clientes puedan tener acceso a datos como recursos usando URI basados en un modelo de datos.  [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] también admite la definición de operaciones de servicio.  Después de la implementación inicial y de haber transcurrido potencialmente varias horas durante su duración, estos servicios de datos pueden necesitar ser cambiados debido a diversas razones, como cambios en las necesidades comerciales, requisitos de tecnología de la información o para resolver otros problemas.  Al realizar cambios en un servicio de datos existente, debe considerar si va a definir una nueva versión de su servicio de datos y cómo minimizar mejor el impacto en las aplicaciones cliente existentes.  En este tema se proporciona orientación sobre cuándo y cómo crear una nueva versión de un servicio de datos.  También describe cómo administra [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] un intercambio entre clientes y servicios de datos que admite diferentes versiones del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
## Control de versiones de WCF Data Services  
 Una vez implementado un servicio de datos y usados los datos, los cambios realizados al servicio de datos tienen el potencial para producir problemas de compatibilidad con las aplicaciones cliente existentes.  Sin embargo, como las necesidades del negocio totales del servicio requieren a menudo cambios, debe considerar cuándo y cómo crear una nueva versión de su servicio de datos con el menor impacto para las aplicaciones cliente.  
  
### Cambios del modelo de datos que recomiendan una nueva versión del servicio de datos  
 Al considerar si se va a publicar una nueva versión de un servicio de datos, es importante entender cómo los diferentes tipos de cambios pueden afectar a las aplicaciones cliente.  Los cambios de un servicio de datos que podrían requerir crear una nueva versión de un servicio de datos se pueden dividir en las siguientes dos categorías:  
  
-   Los cambios del contrato de servicio —que incluyen actualizaciones de las operaciones de servicio, cambios de la accesibilidad de conjuntos de entidades \(fuentes\), cambios de versiones y otros cambios de los comportamientos del servicio.  
  
-   Los cambios del contrato de datos —que incluyen cambios del modelo de datos, formatos de fuente o personalización de la fuente.  
  
 La tabla siguiente detalla para qué clases de cambios debe considerar la posibilidad de publicar una nueva versión del servicio de datos:  
  
|Tipo de cambio|Requiere una nueva versión|No se necesita una nueva versión|  
|--------------------|--------------------------------|--------------------------------------|  
|Operaciones de servicio|-   Agregar nuevo parámetro<br />-   Cambiar el tipo de valor devuelto<br />-   Elimine la operación de servicio|-   Suprimir el parámetro existente<br />-   Agregar la nueva operación del servicio|  
|Comportamientos de servicio|-   Deshabilitar las solicitudes del recuento<br />-   Deshabilitar la compatibilidad de la proyección<br />-   Aumentar la versión del servicio de datos necesaria|-   Habilitar las solicitudes del recuento<br />-   Habilitar la compatibilidad de la proyección<br />-   Disminuir la versión del servicio de datos necesaria|  
|Permisos del conjunto de entidades|-   Restrinja los permisos del conjunto de entidades<br />-   Cambiar el código de respuesta \(nuevo primer valor de dígito\) <sup>1</sup>|-   Relaje los permisos del conjunto de entidades<br />-   Cambiar el código de respuesta \(mismo primer valor de dígito\)|  
|Propiedades de entidad|-   Elimine la propiedad o relación existente<br />-   Agregar la propiedad que no acepta valores NULL<br />-   Cambiar la propiedad existente|-   Agregar la propiedad que acepta valores NULL<sup>2</sup>|  
|Conjuntos de entidades|-   Elimine el conjunto de entidades|-   Agregar el tipo derivado<br />-   Cambiar el tipo base<br />-   Agregar el conjunto de entidades|  
|Personalización de fuentes|-   Cambiar la asignación de la propiedad de entidad||  
  
 <sup>1</sup> esto puede depender de que sea estrictamente necesario que una aplicación cliente se base en recibir un código de error concreto.  
  
 <sup>2</sup> Puede establecer la propiedad <xref:System.Data.Services.Client.DataServiceContext.IgnoreMissingProperties%2A> en `true` para hacer que el cliente omita cualquier nueva propiedad enviada por el servicio de datos no definida en el cliente.  Sin embargo, cuando se realizan inserciones, las propiedades no incluidas por el cliente en la solicitud POST se establecen en sus valores predeterminados.  Para las actualizaciones, cualquier dato existente en una propiedad desconocida para el cliente podría sobrescribirse con los valores predeterminados.  En este caso, debería enviar la actualización como una solicitud MERGE, que es el valor predeterminado.  Para obtener más información, consulta [Administrar el contexto del servicio de datos](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md).  
  
### Cómo controlar las versiones de un servicio de datos  
 Cuando se requiere, una nueva versión del servicio de datos se define creando una nueva instancia del servicio con un contrato de servicio o un modelo de datos actualizado.  A continuación, este nuevo servicio se expone usando un nuevo extremo de URI, que lo diferencia de la versión anterior.  Por ejemplo:  
  
-   La versión anterior: `http://services.odata.org/Northwind/v1/Northwind.svc/`  
  
-   Nueva versión: `http://services.odata.org/Northwind/v2/Northwind.svc/`  
  
 Al actualizar un servicio de datos, los clientes necesitarán también estar actualizados según los nuevos metadatos del servicio de datos y usar el nuevo URI raíz.  Cuando sea posible, debe mantener la versión anterior del servicio de datos para admitir clientes que todavía no se hayan actualizado para usar la nueva versión.  Se pueden quitar las versiones anteriores de un servicio de datos cuando ya no se necesitan.  Debe considerar la posibilidad de mantener el URI del extremo del servicio de datos en un archivo de configuración externo.  
  
## Versiones del protocolo OData  
 A medida que se publican nuevas versiones de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], quizá las aplicaciones cliente no usen la misma versión del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que admite el servicio de datos.  Una aplicación cliente anterior puede tener acceso a un servicio de datos que admita una versión más reciente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  Una aplicación cliente también puede estar usando una versión más reciente de la biblioteca cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], que admite una versión más reciente de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que el servicio de datos al que se tiene acceso.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] aumenta la compatibilidad que proporciona [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] para administrar tales escenarios de versión.  También existe soporte técnico para generar y usar metadatos del modelo de datos con el fin de crear las clases de servicio de datos de cliente cuando el cliente usa una versión distinta de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] de la que usa el servicio de datos.  Para obtener más información, vea el tema sobre [OData: control de versiones del protocolo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
### Negociación de las versiones  
 El servicio de datos se puede configurar para definir la versión más alta del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] que usará el servicio, independientemente de la versión solicitada por el cliente.  Para ello, especifique un valor de la enumeración <xref:System.Data.Services.Common.DataServiceProtocolVersion> para la propiedad <xref:System.Data.Services.DataServiceBehavior.MaxProtocolVersion%2A> de la clase <xref:System.Data.Services.DataServiceBehavior> que usa el servicio de datos.  Para obtener más información, consulta [Configurar el servicio de datos](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Cuando una aplicación usa las bibliotecas de cliente de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para tener acceso a un servicio de datos, las bibliotecas establecen automáticamente estos encabezados en los valores correctos, en función de la versión de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] y de las características que se usan en la aplicación.  De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] utiliza la versión de protocolo más baja que admita la operación solicitada.  
  
 En la siguiente tabla se detallan las versiones de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] y [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)] que incluyen compatibilidad con [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] para versiones específicas del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].  
  
|Versión del protocolo [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]|Compatibilidad introducida en…|  
|----------------------------------------------------------------------------------------|------------------------------------|  
|Versión 1|-   [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] Service Pack 1 \(SP1\)<br />-   Versión 3 de [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)].|  
|Versión 2|-   [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)]<br />-   Actualización a [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] SP1.  Esta actualización se puede descargar e instalar desde el [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkId=158125).<br />-   Versión 4 de [!INCLUDE[silverlight](../../../../includes/silverlight-md.md)].|  
|Versión 3|-   Puede descargar e instalar una versión preliminar que admite la versión 3 de [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] desde el [Centro de descarga de Microsoft](http://go.microsoft.com/fwlink/?LinkId=203885).|  
  
### Versiones de metadatos  
 De forma predeterminada, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] usa la versión 1.1 de CSDL para representar un modelo de datos.  Este siempre es el caso para los modelos de datos basados en un proveedor de reflexión o en un proveedor del servicio de datos personalizados.  No obstante, cuando se define un modelo de datos mediante [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)], la versión devuelta de CSDL es la misma que la que usa [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)].  La versión de CSDL la determina el espacio de nombres del [elemento Schema](http://msdn.microsoft.com/es-es/396074d8-f99c-4f50-a073-68bce848224f).  [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)] la especificación [\[MC\-CSDL\]: Formato de archivo de definición de esquemas conceptuales](http://go.microsoft.com/fwlink/?LinkId=159072).  
  
 El elemento `DataServices` de los metadatos devueltos también contiene un atributo `DataServiceVersion`, que tiene el mismo valor que el encabezado `DataServiceVersion` del mensaje de respuesta.  Las aplicaciones cliente, como el cuadro de diálogo **Agregar referencia de servicio** de [!INCLUDE[vs_current_short](../../../../includes/vs-current-short-md.md)], usan esta información para generar las clases del servicio de datos de cliente que funcionen correctamente con la versión de [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] que hospede el servicio de datos.  Para obtener más información, vea el tema sobre [OData: control de versiones del protocolo](http://go.microsoft.com/fwlink/?LinkId=186071).  
  
## Vea también  
 [Proveedores de servicios de datos](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)   
 [Definir WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)