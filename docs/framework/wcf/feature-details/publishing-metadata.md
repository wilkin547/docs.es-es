---
title: Publicación de metadatos
ms.date: 03/30/2017
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 97836cef12cd1f220e97d2c38d2dca1b878d7484
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183090"
---
# <a name="publishing-metadata"></a>Publicación de metadatos
Servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o varios extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio a través de configuración o código imperativo.  
  
## <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos  
 Para publicar extremos de metadatos para un servicio WCF, primero debe agregar el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamiento al servicio del servicio. Agregar una instancia <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> permite a su servicio exponer los puntos de conexión de metadatos. Una vez que agregue el comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, puede exponer extremos de metadatos que admitan el protocolo MEX o que respondan a solicitudes HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> usa un <xref:System.ServiceModel.Description.WsdlExporter> para exportar metadatos para todos los extremos de servicio al servicio. Para obtener más información acerca de cómo exportar metadatos desde un servicio, consulte [exportar e importar metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> agrega una instancia <xref:System.ServiceModel.Description.ServiceMetadataExtension> como una extensión a su host de servicio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> proporciona la implementación para los protocolos de publicación de metadatos. También puede utilizar <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> para obtener los metadatos del servicio en tiempo de ejecución mediante la obtención de acceso a la propiedad <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Extremos de metadatos MEX  
 Para agregar los extremos de metadatos que usan el protocolo MEX, agregue extremos de servicio a su host de servicio que usen el contrato de servicio de `IMetadataExchange`. WCF incluye un <xref:System.ServiceModel.Description.IMetadataExchange> interfaz con este nombre de contrato de servicio que puede usar como parte del modelo de programación de WCF. Los puntos de conexión de WS-MetadataExchange o los puntos de conexión MEX, pueden usar uno de los cuatro enlaces predeterminados que los métodos de generador estáticos exponen en el <xref:System.ServiceModel.Description.MetadataExchangeBindings> clase para que coincida con los enlaces predeterminados utilizados por herramientas WCF como Svcutil.exe. También puede configurar puntos de conexión de metadatos MEX mediante su propio enlace personalizado.  
  
### <a name="http-get-metadata-endpoints"></a>puntos de conexión de metadatos HTTP GET  
 Para agregar un punto de conexión de metadatos a su servicio que responda a solicitudes HTTP/GET, establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en el <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`. También puede configurar un extremo de metadatos que utilice HTTPS estableciendo la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> del <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Filtrar para publicar metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio WCF para publicar metadatos para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
 [Filtrar para publicar metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes pueden recuperar los metadatos mediante un WS-MetadataExchange o una solicitud HTTP/GET usando el `?wsdl` cadena de consulta.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Vea también

- [Exportación e importación de metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
