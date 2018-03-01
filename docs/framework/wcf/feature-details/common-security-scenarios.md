---
title: Escenarios de seguridad comunes
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
caps.latest.revision: 
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: d8881768d66e95ce1391ce1be1663bdc3107a347
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="common-security-scenarios"></a>Escenarios de seguridad comunes
Los temas de esta sección catalogan varias configuraciones posibles de seguridad de cliente y servicio. Las configuraciones varían según varios factores. Por ejemplo, si un servicio o cliente está en una intranet o si Windows o transporte (como HTTPS) proporciona la seguridad.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cliente y servicio de Internet no protegidos](../../../../docs/framework/wcf/feature-details/internet-unsecured-client-and-service.md)  
 Un ejemplo de un cliente y servicio público y no protegido.  
  
 [Cliente y servicio de intranet no protegidos](../../../../docs/framework/wcf/feature-details/intranet-unsecured-client-and-service.md)  
 Un servicio básico de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] desarrollado para proporcionar información sobre una red privada segura a una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Seguridad del transporte con la autenticación básica](../../../../docs/framework/wcf/feature-details/transport-security-with-basic-authentication.md)  
 La aplicación permite a los clientes iniciar sesión al utilizar autenticación personalizada.  
  
 [Seguridad del transporte con la autenticación de Windows](../../../../docs/framework/wcf/feature-details/transport-security-with-windows-authentication.md)  
 Muestra un cliente y servicio protegidos por seguridad de Windows.  
  
 [Seguridad del transporte con clientes anónimos](../../../../docs/framework/wcf/feature-details/transport-security-with-an-anonymous-client.md)  
 Este escenario utiliza la seguridad de transporte (como HTTPS) para garantizar la confidencialidad y la integridad.  
  
 [Seguridad del transporte con autenticación de certificados](../../../../docs/framework/wcf/feature-details/transport-security-with-certificate-authentication.md)  
 Muestra a un cliente y servicio protegidos por un certificado.  
  
 [Seguridad de mensajes con clientes anónimos](../../../../docs/framework/wcf/feature-details/message-security-with-an-anonymous-client.md)  
 Muestra un cliente y el servicio protegido por el modo de seguridad de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [Seguridad de mensajes con un cliente de nombres de usuario](../../../../docs/framework/wcf/feature-details/message-security-with-a-user-name-client.md)  
 El cliente es una aplicación de Windows Forms que permite a los clientes iniciar sesión al utilizar un nombre de usuario y contraseña del dominio.  
  
 [Seguridad de mensajes con un cliente de certificado](../../../../docs/framework/wcf/feature-details/message-security-with-a-certificate-client.md)  
 Los servidores tienen certificados y cada cliente tiene un certificado. Un contexto de seguridad se establece a través de la negociación de Seguridad de la capa de transporte (TLS).  
  
 [Seguridad de mensajes con un cliente de Windows](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client.md)  
 Una variación del cliente del certificado. Los servidores tienen certificados y cada cliente tiene un certificado. Un contexto de seguridad se establece a través de la negociación de TLS.  
  
 [Seguridad de mensajes con un cliente de Windows sin negociación de credenciales](../../../../docs/framework/wcf/feature-details/message-security-with-a-windows-client-without-credential-negotiation.md)  
 Muestra un cliente y el servicio protegidos por un dominio de Kerberos.  
  
 [Seguridad de mensajes con certificados mutuos](../../../../docs/framework/wcf/feature-details/message-security-with-mutual-certificates.md)  
 Los servidores tienen certificados y cada cliente tiene un certificado. El certificado de servidor se distribuye con la aplicación y está disponible fuera de banda.  
  
 [Seguridad de mensajes con tokens emitidos](../../../../docs/framework/wcf/feature-details/message-security-with-issued-tokens.md)  
 La seguridad federada que permite el establecimiento de confianza entre dominios independientes.  
  
 [Subsistema de confianza](../../../../docs/framework/wcf/feature-details/trusted-subsystem.md)  
 Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red. Los servicios Web tienen acceso a recursos adicionales (como bases de datos u otros servicios Web) que se deben proteger.  
  
## <a name="reference"></a>Referencia  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Información general sobre seguridad](../../../../docs/framework/wcf/feature-details/security-overview.md)  
  
 [Seguridad](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [Enlaces y seguridad](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [Protección de servicios y clientes](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
 [Autenticación](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [Autorización](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
 [Federación y tokens emitidos](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [Auditoría](../../../../docs/framework/wcf/feature-details/auditing-security-events.md)  
  
## <a name="see-also"></a>Vea también  
 [Orientación de seguridad y procedimientos recomendados](../../../../docs/framework/wcf/feature-details/security-guidance-and-best-practices.md)  
 [Modelo de seguridad de Windows Server AppFabric](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
