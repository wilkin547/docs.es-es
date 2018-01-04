---
title: "Publicación de metadatos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 86d9eb8e7e7c78f091deea55322cbef6e6d0f3c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="publishing-metadata"></a>Publicación de metadatos
Los servicios de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] publican metadatos mediante la publicación de uno o más extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio a través de configuración o código imperativo.  
  
## <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos  
 Para publicar extremos de metadatos para un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], debe agregar primero el comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior> al servicio. Agregar una instancia <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> permite a su servicio exponer los extremos de metadatos. Una vez que agregue el comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, puede exponer extremos de metadatos que admitan el protocolo MEX o que respondan a solicitudes HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> usa un <xref:System.ServiceModel.Description.WsdlExporter> para exportar metadatos para todos los extremos de servicio al servicio. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]exportación de metadatos de un servicio, consulte [exportar e importar metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> agrega una instancia <xref:System.ServiceModel.Description.ServiceMetadataExtension> como una extensión a su host de servicio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> proporciona la implementación para los protocolos de publicación de metadatos. También puede utilizar <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> para obtener los metadatos del servicio en tiempo de ejecución mediante la obtención de acceso a la propiedad <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Extremos de metadatos MEX  
 Para agregar los extremos de metadatos que usan el protocolo MEX, agregue extremos de servicio a su host de servicio que usen el contrato de servicio de `IMetadataExchange`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] incluye una interfaz <xref:System.ServiceModel.Description.IMetadataExchange> con este nombre de contrato de servicio que se puede usar como parte del modelo de programación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Los extremos de WS-MetadataExchange o los extremos MEX, pueden utilizar uno de los cuatro enlaces predeterminados que los métodos de generador estáticos exponen en la clase <xref:System.ServiceModel.Description.MetadataExchangeBindings> para coincidir con los enlaces predeterminados utilizados por herramientas de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] como Svcutil.exe. También puede configurar extremos de metadatos MEX mediante su propio enlace personalizado.  
  
### <a name="http-get-metadata-endpoints"></a>Extremos de metadatos HTTP GET  
 Para agregar un extremo de metadatos a su servicio que responda a solicitudes HTTP/GET, establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en el <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`. También puede configurar un extremo de metadatos que utilice HTTPS estableciendo la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> del <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Publicación de metadatos para un servicio mediante un archivo de configuración](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] para publicar metadatos de tal modo que los clientes puedan recuperar los metadatos mediante una solicitud HTTP/GET o WS-MetadataExchange mediante la cadena de consulta `?wsdl`.  
  
 [Publicación de metadatos para un servicio mediante código](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] en código de tal modo que los clientes puedan recuperar los datos mediante una solicitud HTTP/GET o WS-MetadataExchange mediante la cadena de consulta `?wsdl`.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Vea también  
 [Exportación e importación de metadatos](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
