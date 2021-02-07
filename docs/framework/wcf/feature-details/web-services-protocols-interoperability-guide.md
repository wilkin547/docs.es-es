---
description: 'Más información acerca de: Guía de interoperabilidad de los protocolos de servicios Web'
title: Guía de interoperabilidad de los protocolos de servicios Web
ms.date: 03/30/2017
ms.assetid: f2981678-ebdb-433d-899b-467f7df95fb2
ms.openlocfilehash: cab744818d3a52c6f6cd0d95195d9112ac9babf6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752553"
---
# <a name="web-services-protocols-interoperability-guide"></a>Guía de interoperabilidad de los protocolos de servicios Web

Windows Communication Foundation (WCF) implementa varios protocolos de servicios Web. Muchos de estos protocolos incluyen distintas opciones y puntos de extensibilidad que son decisión del responsable de la implementación. En este artículo se proporciona una lista de los protocolos de servicios web que implementa WCF. En otros artículos de esta sección se proporcionan detalles de implementación para cada protocolo admitido.

## <a name="web-services-protocols-implemented-by-wcf"></a>Protocolos de servicios web implementados por WCF

WCF proporciona compatibilidad con los protocolos de infraestructura de servicios web (WS) a través de canales y protocolos de aplicación de servicios web a través de la característica de contratos. La interoperabilidad de los protocolos de aplicación se consigue mediante el lenguaje de descripción Esquema XML 1.0 (XSD) y el Lenguaje de descripción de servicios Web (WSDL) 1.1.

La interoperabilidad de los protocolos de infraestructura la proporcionan las especificaciones de WS-*. Los canales de WCF proporcionan compatibilidad con varios protocolos de WS- \* Infrastructure. Los canales de WCF se configuran mediante elementos de enlace. Las tablas siguientes contienen la lista completa de los protocolos WS- \* Infrastructure implementados por diversos elementos de enlace de WCF.

<xref:System.ServiceModel.Channels.HttpTransportBindingElement> admite las especificaciones de la tabla siguiente.

|Especificación/documento|Vínculo|
|-----------------------------|----------|
|HTTP 1.1|[RFC 2616](https://www.rfc-editor.org/rfc/rfc2616.txt)|
|Enlace HTTP de SOAP 1.1|[Protocolo simple de acceso a objetos (SOAP) 1,1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/), sección 7|
|Enlace HTTP de SOAP 1,2|[SOAP versión 1,2, parte 2: adjuntos (segunda edición)](https://www.w3.org/TR/soap12-part2/), sección 7|

<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement> y <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> admiten las especificaciones de la tabla siguiente.

|Especificación/documento|Vínculo|
|-----------------------------|----------|
|XML|[Extensible Markup Language (XML) 1.0 (Fourth Edition)](https://www.w3.org/TR/REC-xml/)|
|SOAP 1,1|[Simple Object Access Protocol (SOAP) 1.1](https://www.w3.org/TR/2000/NOTE-SOAP-20000508/)|
|Núcleo de SOAP 1.2|[SOAP Version 1.2 Part 1: Messaging Framework (Second Edition)](https://www.w3.org/TR/2007/REC-soap12-part1-20070427/)|
|WS-Addressing 2004/08|[Web Services Addressing (WS-Addressing)](https://www.w3.org/Submission/2004/SUBM-ws-addressing-20040810/)|
|Web Services Addressing 1.0 de W3C - Núcleo|[Direccionamiento de servicios Web 1.0 - Núcleo](https://www.w3.org/TR/2006/REC-ws-addr-core-20060509/)|
|Web Services Addressing 1.0 de W3C - Enlace SOAP|[Direccionamiento de servicios web 1.0 – Enlace SOAP](https://www.w3.org/TR/2006/REC-ws-addr-soap-20060509/)|
|W3C Web Services Addressing 1.0 – Enlace* WSDL|[Web Services Addressing 1.0 – Enlace WSDL](https://www.w3.org/TR/2006/CR-ws-addr-wsdl-20060529/)|
|Metadatos de W3C Web Services Addressing 1.0|[Web Services Addressing 1.0 - Metadatos](https://www.w3.org/TR/ws-addr-metadata/)|
|Enlace SOAP 1.1 de WSDL|[Lenguaje de descripción de servicios Web (WSDL) 1.1](https://www.w3.org/TR/wsdl/)|
|Enlace SOAP 1.2 de WSDL|[WSDL 1.1 Binding Extension for SOAP 1.2](https://www.w3.org/Submission/wsdl11soap12/)|

<xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement> admite las especificaciones de la tabla siguiente.

|Especificación/documento|Vínculo|
|-----------------------------|----------|
|XOP|[XML-binary Optimized Packaging](https://www.w3.org/TR/xop10/)|
|MTOM + Enlace SOAP1.2|[Mecanismo de optimización de transmisión de mensajes SOAP](https://www.w3.org/TR/soap12-mtom/)|
|Enlace SOAP 1.1 de MTOM|[SOAP 1.1 Binding for MTOM 1.0](https://www.w3.org/Submission/soap11mtom10/)|
|WS-PolicyAssertions de MTOM|[Aserción de directiva de serialización MTOM (WS-MTOMPolicy)](https://www.w3.org/Submission/WS-MTOMPolicy/)|

<xref:System.ServiceModel.Channels.SecurityBindingElement> admite las especificaciones de la tabla siguiente.

|Especificación/documento|Vínculo|
|-----------------------------|----------|
|WSS: Message Security 1,0 de SOAP|[Seguridad de Servicios web: seguridad del mensaje SOAP 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-soap-message-security-1.0.pdf)|
|WSS: Token Profile 1.0 de Username|[Perfil Seguridad de Servicios web UsernameToken 1,0](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-username-token-profile-1.0.pdf)<br /><br /> requerir Password/@Type = PasswordText (valor predeterminado)|
|WSS: Token Profile 1.0 de X.509|[Perfil de token de certificado X.509 de seguridad de servicios Web](https://docs.oasis-open.org/wss/2004/01/oasis-200401-wss-x509-token-profile-1.0.pdf)|
|WSS: Token Profile 1.1 de SAML 1,0|[Web Services Security: SAML Token Profile](https://docs.oasis-open.org/wss/oasis-wss-saml-token-profile-1.0.pdf)|
|WSS: Message Security 1.1 de SOAP|[Web Services Security: SOAP Message Security 1.1](https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf)|
|WSS: Token Profile 1.1 de Username|[Web Services Security UsernameToken Profile 1.1](https://www.oasis-open.org/committees/download.php/16782/wss-v1.1-spec-os-UsernameTokenProfile.pdf)<br /><br /> no implemente la derivación de clave basada en la contraseña;<br /><br /> requerir Password/@Type = PasswordText (valor predeterminado)|
|WSS: Token Profile 1.1 de X509|[Web Services Security X.509 Certificate Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf)|
|WSS: Token Profile 1.1 de Kerberos|[Web Services Security Kerberos Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16788/wss-v1.1-spec-os-KerberosTokenProfile.pdf)|
|WSS: Token Profile 1.1 de SAML 1.1|[Web Services Security SAML Token Profile 1.1](https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf)|
|WS-Secure Conversation|[Web Services Secure Conversation Language](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)|
|WS-Trust 1.4|[Web Services Trust Language](https://docs.oasis-open.org/ws-sx/ws-trust/200802)|
|WS-SecurityPolicy 2005/07|[Web Services Secure Conversation Language](http://specs.xmlsoap.org/ws/2005/02/sc/ws-secureconversation.pdf)<br /><br /> Según la corrección de las erratas enviadas al comité técnico de OASIS WS-SX.<br /><br /> [ws-sx message](https://lists.oasis-open.org/archives/ws-sx/200512/msg00017.html)|
|WS-ReliableMessaging 1.1|[Protocolo de mensajería de confianza versión 1,1](reliable-messaging-protocol-version-1-1.md)|

<xref:System.ServiceModel.Channels.TransactionFlowBindingElement> admite las especificaciones de la tabla siguiente.

|Especificación/documento|Vínculo|
|-----------------------------|----------|
|WS-Coordination|[Web Services Coordination](/previous-versions/ms951231(v=msdn.10))|
|Transacción WS-Atomic|[Web Services Atomic Transaction](http://specs.xmlsoap.org/ws/2004/10/wsat/wsat.pdf)|

Las clases <xref:System.ServiceModel.Description.MetadataExporter>, <xref:System.ServiceModel.Description.MetadataImporter>, <xref:System.ServiceModel.Description.WsdlExporter>, <xref:System.ServiceModel.Description.WsdlImporter> y <xref:System.ServiceModel.Description.MetadataResolver> proporcionan compatibilidad con las siguientes especificaciones de metadatos:

- [Esquema XML Parte 1: segunda edición de estructuras](https://www.w3.org/TR/xmlschema-1/)

- [Esquema XML Parte 2: segunda edición de tipos de datos](https://www.w3.org/TR/xmlschema-2/)

- [WSDL 1.1](https://www.w3.org/TR/wsdl/)

- [WS-Policy 1,2](https://www.w3.org/Submission/2006/SUBM-WS-Policy-20060425/)

- [WS-Policy 1.5](https://www.w3.org/TR/ws-policy/)

- [WS-PolicyAttachment 1.2](https://www.w3.org/Submission/2006/SUBM-WS-PolicyAttachment-20060425/)

- [WS-MetadataExchange 1.1](http://specs.xmlsoap.org/ws/2004/09/mex/WS-MetadataExchange.pdf)

- [WS-Transfer Get para la recuperación de metadatos](https://www.w3.org/Submission/2006/SUBM-WS-Transfer-20060315/)

Además, se implementan los siguientes perfiles de interoperabilidad en WCF:

- [Basic Profile 1.1](http://www.ws-i.org/Profiles/BasicProfile-1.1-2004-08-24.html)

- [Enlace simple de SOAP 1.0](http://www.ws-i.org/Profiles/SimpleSoapBindingProfile-1.0-2004-08-24.html)

- [Borrador de trabajo de Basic Security Profile 1.0](http://www.ws-i.org/Profiles/BasicSecurityProfile-1.0-2006-03-29.html)

## <a name="see-also"></a>Vea también

- [Protocolos de servicios Web compatibles con los enlaces de interoperabilidad proporcionados por el sistema](web-services-protocols-supported-by-system-provided-interoperability-bindings.md)
- [Protocolos de mensajería](messaging-protocols.md)
- [Referencia de esquema de contrato de datos](data-contract-schema-reference.md)
- [WSDL y directivas](wsdl-and-policy.md)
- [Protocolos de seguridad](security-protocols.md)
- [Protocolo de mensajería de confianza versión 1.0](reliable-messaging-protocol-version-1-0.md)
- [Protocolo de mensajería de confianza versión 1,1](reliable-messaging-protocol-version-1-1.md)
- [Protocolos de transacciones](transaction-protocols.md)
- [Protocolo de intercambio de contexto](context-exchange-protocol.md)
