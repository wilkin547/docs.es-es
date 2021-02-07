---
description: 'Más información acerca de: WSDL y Policy'
title: WSDL y directivas
ms.date: 03/30/2017
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
ms.openlocfilehash: e7d0ca81fbac1a746fa7c10efb8e8d32f1ee3240
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99704152"
---
# <a name="wsdl-and-policy"></a>WSDL y directivas

En este tema se tratan los detalles de la implementación de Windows Communication Foundation (WCF) WSDL 1,1, WS-Policy y WS-PolicyAttachment, así como las aserciones WS-Policy adicionales y las extensiones WSDL 1,1 introducidas por WCF.  
  
 WCF implementa WS-Policy y WS-PolicyAttachment especificaciones enviadas a W3C con restricciones y aclaraciones que se describen en este documento.  
  
 En este documento se utilizan los prefijos y espacios de nombres mostrados en la tabla siguiente.  
  
|Prefijo|Espacio de nombres|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|`http://schemas.xmlsoap.org/ws/2004/09/policy`|  
|wsp (WS-Policy 1.5)|`http://www.w3.org/ns/ws-policy`|  
|http|`http://schemas.microsoft.com/ws/06/2004/policy/http`|  
|msmq|`http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq`|  
|msf|`http://schemas.microsoft.com/ws/2006/05/framing/policy`|  
|mssp|`http://schemas.microsoft.com/ws/2005/07/securitypolicy`|  
|msc|`http://schemas.microsoft.com/ws/2005/12/wsdl/contract`|  
|cdp|`http://schemas.microsoft.com/net/2006/06/duplex`|  
  
## <a name="wcf-wsdl11-extensions"></a>Extensiones WCF WSDL1.1   

 WCF usa las siguientes extensiones WSDL 1.1 para describir los requisitos de la sesión de contrato.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 XS: Boolean, indica que esta operación inicia una sesión de WCF; el valor predeterminado es `false` .  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 XS: Boolean, indica que esta operación finaliza una sesión de WCF; el valor predeterminado es `false` .  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, indica que este contrato requiere establecer la sesión.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>SOAP 1.x HTTPTransporte de enlace URIs  

 WCF usa los siguientes URI para indicar los transportes que se van a usar para los elementos de extensión de enlace de WSDL 1,1, SOAP 1,1 y SOAP 1,2.  
  
|Transporte|URI|  
|---------------|---------|  
|HTTP|`http://schemas.xmlsoap.org/soap/http`|  
|TCP|`http://schemas.microsoft.com/soap/tcp`|  
|MSMQ|`http://schemas.microsoft.com/soap/msmq`|  
|Canalizaciones con nombre|`http://schemas.microsoft.com/soap/named-pipe`|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Aserciones de directivas implementadas por WCF  

 Además de las aserciones de directiva introducidas en las especificaciones de servicios web (WS-*) y mencionadas en otras secciones de este documento, WCF implementa las siguientes aserciones de directiva.  
  
|Aserción de directiva|Asunto de directiva|Descripción|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Punto de conexión|El punto de conexión utiliza autenticación básica de Http.|  
|http:HttpDigestAuthentication|Punto de conexión|El punto de conexión utiliza autenticación implícita de Http.|  
|http:HttpNegotiateAuthentication|Punto de conexión|El punto de conexión utiliza autenticación de negociación de Http.|  
|http:HttpNtlmAuthentication|Punto de conexión|El extremo utiliza autenticación NTLM de Http.|  
|msf:Streamed|Punto de conexión|El extremo utiliza trama de mensajes transmitidos. Esta aserción se utiliza con el protocolo de trama de mensajes proporcionado para los transportes como TCP y canalizaciones con nombre.|  
|msf:SslTransportSecurity|Punto de conexión|El punto de conexión utiliza la seguridad del nivel de transporte (TLS) con trama de mensaje.|  
|msf:WindowsTransportSecurity|Punto de conexión|El punto de conexión utiliza Negociación de proveedor de seguridad (SPNEGO) con trama de mensaje.|  
|msmq:MsmqBestEffort|Punto de conexión|MSMQ con garantías de mejor esfuerzo.|  
|msmq:MsmqSession|Punto de conexión|MSMQ con garantías de sesión.|  
|msmq:MsmqVolatile|Punto de conexión|MSMQ Volatile.|  
|msmq:Authenticated|Punto de conexión|La autenticación se utiliza con transporte de MSMQ.|  
|msmq:WindowsDomain|Punto de conexión|MSMQ utiliza la autenticación de Dominio Windows.|  
|cdp:CompositeDuplex|Punto de conexión|El extremo utiliza dos conexiones de transporte de conversación independientes para mensajes de entrada y salida.|  
|mssp:RsaToken|está anidada|Aserción del token de clave RSA. En general, una clave RSA serializada directamente como parte de la información clave en una firma endosada cumple este requisito.|  
|mssp:SslContextToken|está anidada|Requiere que se utilice un SecurityContextToken obtenido mediante protocolo de enlace TLS binario y WS-Trust. Las aserciones anidadas incluyen: sp:RequireDerivedKeys, mssp:MustNotSendCancel, mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|está anidada|Especifica un requisito que consiste en que un token de seguridad de solicitud (RST) solicite mensajes [WS-Trust] mediante el enlace de cancelación [WS-Trust, WS-SC] y no se envíe al emisor de un SecurityContextToken determinado. Si esta aserción está presente, no se deben enviar al emisor dichos mensajes de solicitud. Si esta aserción no está presente, se puede enviar al emisor dichos mensajes de solicitud.|  
|mssp:RequireClientCertificate|está anidada|Este elemento opcional especifica un requisito para un certificado de cliente que se proporcionará como parte del protocolo TLSNEGO. Si esta aserción está presente, se debe proporcionar un certificado de cliente. Si esta aserción no está presente, no se debe proporcionar un certificado de cliente. Esta aserción no se debe utilizar fuera de mssp:SslContextToken.|  
  
## <a name="see-also"></a>Vea también

- [Publicación de WSDL personalizada](../samples/custom-wsdl-publication.md)
- [Procedimiento para exportar el WSDL personalizado](../extending/how-to-export-custom-wsdl.md)
- [Procedimiento para importar el WSDL personalizado](../extending/how-to-import-custom-wsdl.md)
