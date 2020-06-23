---
title: Publicación de metadatos
description: Obtenga información sobre cómo los servicios WCF publican metadatos mediante la publicación de uno o más extremos de metadatos, lo que hace que los metadatos estén disponibles mediante protocolos estándar.
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 2aa6d877db4e5b09b4c594e6e87b63fb6c04703b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244964"
---
# <a name="publishing-metadata"></a>Publicación de metadatos
Los servicios Windows Communication Foundation (WCF) publican metadatos mediante la publicación de uno o más extremos de metadatos. La publicación de metadatos de servicio pone los metadatos a disposición mediante protocolos estandarizados, como WS-MetadataExchange (MEX) y solicitudes HTTP/GET. Los extremos de metadatos son similares a otros extremos de servicio en cuanto que tienen una dirección, un enlace y un contrato, y se pueden agregar a un host del servicio a través de configuración o código imperativo.  
  
## <a name="publishing-metadata-endpoints"></a>Publicación de puntos de conexión de metadatos  
 Para publicar extremos de metadatos para un servicio WCF, primero debe agregar el <xref:System.ServiceModel.Description.ServiceMetadataBehavior> comportamiento del servicio al servicio. Agregar una instancia <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> permite a su servicio exponer los puntos de conexión de metadatos. Una vez que agregue el comportamiento del servicio <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>, puede exponer extremos de metadatos que admitan el protocolo MEX o que respondan a solicitudes HTTP/GET.  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> usa un <xref:System.ServiceModel.Description.WsdlExporter> para exportar metadatos para todos los extremos de servicio al servicio. Para obtener más información acerca de la exportación de metadatos desde un servicio, vea [exportar e importar metadatos](exporting-and-importing-metadata.md).  
  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> agrega una instancia <xref:System.ServiceModel.Description.ServiceMetadataExtension> como una extensión a su host de servicio. <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> proporciona la implementación para los protocolos de publicación de metadatos. También puede utilizar <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> para obtener los metadatos del servicio en tiempo de ejecución mediante la obtención de acceso a la propiedad <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>.  
  
### <a name="mex-metadata-endpoints"></a>Extremos de metadatos MEX  
 Para agregar los extremos de metadatos que usan el protocolo MEX, agregue extremos de servicio a su host de servicio que usen el contrato de servicio de `IMetadataExchange`. WCF incluye una <xref:System.ServiceModel.Description.IMetadataExchange> interfaz con este nombre de contrato de servicio que puede usar como parte del modelo de programación de WCF. Los extremos de WS-MetadataExchange o los extremos MEX, pueden utilizar uno de los cuatro enlaces predeterminados que los métodos de generador estáticos exponen en la <xref:System.ServiceModel.Description.MetadataExchangeBindings> clase para que coincidan con los enlaces predeterminados utilizados por herramientas de WCF como Svcutil.exe. También puede configurar puntos de conexión de metadatos MEX mediante su propio enlace personalizado.  
  
### <a name="http-get-metadata-endpoints"></a>puntos de conexión de metadatos HTTP GET  
 Para agregar un punto de conexión de metadatos a su servicio que responda a solicitudes HTTP/GET, establezca la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> en el <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`. También puede configurar un extremo de metadatos que utilice HTTPS estableciendo la propiedad <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> del <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> en `true`.  
  
## <a name="in-this-section"></a>En esta sección  
 [Procedimiento para publicar metadatos para un servicio mediante un archivo de configuración](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Muestra cómo configurar un servicio WCF para publicar metadatos de modo que los clientes puedan recuperar los metadatos mediante una solicitud de WS-MetadataExchange o HTTP/GET usando la `?wsdl` cadena de consulta.  
  
 [Procedimiento para publicar metadatos para un servicio mediante código](how-to-publish-metadata-for-a-service-using-code.md)  
 Muestra cómo habilitar la publicación de metadatos para un servicio WCF en el código para que los clientes puedan recuperar los metadatos mediante una solicitud de WS-MetadataExchange o HTTP/GET usando la `?wsdl` cadena de consulta.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Vea también

- [Exportación e importación de metadatos](exporting-and-importing-metadata.md)
