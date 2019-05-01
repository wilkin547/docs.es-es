---
title: Guía de interoperabilidad de los protocolos de servicios web
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: 647212558b6be38e9b30239f7fb71213e6eb7d86
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62050355"
---
# <a name="web-services-protocols-interoperability-guide"></a>Guía de interoperabilidad de los protocolos de servicios web
Windows Communication Foundation (WCF) se implementa una serie de protocolos de servicios Web. Muchos de estos protocolos incluyen distintas opciones y puntos de extensibilidad que son decisión del responsable de la implementación. En este tema se proporciona una lista de protocolos de servicios Web que WCF implementa. Otros temas incluidos en esta sección proporcionan información detallada acerca de la implementación de cada protocolo admitido.  
  
## <a name="web-services-protocols-implemented-by-wcf"></a>Protocolos de servicios web implementados por WCF  
 WCF proporciona compatibilidad para protocolos de infraestructura de Web services (WS) a través de canales y protocolos de aplicación a través de la característica de contratos de servicios Web. La interoperabilidad de los protocolos de aplicación se consigue mediante el lenguaje de descripción Esquema XML 1.0 (XSD) y el Lenguaje de descripción de servicios Web (WSDL) 1.1.  
  
 La interoperabilidad de los protocolos de infraestructura la proporcionan las especificaciones de WS-*. Los canales WCF proporcionan compatibilidad para un número de WS -\* protocolos de infraestructura. Canales de WCF se configuran mediante elementos de enlace. Las tablas siguientes contienen la lista completa de WS -\* protocolos de infraestructura implementadas por los distintos elementos de enlace de WCF.  
  
 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> admite las especificaciones de la tabla siguiente.  
  
|Especificación/documento|Link|  
|-----------------------------|----------|  
|HTTP 1.1|[RFC 2616](https://go.microsoft.com/fwlink/?LinkId=90372)|  
|Enlace HTTP de SOAP 1.1|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=90520), sección 7|  
|Enlace HTTP de SOAP 1,2|[SOAP versión 1.2, parte 2: Adjuntos (segunda edición)](https://go.microsoft.com/fwlink/?LinkId=95329), sección 7|  
  
 <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> admiten las especificaciones de la tabla siguiente.  
  
|Especificación/documento|Link|  
|-----------------------------|----------|  
|XML|[Lenguaje de marcado extensible (XML) 1.0 (Fourth Edition)](https://go.microsoft.com/fwlink/?LinkId=15139)|  
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1.1](https://go.microsoft.com/fwlink/?LinkId=96687)|  
|Núcleo de SOAP 1.2|[Versión de SOAP 1.2, parte 1: Marco de mensajería (segunda edición)](https://go.microsoft.com/fwlink/?LinkId=94664)|  
|WS-Addressing 2004/08|[Web Services Addressing (WS-Addressing)](https://go.microsoft.com/fwlink/?LinkId=81239)|  
|Web Services Addressing 1.0 de W3C - Núcleo|[Web Services Addressing 1.0 - núcleo](https://go.microsoft.com/fwlink/?LinkId=96688)|  
|Web Services Addressing 1.0 de W3C - Enlace SOAP|[Web Services Addressing 1.0 - enlace SOAP](https://go.microsoft.com/fwlink/?LinkId=96689)|  
|W3C Web Services Addressing 1.0 – Enlace* WSDL|[Web Services Addressing 1.0 – enlace WSDL](https://go.microsoft.com/fwlink/?LinkId=96690)|  
|Metadatos de W3C Web Services Addressing 1.0|[Web Services Addressing 1.0 - metadatos](https://www.w3.org/TR/ws-addr-metadata/)|  
|Enlace SOAP 1.1 de WSDL|[Lenguaje de descripción de servicios Web (WSDL) 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)|  
|Enlace SOAP 1.2 de WSDL|[WSDL 1.1 Binding Extension para SOAP 1.2](https://go.microsoft.com/fwlink/?LinkId=96691)|  
  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> admite las especificaciones de la tabla siguiente.  
  
|Especificación/documento|Link|  
|-----------------------------|----------|  
|XOP|[Empaquetado optimizado de XML binario](https://go.microsoft.com/fwlink/?LinkId=96714)|  
|MTOM + Enlace SOAP1.2|[Mecanismo de optimización de transmisión de mensajes SOAP](https://go.microsoft.com/fwlink/?LinkId=96713)|  
|Enlace SOAP 1.1 de MTOM|[Enlace SOAP 1.1 para MTOM 1.0](https://go.microsoft.com/fwlink/?LinkId=96712)|  
|WS-PolicyAssertions de MTOM|Para publicación.|  
  
 <xref:System.ServiceModel.Channels.SecurityBindingElement> admite las especificaciones de la tabla siguiente.  
  
|Especificación/documento|Link|  
|-----------------------------|----------|  
|WSS: Seguridad del mensaje SOAP 1.0|[Seguridad de servicios Web: Seguridad del mensaje SOAP 1.0](https://go.microsoft.com/fwlink/?LinkId=94684)|  
|WSS: Perfil 1.0 de Token de nombre de usuario|[Perfil UsernameToken 1.0 de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95334)<br /><br /> requerir Password/@Type= PasswordText (valor predeterminado)|  
|WSS: Token Profile 1.0 de X.509|[Perfil de Token de Web Services Security X.509 Certificate](https://go.microsoft.com/fwlink/?LinkId=95335)|  
|WSS: 1.1 de SAML Token Profile 1.0|[Seguridad de servicios Web: Perfil de Token de SAML](https://go.microsoft.com/fwlink/?LinkId=96693)|  
|WSS: Seguridad de los mensajes SOAP 1.1|[Seguridad de servicios Web: Seguridad de los mensajes SOAP 1.1](https://go.microsoft.com/fwlink/?LinkId=91240)|  
|WSS: Token Profile 1.1 de Username|[Perfil UsernameToken 1.1 de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95331)<br /><br /> no implemente la derivación de clave basada en la contraseña;<br /><br /> requerir Password/@Type= PasswordText (valor predeterminado)|  
|WSS: X509 token Profile 1.1|[Web Services Security Token perfil de certificado X.509 1.1](https://go.microsoft.com/fwlink/?LinkId=95332)|  
|WSS: Kerberos Token Profile 1.1|[Web Services Security Kerberos Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=95333)|  
|WSS: 1.1 de SAML Token Profile 1.1|[Web Services seguridad SAML Token Profile 1.1](https://go.microsoft.com/fwlink/?LinkId=96694)|  
|WS-Secure Conversation|[Lenguaje de conversación segura de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95317)|  
|WS-Trust 1.4|[Lenguaje de confianza de servicios Web](https://go.microsoft.com/fwlink/?LinkId=169514)|  
|WS-SecurityPolicy 2005/07|[Lenguaje de conversación segura de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95317)<br /><br /> Según la corrección de las erratas enviadas al comité técnico de OASIS WS-SX.<br /><br /> [ws-sx message](https://go.microsoft.com/fwlink/?LinkId=96700)|  
|WS-ReliableMessaging 1.1|[Protocolo de mensajería de confianza versión 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)|  
  
 <xref:System.ServiceModel.Channels.TransactionFlowBindingElement> admite las especificaciones de la tabla siguiente.  
  
|Especificación/documento|Link|  
|-----------------------------|----------|  
|WS-Coordination|[Coordinación de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95324)|  
|Transacción WS-Atomic|[Transacción atómica de servicios Web](https://go.microsoft.com/fwlink/?LinkId=95323)|  
  
 Las clases <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> y <xref:System.ServiceModel.Description.MetadataResolver> proporcionan compatibilidad con las siguientes especificaciones de metadatos:  
  
- [Esquema XML parte 1: Segunda edición de estructuras](https://go.microsoft.com/fwlink/?LinkId=3536)  
  
- [Esquema XML parte 2: Tipos de datos segunda edición](https://go.microsoft.com/fwlink/?LinkId=40138)  
  
- [WSDL 1.1](https://go.microsoft.com/fwlink/?LinkId=96160)  
  
- [WS-Policy 1.2](https://go.microsoft.com/fwlink/?LinkId=96705)  
  
- [WS-Policy 1.5](https://go.microsoft.com/fwlink/?LinkId=96706)  
  
- [WS-PolicyAttachment 1.2](https://go.microsoft.com/fwlink/?LinkId=96707)  
  
- [WS-MetadataExchange 1.1](https://go.microsoft.com/fwlink/?LinkId=94868)  
  
- [WS-Transfer Get para recuperar metadatos](https://go.microsoft.com/fwlink/?LinkId=96708)  
  
 Además, los siguientes perfiles de interoperabilidad se implementan a través de WCF:  
  
- [Perfil básico 1.1](https://go.microsoft.com/fwlink/?LinkId=69313)  
  
- [Enlace SOAP simple 1.0](https://go.microsoft.com/fwlink/?LinkId=96710)  
  
- [Basic Security Profile 1.0 trabajo borrador](https://go.microsoft.com/fwlink/?LinkId=96711)  
  
## <a name="see-also"></a>Vea también

- [Protocolos de servicios web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](../../../../docs/framework/wcf/feature-details/web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [Protocolos de mensajería](../../../../docs/framework/wcf/feature-details/messaging-protocols.md)
- [Referencia de esquema de contrato de datos](../../../../docs/framework/wcf/feature-details/data-contract-schema-reference.md)
- [WSDL y directivas](../../../../docs/framework/wcf/feature-details/wsdl-and-policy.md)
- [Protocolos de seguridad](../../../../docs/framework/wcf/feature-details/security-protocols.md)
- [Protocolo de mensajería de confianza versión 1.0](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-0.md)
- [Protocolo de mensajería de confianza versión 1.1](../../../../docs/framework/wcf/feature-details/reliable-messaging-protocol-version-1-1.md)
- [Protocolos de transacciones](../../../../docs/framework/wcf/feature-details/transaction-protocols.md)
- [Protocolo de intercambio de contexto](../../../../docs/framework/wcf/feature-details/context-exchange-protocol.md)
