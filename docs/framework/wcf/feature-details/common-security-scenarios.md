---
title: Escenarios de seguridad comunes
ms.date: 03/30/2017
helpviewer_keywords:
- security [WCF], scenarios
ms.assetid: 201923b5-5162-4a8a-8d4c-e7bd242748d5
ms.openlocfilehash: 21c8279890d1d1cf746e98f875efb6b1ff869c73
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295085"
---
# <a name="common-security-scenarios"></a>Escenarios de seguridad comunes

Los temas de esta sección catalogan varias configuraciones posibles de seguridad de cliente y servicio. Las configuraciones varían según varios factores. Por ejemplo, si un servicio o cliente está en una intranet o si Windows o transporte (como HTTPS) proporciona la seguridad.  
  
## <a name="in-this-section"></a>En esta sección  

 [Cliente y servicio de Internet no protegidos](internet-unsecured-client-and-service.md)  
 Un ejemplo de un cliente y servicio público y no protegido.  
  
 [Cliente y servicio de intranet no protegidos](intranet-unsecured-client-and-service.md)  
 Un servicio básico de Windows Communication Foundation (WCF) desarrollado para proporcionar información sobre una red privada segura a una aplicación WCF.  
  
 [Seguridad de transporte con autenticación básica](transport-security-with-basic-authentication.md)  
 La aplicación permite a los clientes iniciar sesión al utilizar autenticación personalizada.  
  
 [Seguridad del transporte con la autenticación de Windows](transport-security-with-windows-authentication.md)  
 Muestra un cliente y servicio protegidos por seguridad de Windows.  
  
 [Seguridad del transporte con clientes anónimos](transport-security-with-an-anonymous-client.md)  
 Este escenario utiliza la seguridad de transporte (como HTTPS) para garantizar la confidencialidad y la integridad.  
  
 [Seguridad del transporte con autenticación de certificados](transport-security-with-certificate-authentication.md)  
 Muestra a un cliente y servicio protegidos por un certificado.  
  
 [Seguridad de mensajes con clientes anónimos](message-security-with-an-anonymous-client.md)  
 Muestra un cliente y servicio protegido por la seguridad de mensajes de WCF.  
  
 [Seguridad de los mensajes con un cliente de nombres de usuario](message-security-with-a-user-name-client.md)  
 El cliente es una aplicación de Windows Forms que permite a los clientes iniciar sesión al utilizar un nombre de usuario y contraseña del dominio.  
  
 [Seguridad de mensajes con un cliente de certificado](message-security-with-a-certificate-client.md)  
 Los servidores tienen certificados y cada cliente tiene un certificado. Un contexto de seguridad se establece a través de la negociación de Seguridad de la capa de transporte (TLS).  
  
 [Seguridad del mensaje con un cliente de Windows](message-security-with-a-windows-client.md)  
 Una variación del cliente del certificado. Los servidores tienen certificados y cada cliente tiene un certificado. Un contexto de seguridad se establece a través de la negociación de TLS.  
  
 [Seguridad de los mensajes con un cliente de Windows sin negociación de credenciales](message-security-with-a-windows-client-without-credential-negotiation.md)  
 Muestra un cliente y el servicio protegidos por un dominio de Kerberos.  
  
 [Seguridad de mensajes con certificados mutuos](message-security-with-mutual-certificates.md)  
 Los servidores tienen certificados y cada cliente tiene un certificado. El certificado de servidor se distribuye con la aplicación y está disponible fuera de banda.  
  
 [Seguridad de los mensajes con tokens emitidos](message-security-with-issued-tokens.md)  
 La seguridad federada que permite el establecimiento de confianza entre dominios independientes.  
  
 [Subsistema de confianza](trusted-subsystem.md)  
 Un cliente obtiene acceso a uno o varios servicios Web distribuidos a través de una red. Los servicios Web tienen acceso a recursos adicionales (como bases de datos u otros servicios Web) que se deben proteger.  
  
## <a name="reference"></a>Referencia  

 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a>Secciones relacionadas  

 [Autorización](authorization-in-wcf.md)  
  
 [Información general sobre seguridad](security-overview.md)  
  
 [Seguridad](security.md)  
  
 [Enlaces y seguridad](bindings-and-security.md)  
  
 [Protección de servicios y clientes](securing-services-and-clients.md)  
  
 [Autenticación](authentication-in-wcf.md)  
  
 [Autorización](authorization-in-wcf.md)  
  
 [Federación y tokens emitidos](federation-and-issued-tokens.md)  
  
 [Auditoría](auditing-security-events.md)  
  
## <a name="see-also"></a>Vea también

- [Orientación de seguridad y procedimientos recomendados](security-guidance-and-best-practices.md)
- [Modelo de seguridad para Windows Server App Fabric](/previous-versions/appfabric/ee677202(v=azure.10))
