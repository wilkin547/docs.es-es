---
title: "Credencial personalizada y validaci&#243;n de la credencial | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "validación de la credencial [WCF]"
  - "credenciales [WCF]"
  - "credenciales [WCF], personalizadas"
  - "credenciales [WCF], validación"
  - "credenciales personalizadas [WCF]"
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Credencial personalizada y validaci&#243;n de la credencial
La seguridad en [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] está basada en el intercambio de credenciales entre los servicios y clientes.  La mayoría de los escenarios de seguridad se pueden cumplir utilizando tipos de credencial comunes, como Windows \(Kerberos\), el nombre de usuario y contraseñas y certificados.  Sin embargo, si se exige un nuevo tipo de credencial, los temas en esta sección explican cómo administrar y validar los nuevos tipos.  
  
## En esta sección  
 [Cómo crear un servicio que emplee un validador de certificado personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 Explica cómo personalizar la validación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] mediante la adquisición de la clase <xref:System.IdentityModel.Selectors.X509CertificateValidator>.  
  
 [Tutorial: Crear credenciales de cliente y servicio personalizadas](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 Muestra cómo extender <xref:System.ServiceModel.Description.ClientCredentials> y las clases <xref:System.ServiceModel.Description.ServiceCredentials> para alojar nuevos tipos de credencial.  Esto es lo primero en una serie de temas que habilitan la creación de tipos de credencial personalizados.  
  
 [Cómo crear un proveedor de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 Explica cómo crear un proveedor de token de seguridad para administrar nuevos tipos de credencial y devolver nuevos tokens para la credencial.  Este es el segundo tema en la serie.  
  
 [Cómo: Crear un autenticador de tokens de seguridad personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 Explica cómo crear un autenticador personalizado para autenticar un nuevo tipo de credencial.  Este es el tercer tema en la serie.  
  
## Referencia  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## Secciones relacionadas  
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## Vea también  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)