---
description: Más información acerca de cómo ampliar la seguridad
title: Extensión de la seguridad
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
ms.openlocfilehash: 8dd514e16106ac5cdae072d92c7de66cefd39fe4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99685730"
---
# <a name="extending-security"></a>Extensión de la seguridad

Para dar cabida a nuevos tipos de notificaciones y tokens personalizados, puede extender la infraestructura de seguridad de Windows Communication Foundation (WCF). Los temas de esta sección le muestran cómo hacerlo.  
  
## <a name="in-this-section"></a>En esta sección  
  
 [Credencial personalizada y validación de la credencial](custom-credential-and-credential-validation.md)  
 Explica cómo se utiliza el modelo de identidad al validar las credenciales personalizadas.  
  
 [Tokens personalizados](custom-tokens.md)  
 Los tokens emitidos por un servicio de token de seguridad (STS) normalmente son tokens de SAML. En este tema se explica cómo crear un tipo de token personalizado.  
  
 [Autorización personalizada](custom-authorization.md)  
 Explica cómo implementar la autorización personalizada.  
  
 [Invalidación de la identidad de un servicio para la autenticación](overriding-the-identity-of-a-service-for-authentication.md)  
 Describe cómo invalidar la identidad de un servicio para la autenticación.  
  
 [Procedimiento para crear un comprobador de identidad de cliente personalizado](how-to-create-a-custom-client-identity-verifier.md)  
 Muestra cómo validar una identidad del extremo personalizada.  
  
 [Procedimiento para usar diferentes certificados X.509 para la firma y el cifrado](how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 Los mensajes normalmente se firman y cifran con un certificado único. En este tema se explica cómo se pueden utilizar dos certificados, cuando se requiere.  
  
 [Procedimiento para cambiar el proveedor criptográfico para la clave privada de un certificado X.509](change-cryptographic-provider-x509-certificate-private-key.md)  
 Explica cómo cambiar el proveedor de servicios criptográficos que se usa para proporcionar la clave privada de un certificado X. 509 y cómo integrar el proveedor en el marco de Windows Communication Foundation (WCF).  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Seguridad](../feature-details/security.md)  
  
 [Programación básica de WCF](../basic-wcf-programming.md)  
  
## <a name="see-also"></a>Vea también

- [Información general sobre seguridad](../feature-details/security-overview.md)
