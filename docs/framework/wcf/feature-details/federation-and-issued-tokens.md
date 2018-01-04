---
title: "Federación y tokens emitidos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a>Federación y tokens emitidos
Con [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], puede crear clientes que se comuniquen de manera segura con servicios que implementan las especificaciones WS-Federation y WS-Trust. Las especificaciones utilizan XML, SOAP y lenguaje de descripción de servicios Web (WSDL) para proporcionar mecanismos que habilitan la autenticación y autorización en los diferentes dominios de confianza.  
  
## <a name="in-this-section"></a>En esta sección  
 [Federación](../../../../docs/framework/wcf/feature-details/federation.md)  
 Proporciona información general sobre la federación.  
  
 [Federación y confianza](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 Enumera los problemas de diseño a tener en cuenta al crear servicios o clientes federados.  
  
 [Creación de un cliente federado](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 Describe los fundamentos de la creación de un cliente federado con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
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
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
