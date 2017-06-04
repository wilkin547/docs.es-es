---
title: "Extensi&#243;n de la seguridad | Microsoft Docs"
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
  - "seguridad [WCF], extender"
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: 23
author: "BrucePerlerMS"
ms.author: "bruceper"
manager: "mbaldwin"
caps.handback.revision: 23
---
# Extensi&#243;n de la seguridad
Para alojar nuevos tipos de notificación y tokens personalizados, puede extender la infraestructura de seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Los temas de esta sección le muestran cómo hacerlo.  
  
## En esta sección  
 [Security Architecture](http://msdn.microsoft.com/es-es/16593476-d36a-408d-808c-ae6fd483e28f)  
 Describe la arquitectura del sistema de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Credencial personalizada y validación de la credencial](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.  
  
 [Tokens personalizados](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 Los tokens emitidos por un servicio de token de seguridad \(STS\) normalmente son tokens de SAML.En este tema se explica cómo crear un tipo de token personalizado.  
  
 [Autorización personalizada](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 Explica cómo implementar la autorización personalizada.  
  
 [Invalidación de la identidad de un servicio para la autenticación](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 Describe cómo invalidar la identidad de un servicio para la autenticación.  
  
 [Cómo crear un comprobador de identidad de cliente personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 Muestra cómo validar una identidad del extremo personalizada.  
  
 [Cómo: Utilizar diferentes certificados X.509 para la firma y el cifrado](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Los mensajes normalmente se firman y cifran con un certificado único.En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.  
  
 [Cómo: Cambiar el proveedor criptográfico para la clave privada de un certificado X.509](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 Explica cómo cambiar el proveedor criptográfico utilizado para proporcionar la clave privada de un certificado X.509 y cómo integrar el proveedor en el marco [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## Referencia  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## Secciones relacionadas  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)