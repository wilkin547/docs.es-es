---
title: WSDL y directivas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cea87440-3519-4640-8494-b8a2b0e88c84
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: d9255800b08fee4ab15a6d6feef3a53c2755dde8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="wsdl-and-policy"></a>WSDL y directivas
En este tema se explica [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] WSDL 1.1, WS-Policy y detalles de implementación de WS-PolicyAttachment, así como las aserciones adicionales de WS-Policy y las extensiones de WSDL 1.1 introducidas por [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa WS-Policy y especificaciones de WS-PolicyAttachment enviadas a W3C con las restricciones y clarificaciones descritas en este documento.  
  
 En este documento se utilizan los prefijos y espacios de nombres mostrados en la tabla siguiente.  
  
|Prefijo|Espacio de nombres|  
|------------|---------------|  
|wsp (WS-Policy 1,2)|http://schemas.xmlsoap.org/ws/2004/09/policy|  
|wsp (WS-Policy 1.5)|http://www.w3.org/ns/ws-policy|  
|http|http://schemas.microsoft.com/ws/06/2004/policy/http|  
|msmq|http://schemas.microsoft.com/ws/06/2004/mspolicy/msmq|  
|msf|http://schemas.microsoft.com/ws/2006/05/framing/policy|  
|mssp|http://schemas.microsoft.com/ws/2005/07/securitypolicy|  
|msc|http://schemas.microsoft.com/ws/2005/12/wsdl/contract|  
|cdp|http://schemas.microsoft.com/net/2006/06/duplex|  
  
## <a name="wcf-wsdl11-extensions"></a>Extensiones WCF WSDL1.1   
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza las extensiones WSDL1.1 siguientes para describir los requisitos de sesión de contrato.  
  
 wsdl:portType/wsdl:operation/@msc:isInitiating  
 xs:boolean, indica que esta operación inicia una sesión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]; el valor predeterminado es `false`.  
  
 wsdl:portType/wsdl:operation/@msc:isTerminating  
 xs:boolean, indica que esta operación finaliza una sesión [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]; el valor predeterminado es `false`.  
  
 wsdl:portType/wsdl:operation/@msc:usingSession  
 xs:boolean, indica que este contrato requiere establecer la sesión.  
  
### <a name="soap-1x-http-binding-transport-uris"></a>SOAP 1.x HTTPTransporte de enlace URIs  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] utiliza los URI siguientes para indicar qué transportes se van a utilizar para los elementos de extensión de enlace WSDL 1.1, SOAP 1.1 y SOAP 1.2.  
  
|Transporte|URI|  
|---------------|---------|  
|HTTP|http://schemas.xmlsoap.org/soap/http|  
|TCP|http://schemas.microsoft.com/soap/tcp|  
|MSMQ|http://schemas.microsoft.com/soap/msmq|  
|Canalizaciones con nombre|http://schemas.microsoft.com/soap/named-pipe|  
  
## <a name="policy-assertions-implemented-by-wcf"></a>Aserciones de directivas implementadas por WCF  
 Además de las aserciones de directiva introducidas en las especificaciones de los Servicio Web (WS - *) y mencionadas en otras secciones de este documento, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] implementa las aserciones de directiva siguientes.  
  
|Aserción de directiva|Asunto de directiva|Descripción|  
|----------------------|--------------------|-----------------|  
|http:HttpBasicAuthentication|Extremo|El extremo utiliza autenticación básica de Http.|  
|http:HttpDigestAuthentication|Extremo|El extremo utiliza autenticación implícita de Http.|  
|http:HttpNegotiateAuthentication|Extremo|El extremo utiliza autenticación de negociación de Http.|  
|http:HttpNtlmAuthentication|Extremo|El extremo utiliza autenticación NTLM de Http.|  
|msf:Streamed|Extremo|El extremo utiliza trama de mensajes transmitidos. Esta aserción se utiliza con el protocolo de trama de mensajes proporcionado para los transportes como TCP y canalizaciones con nombre.|  
|msf:SslTransportSecurity|Extremo|El extremo utiliza la seguridad del nivel de transporte (TLS) con trama de mensaje.|  
|msf:WindowsTransportSecurity|Extremo|El extremo utiliza Negociación de proveedor de seguridad (SPNEGO) con trama de mensaje.|  
|msmq:MsmqBestEffort|Extremo|MSMQ con garantías de mejor esfuerzo.|  
|msmq:MsmqSession|Extremo|MSMQ con garantías de sesión.|  
|msmq:MsmqVolatile|Extremo|MSMQ Volatile.|  
|msmq:Authenticated|Extremo|La autenticación se utiliza con transporte de MSMQ.|  
|msmq:WindowsDomain|Extremo|MSMQ utiliza la autenticación de Dominio Windows.|  
|cdp:CompositeDuplex|Extremo|El extremo utiliza dos conexiones de transporte de conversación independientes para mensajes de entrada y salida.|  
|mssp:RsaToken|Anidadas|Aserción del token de clave RSA. En general, una clave RSA serializada directamente como parte de la información clave en una firma endosada cumple este requisito.|  
|mssp:SslContextToken|Anidadas|Requiere que se utilice un SecurityContextToken obtenido mediante protocolo de enlace TLS binario y WS-Trust. Las aserciones anidadas incluyen: sp:RequireDerivedKeys, mssp:MustNotSendCancel, mssp:RequireClientCertificate.|  
|mssp:MustNotSendCancel|Anidadas|Especifica un requisito que consiste en que un token de seguridad de solicitud (RST) solicite mensajes [WS-Trust] mediante el enlace de cancelación [WS-Trust, WS-SC] y no se envíe al emisor de un SecurityContextToken determinado. Si esta aserción está presente, no se deben enviar al emisor dichos mensajes de solicitud. Si esta aserción no está presente, se puede enviar al emisor dichos mensajes de solicitud.|  
|mssp:RequireClientCertificate|Anidadas|Este elemento opcional especifica un requisito para un certificado de cliente que se proporcionará como parte del protocolo TLSNEGO. Si esta aserción está presente, se debe proporcionar un certificado de cliente. Si esta aserción no está presente, no se debe proporcionar un certificado de cliente. Esta aserción no se debe utilizar fuera de mssp:SslContextToken.|  
  
## <a name="see-also"></a>Vea también  
 [Publicación de WSDL personalizado](../../../../docs/framework/wcf/samples/custom-wsdl-publication.md)  
 [Cómo: exportar el WSDL personalizado](../../../../docs/framework/wcf/extending/how-to-export-custom-wsdl.md)  
 [Cómo: importar WSDL personalizado](../../../../docs/framework/wcf/extending/how-to-import-custom-wsdl.md)
