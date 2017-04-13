---
title: "Publicaci&#243;n y recuperaci&#243;n de metadatos a trav&#233;s de un enlace personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 904e11b4-d90e-45c6-9ee5-c3472c90008c
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Publicaci&#243;n y recuperaci&#243;n de metadatos a trav&#233;s de un enlace personalizado
<xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=fullName> proporciona soporte para agregar el extremo de metadatos a un servicio.Estos extremos de metadatos pueden responder a solicitudes HTTP GET en una dirección URL que tiene una querystring `?wsdl` y a solicitudes WS\-Transfer GET como se define en la especificación de WS\-MetadataExchange \(MEX\).Los extremos MEX implementan el contrato <xref:System.ServiceModel.Description.IMetadataExchange?displayProperty=fullName>.  
  
## Publicar los metadatos a través de un enlace personalizado  
 Los extremos de metadatos HTTP GET y los extremos de metadatos de HTTPS GET se habilitan estableciendo <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A?displayProperty=fullName> o las propiedades <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A?displayProperty=fullName> en `true`.No se pueden configurar los enlaces para estos extremos.  
  
 Sin embargo, el contrato <xref:System.ServiceModel.Description.IMetadataExchange> se puede utilizar con cualquier extremo, incluyendo aquellos que utilizan enlaces personalizados, porque los extremos <xref:System.ServiceModel.Description.IMetadataExchange> son idénticos a cualquier otro extremo de servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Si sabe cómo modificar la configuración de un enlace proporcionado por el sistema, o sabe cómo configurar <xref:System.ServiceModel.Channels.CustomBinding?displayProperty=fullName>, puede configurar un enlace para usarlo con un extremo <xref:System.ServiceModel.Description.IMetadataExchange>.  
  
## Recuperar los metadatos a través de un enlace personalizado  
 Los metadatos se pueden recuperar de los extremos de metadatos HTTP Get y HTTPS Get utilizando solicitudes estándares HTTP o HTTPS GET.  
  
 Para recuperar los metadatos de un extremo de metadatos MEX, generalmente puede utilizar uno de los enlaces MEX estándares soportados por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].[!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<xref:System.ServiceModel.Description.MetadataExchangeBindings?displayProperty=fullName>.El tipo <xref:System.ServiceModel.Description.MetadataExchangeClient?displayProperty=fullName> y la herramienta Svcutil.exe seleccionan automáticamente uno de estos enlaces MEX estándar basándose en la dirección del extremo de metadatos especificado.  
  
 Si un extremo de metadatos MEX utiliza un enlace diferente que uno de los enlaces MEX estándares, puede configurar el enlace utilizado por <xref:System.ServiceModel.Description.MetadataExchangeClient> utilizando código o proporcionando una configuración de extremo de cliente <xref:System.ServiceModel.Description.IMetadataExchange>.La herramienta Svcutil.exe automáticamente carga de su archivo de configuración una configuración de extremo de cliente <xref:System.ServiceModel.Description.IMetadataExchange> que tiene el mismo nombre que el esquema del URI para la dirección del extremo de metadatos.  
  
## Seguridad  
 Al publicar los metadatos a través de un enlace personalizado, asegúrese de que el enlace proporcione el soporte de seguridad que sus metadatos requieren.Por ejemplo, para evitar la divulgación de información y asegurarse de que su cliente tenga el derecho a obtener los metadatos, puede hacer que sus metadatos y su aplicación sean más seguros configurando su extremo <xref:System.ServiceModel.Description.IMetadataExchange> para que requiera autenticación y cifrado.El ejemplo [Extremo personalizado de metadatos seguros](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) muestra este escenario.  
  
## Vea también  
 [Seguridad de servicios](../../../../docs/framework/wcf/securing-services.md)   
 [Enlaces de WS\-MetadataExchange](../../../../docs/framework/wcf/extending/ws-metadataexchange-bindings.md)   
 [Cómo: Configurar un enlace de WS\-Metadata Exchange Binding personalizado](../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)   
 [Cómo: Recuperar metadatos mediante un enlace que no sea MEX](../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)