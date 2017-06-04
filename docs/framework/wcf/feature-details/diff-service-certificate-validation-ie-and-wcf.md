---
title: "Diferencias entre la validaci&#243;n de certificados de servicio realizada por Internet Explorer y WCF | Microsoft Docs"
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
  - "certificados [WCF], validación de certificado de servicio"
  - "validación de certificado de servicio [WCF]"
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Diferencias entre la validaci&#243;n de certificados de servicio realizada por Internet Explorer y WCF
Debido a la diferencia entre las maneras en que Internet Explorer e [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] validan los certificados del servicio cuando se utilizan HTTPS, es posible que Internet Explorer no pueda tener acceso a la página de Ayuda o el Lenguaje de descripción de servicios Web \(WSDL\) de un servicio aunque un cliente [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] pueda enviar correctamente los mensajes a los extremos de servicio.Esto es porque Internet Explorer comprueba si el certificado del servicio tiene los identificadores de objetos `ServerAuthentication` \(OID\) en las marcas de uso mejoradas, mientras que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] no exige este tipo de restricción.Si Internet Explorer no puede tener acceso a la página de Ayuda del servicio o al WSDL para el servicio, utilice [Herramienta de utilidad de metadatos de ServiceModel \(Svcutil.exe\)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para tener acceso a los metadatos del servicio.  
  
## Vea también  
 [Diferencias en la validación de certificados entre HTTPS, SSL a través de TCP, y seguridad SOAP](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)   
 [Cómo recuperar los metadatos e implementar un servicio conforme](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)