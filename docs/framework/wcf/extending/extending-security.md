---
title: "Extensión de la seguridad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ecbbaac0023ca528967abe2cb60c3d790772fb2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="extending-security"></a>Extensión de la seguridad
Para alojar nuevos tipos de notificación y tokens personalizados, puede extender la infraestructura de seguridad de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]. Los temas de esta sección le muestran cómo hacerlo.  
  
## <a name="in-this-section"></a>En esta sección  
 [Arquitectura de seguridad](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)  
 Describe la arquitectura del sistema de seguridad [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Credencial personalizada y validación de la credencial](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.  
  
 [Tokens personalizados](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML. En este tema se explica cómo crear un tipo de token personalizado.  
  
 [Autorización personalizada](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 Explica cómo implementar la autorización personalizada.  
  
 [Invalidación de la identidad de un servicio para la autenticación](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 Describe cómo invalidar la identidad de un servicio para la autenticación.  
  
 [Creación de un comprobador de identidad de cliente personalizado](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 Muestra cómo validar una identidad del punto de conexión personalizada.  
  
 [Uso de diferentes certificados X.509 para la firma y el cifrado](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Los mensajes normalmente se firman y cifran con un certificado único. En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.  
  
 [Cambio de proveedor criptográfico para la clave privada de un certificado X.509](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 Explica cómo cambiar el proveedor criptográfico utilizado para proporcionar la clave privada de un certificado X.509 y cómo integrar el proveedor en el marco [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)
