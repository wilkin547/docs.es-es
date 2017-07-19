---
title: "Integraci&#243;n en aplicaciones COM | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "COM [WCF]"
  - "COM [WCF], Integración en Windows Communication Foundation"
  - "WCF, Integración de COM"
  - "WCF, reutilizar código"
  - "Windows Communication Foundation, Integración de COM"
  - "Windows Communication Foundation, reutilizar código"
ms.assetid: c98bda3e-6779-419e-8e6d-9aa94053026d
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Integraci&#243;n en aplicaciones COM
Los servicios [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] se pueden integrar directamente en su código existente mediante el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  El moniker de servicio se puede utilizar a partir de una gama amplia de entornos de desarrollo basados en COM, como Office VBA, Visual Basic 6.0 o Visual C\+\+ 6.0.  
  
## En esta sección  
 [Integración con la información general de las aplicaciones COM](../../../../docs/framework/wcf/feature-details/integrating-with-com-applications-overview.md)  
 Proporciona información general de las partes principales del proceso de la integración.  
  
 [Cómo registrar y configurar un moniker de servicio](../../../../docs/framework/wcf/feature-details/how-to-register-and-configure-a-service-moniker.md)  
 Para utilizar el moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] dentro de una aplicación COM, registre los tipos de atributos necesarios con COM y configure la aplicación COM y el moniker con la configuración de enlace necesaria.  
  
 [Cómo utilizar el moniker de servicio de Windows Communication Foundation sin registrarse](../../../../docs/framework/wcf/feature-details/use-the-wcf-service-moniker-without-registration.md)  
 Explica cómo obtener la definición del contrato en forma de un documento de Lenguaje de Definición de servicios Web \(WSDL\) o de un extremo de WS\-MetadataExchange.  
  
 [Cómo: Utilizar un moniker de servicio con contratos WSDL](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-wsdl-contracts.md)  
 Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker de WSDL [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Cómo: Utilizar un moniker de servicio con contratos de intercambio de metadatos](../../../../docs/framework/wcf/feature-details/how-to-use-a-service-moniker-with-metadata-exchange-contracts.md)  
 Describe cómo llamar a un ejemplo [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante un moniker [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que especifica un extremo de Mex.  
  
 [Cómo especificar las credenciales de seguridad de los canales](../../../../docs/framework/wcf/feature-details/how-to-specify-channel-security-credentials.md)  
 El moniker del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite la interfaz `IChannelCredentials` que permite una serie de métodos alternativos para especificar las credenciales del canal.  
  
## Referencia  
 <xref:System.ServiceModel>  
  
## Vea también  
 [Integración en aplicaciones COM\+](../../../../docs/framework/wcf/feature-details/integrating-with-com-plus-applications.md)