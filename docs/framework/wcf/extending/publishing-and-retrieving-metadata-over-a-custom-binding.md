---
title: Publicación y recuperación de metadatos a través de un enlace personalizado
ms.date: 03/30/2017
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
ms.openlocfilehash: 33777358262465e9ecbadd75df8abf066bafcd01
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991216"
---
# <a name="publishing-and-retrieving-metadata-over-a-custom-binding"></a>Publicación y recuperación de metadatos a través de un enlace personalizado
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> proporciona soporte para agregar el extremo de metadatos a un servicio. Estos puntos de conexión de metadatos pueden responder a solicitudes HTTP GET en una dirección URL que tenga un `?wsdl` querystring y a las solicitudes de WS-Transfer GET como se define en la especificación WS-MetadataExchange (MEX). Los puntos de conexión MEX implementan el contrato <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=nameWithType>.  
  
## <a name="publishing-metadata-over-a-custom-binding"></a>Publicar los metadatos a través de un enlace personalizado  
 Los puntos de conexión de metadatos HTTP GET y los puntos de conexión de metadatos de HTTPS GET se habilitan estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=nameWithType> o las propiedades <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=nameWithType> en `true`. No se pueden configurar los enlaces para estos extremos.  
  
 El <xref:System.ServiceModel.Description.IMetadataExchange> contrato, sin embargo, se puede utilizar con cualquier punto de conexión, incluyendo aquellos que utilizan enlaces personalizados, porque <xref:System.ServiceModel.Description.IMetadataExchange> puntos de conexión son idénticos a cualquier otro punto de conexión de servicio de Windows Communication Foundation (WCF). Si sabe cómo modificar la configuración de un enlace proporcionado por el sistema, o sabe cómo configurar <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=nameWithType>, puede configurar un enlace para usarlo con un extremo <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## <a name="retrieving-metadata-over-a-custom-binding"></a>Recuperar los metadatos a través de un enlace personalizado  
 Los metadatos se pueden recuperar de los extremos de metadatos HTTP Get y HTTPS Get utilizando solicitudes estándares HTTP o HTTPS GET.  
  
 Para recuperar metadatos de un extremo de metadatos MEX, que generalmente puede utilizar uno de los enlaces MEX estándares admitidos por WCF. Para obtener más información, consulta <xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=nameWithType>. El tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=nameWithType> y la herramienta Svcutil.exe seleccionan automáticamente uno de estos enlaces MEX estándar basándose en la dirección del extremo de metadatos especificado.  
  
 Si un extremo de metadatos MEX utiliza un enlace diferente que uno de los enlaces MEX estándares, puede configurar el enlace utilizado por <xref:System.ServiceModel.Description.MetadataExchangeClient> utilizando código o proporcionando una configuración de extremo de cliente <xref:System.ServiceModel.Description.IMetadataExchange>. La herramienta Svcutil.exe automáticamente carga de su archivo de configuración una configuración de punto de conexión de cliente <xref:System.ServiceModel.Description.IMetadataExchange> que tiene el mismo nombre que el esquema del URI para la dirección del punto de conexión de metadatos.  
  
## <a name="security"></a>Seguridad  
 Al publicar los metadatos a través de un enlace personalizado, asegúrese de que el enlace proporcione el soporte de seguridad que sus metadatos requieren. Por ejemplo, para evitar la divulgación de información y asegurarse de que su cliente tenga el derecho a obtener los metadatos, puede hacer que sus metadatos y su aplicación sean más seguros configurando su punto de conexión <xref:System.ServiceModel.Description.IMetadataExchange> para que requiera autenticación y cifrado. El ejemplo [extremo de metadatos personalizada Secure](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) muestra este escenario.  
  
## <a name="see-also"></a>Vea también

- [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)
- [Enlaces de WS-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)
- [Cómo: Configurar un personalizados WS-Metadata Exchange Binding](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [Cómo: Recuperar metadatos mediante un enlace que no sea - MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
