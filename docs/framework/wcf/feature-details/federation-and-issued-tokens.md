---
title: Federación y tokens emitidos
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: 0ab3d6bad717e71901b4d94c99f1c48f99d8675e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255525"
---
# <a name="federation-and-issued-tokens"></a>Federación y tokens emitidos

Con Windows Communication Foundation (WCF), puede crear clientes que se comuniquen de forma segura con servicios que implementan las especificaciones de WS-Federation y WS-Trust. Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.  
  
## <a name="in-this-section"></a>En esta sección  

 [Federación](federation.md)  
 Proporciona información general sobre la federación.  
  
 [Federación y confianza](federation-and-trust.md)  
 Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.  
  
 [Procedimiento para crear un cliente federado](how-to-create-a-federated-client.md)  
 Describe los conceptos básicos de la creación de un cliente federado con WCF.  
  
 [Procedimiento para configurar las credenciales en un servicio de federación](how-to-configure-credentials-on-a-federation-service.md)  
 Describe los pasos de creación de un servicio federado.  
  
 [Procedimiento para crear un WSFederationHttpBinding](how-to-create-a-wsfederationhttpbinding.md)  
 Describe cómo configurar los clientes y servicios que utilizan el `WSFederationHttpBinding`.  
  
 [Procedimiento para crear un servicio de token de seguridad](how-to-create-a-security-token-service.md)  
 Describe los pasos de creación de un servicio de token de seguridad.  
  
 [Tokens y notificaciones del Lenguaje de marcado de aserción de seguridad (SAML)](saml-tokens-and-claims.md)  
 Describe tokens del lenguaje de marcado de aserción de seguridad (SAML), que son extensibles y le permiten crear tipos de demanda eficaces.  
  
 [Procedimiento para configurar un emisor local](how-to-configure-a-local-issuer.md)  
 Describe cómo crear un emisor local de tokens de seguridad.  
  
 [Procedimiento para deshabilitar sesiones seguras en WSFederationHttpBinding](how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Describe cómo deshabilitar las sesiones seguras en un `WSFederationHttpBinding`. La deshabilitación de las sesiones seguras es necesaria al crear una granja de servidores web que requiere una sesión para cada cliente.  
  
## <a name="reference"></a>Referencia  

 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a>Vea también

- [Autorización](authorization-in-wcf.md)
- [Tokens personalizados](../extending/custom-tokens.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
