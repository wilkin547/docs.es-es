---
title: Federación y tokens emitidos
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
ms.openlocfilehash: bdbd5c49197b65816da9b0f2c87d97afb893d79f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43788109"
---
# <a name="federation-and-issued-tokens"></a>Federación y tokens emitidos
Con Windows Communication Foundation (WCF), puede crear a clientes que se comunican de forma segura con servicios que implementan las especificaciones de WS-Federation y WS-Trust. Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.  
  
## <a name="in-this-section"></a>En esta sección  
 [Federación](../../../../docs/framework/wcf/feature-details/federation.md)  
 Proporciona información general sobre la federación.  
  
 [Federación y confianza](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.  
  
 [Creación de un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 Describe los fundamentos de la creación de un cliente federado con WCF.  
  
 [Configuración de las credenciales en un servicio de federación](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 Describe los pasos de creación de un servicio federado.  
  
 [Creación de un WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 Describe cómo configurar los clientes y servicios que utilizan el `WSFederationHttpBinding`.  
  
 [Creación de un servicio de token de seguridad](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 Describe los pasos de creación de un servicio de token de seguridad.  
  
 [Tokens y notificaciones del Lenguaje de marcado de aserción de seguridad (SAML)](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 Describe tokens del lenguaje de marcado de aserción de seguridad (SAML), que son extensibles y le permiten crear tipos de demanda eficaces.  
  
 [Configuración de un emisor local](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 Describe cómo crear un emisor local de tokens de seguridad.  
  
 [Deshabilitar sesiones seguras en WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
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
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [Tokens personalizados](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [Modelo de seguridad de Windows Server AppFabric](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
