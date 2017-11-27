---
title: Enlaces proporcionados por el sistema
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
caps.latest.revision: "60"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c5583956e206194e7c457f9e4162660a6f1c59b0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema
Los enlaces especifican el mecanismo de comunicación que se ha de utilizar al hablar con un punto de conexión e indican cómo conectarse a un punto de conexión. Un enlace contiene los siguientes elementos:  
  
-   La pila de protocolos determina la seguridad, confiabilidad y valores de flujo de contexto que se han de utilizar para los mensajes que se envían al extremo.  
  
-   El transporte determina el protocolo de transporte subyacente que se ha de utilizar al enviar mensajes al extremo, como, por ejemplo, TCP o HTTP.  
  
-   La codificación determina la codificación de la conexión que se ha de utilizar para los mensajes que se envían al extremo, como, por ejemplo, texto/XML, binaria o Mecanismo de optimización de transmisión de mensajes (MTOM).  
  
 En este tema se presentan todos los enlaces de [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] proporcionados por el sistema. Si ninguno de estos cumplen los criterios exactos de su aplicación, puede crear un enlace personalizado. [!INCLUDE[crabout](../../../includes/crabout-md.md)]cómo crear enlaces personalizados, consulte [enlaces personalizados](../../../docs/framework/wcf/extending/custom-bindings.md).  
  
 Un enlace seguro e interoperable que admite el protocolo WS-Federation permite a las organizaciones que están en una federación autenticar y autorizar eficazmente a los usuarios.  
  
> [!IMPORTANT]
>  Siempre seleccione un enlace que incluya seguridad. De forma predeterminada, todos los enlaces excepto la [ \<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) elemento tiene la seguridad habilitada. Si no selecciona un enlace seguro o deshabilita la seguridad, asegúrese de proteger sus datos de alguna otra manera, como realizar el almacenamiento en un centro de datos seguro o en una red aislada.  
  
> [!IMPORTANT]
>  Nunca utilice contratos dúplex con enlaces que no admiten la seguridad o que tienen la seguridad deshabilitada, a menos que proteja los datos de algún otro modo.  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  
 Los siguientes enlaces vienen con [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].  
  
|Enlaces|Elemento de configuración |Descripción|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Un enlace que es útil para la comunicación con servicios web conformes con WS-Basic Profile, como, por ejemplo, servicios basados en servicios web de ASP.NET (ASMX). Este enlace utiliza HTTP como el transporte, y texto/XML como la codificación de mensajes predeterminada.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Un enlace seguro e interoperable, adecuado para contratos de servicio que no son dúplex.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Un enlace seguro e interoperable adecuado para contratos de servicios dúplex o para la comunicación a través de intermediarios de SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Un enlace seguro e interoperable que admite el protocolo WS-Federation que permite a las organizaciones que están en una federación autenticar y autorizar eficazmente a los usuarios.|  
|<xref:System.ServiceModel.NetHttpBinding>|\<netHttpBinding >|Enlace diseñado para consumir servicios HTTP o WebSocket que usa la codificación binaria de forma predeterminada.|  
|<xref:System.ServiceModel.NetHttpsBinding>|\<NetHttpBinding >|Enlace protegido diseñado para consumir servicios HTTP o WebSocket que usa la codificación binaria de forma predeterminada.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Un enlace seguro y optimizado adecuado para la comunicación entre equipos entre aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Un enlace seguro, confiable y optimizado que es adecuado para la comunicación en equipos entre aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Un enlace en cola adecuado para la comunicación entre equipos entre aplicaciones de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Un enlace que permite una comunicación segura entre múltiples equipos.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Un enlace adecuado para la comunicación entre equipos entre una aplicación de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] y aplicaciones de Message Queuing existentes.|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Un enlace adecuado para la comunicación con los servicios web compatibles con el perfil WS-Basic que permite el uso de cookies HTTP para intercambiar el contexto.|  
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Un enlace seguro y optimizado adecuado para la comunicación entre aplicaciones [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] en distintos equipos que permite utilizar encabezados SOAP para intercambiar el contexto.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Un enlace que se utiliza para configurar los extremos de los servicios web de [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] que se exponen mediante solicitudes HTTP en lugar de mensajes SOAP.|  
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Una ubicación segura y |<xref:System.ServiceModel.UdpBinding>|\<udpBinding >|Enlace que se usará al enviar una ráfaga de mensajes simples a un gran número de clientes simultáneamente.|  
  
 La siguiente tabla muestra las características de cada uno de los enlaces proporcionados por el sistema. Los enlaces se encuentran en las columnas de la tabla; las características se enumeran en las filas y se describen en una segunda tabla. La siguiente tabla proporciona una clave para las abreviaturas de enlaces utilizadas. Para seleccionar un enlace, determine qué columna satisface todas las características de fila que necesite.  
  
|Enlaces|Interoperabilidad|Seguridad (valor predeterminado)|Sesión<br /><br /> (Predeterminado)|Transacciones|Dúplex|Codificación (valor predeterminado)|Streaming<br /><br /> (Predeterminado)|  
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Ninguno), transporte, mensaje, mixto|(Ninguno)|(Ninguno)|no disponible|Texto, (MTOM)|Sí<br /><br /> (almacenado en búfer)|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Transporte, (mensaje), mixto|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|no disponible|(Texto), MTOM|No|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Mensaje), ninguno|(Sesión confiable), sesión de seguridad|(Ninguno), Sí|Sí|(Texto), MTOM|No|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Mensaje), mixto, ninguno|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|No|(Texto), MTOM|No|  
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(Ninguno), Transporte, Mensaje, TransportWithMessageCredential, TransportCredentialOnly|Vea la nota siguiente|Ninguna|Vea la nota siguiente|(Binary), Text,MTOM|Sí (almacenado en búfer)|  
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Transporte), TransportWithMessageCredential|Vea la nota siguiente|Ninguna|Vea la nota siguiente|(Binary), Text,MTOM|Sí (almacenado en búfer)|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transporte), mensaje, ninguno, mixto|(Transporte), sesión confiable, sesión de seguridad|(Ninguno), Sí|Sí|Binary|Sí<br /><br /> (almacenado en búfer)|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transporte), ninguno|Ninguno, (transporte)|(Ninguno), Sí|Sí|Binary|Sí<br /><br /> (almacenado en búfer)|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Mensaje, (Transporte), Ninguno|(Ninguno), transporte|Ninguno, (Sí)|No|Binary|No|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Del mismo nivel|(Transporte)|(Ninguno)|(Ninguno)|Sí||No|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Transporte)|(Ninguno)|Ninguno, (Sí)|no disponible|no disponible|No|  
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(Ninguno), transporte, mensaje, mixto|(Ninguno)|(Ninguno)|no disponible|Texto, (MTOM)|Sí<br /><br /> (almacenado en búfer)|  
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transporte), mensaje, ninguno, mixto|(Transporte), sesión confiable, sesión de seguridad|(Ninguno), Sí|Sí|Binary|Sí<br /><br /> (almacenado en búfer)|  
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Transporte, (mensaje), mixto|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|no disponible|Texto, (MTOM)|No|  
|<xref:System.ServiceModel.UdpBinding>|.NET **Nota:** se puede lograr interoperabilidad implementando la especificación estándar de SOAP-sobre-UDP que este enlace implementa.|(Ninguno)|(Ninguno)|(Ninguno)|no disponible|(Texto)|No|  
  
> [!IMPORTANT]
>  <xref:System.ServiceModel.NetHttpBinding> es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada. <xref:System.ServiceModel.NetHttpBinding> detectará si se usa con un contrato de solicitud-respuesta o dúplex y cambiará su comportamiento para que coincida; usará HTTP para los contratos de solicitud-respuesta y WebSockets para los dúplex. Este comportamiento puede invalidarse mediante el <!--zz <xref:System.ServiceModel.NetHttpBinding.WebSocketTransportUsage%2A>--> `System.ServiceModel.NetHttpBinding.WebSocketTransportUsage` valor de enlace: permitida: este es el valor predeterminado y se comporta como se describió anteriormente. NotAllowed - Esto impide que se use WebSockets. Intenta usar un contrato dúplex con este valor se producirá una excepción. Requerido: obliga a utilizar incluso para los contratos de solicitud-respuesta WebSockets. NetHttpBinding admite sesiones confiables en modo de HTTP y el modo WebSocket. En el modo WebSocket, el transporte proporciona las sesiones.  
  
 La siguiente tabla explica las características enumeradas en la tabla anterior.  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Tipo de interoperabilidad|Nombra el protocolo o tecnología con la que el enlace asegura la interoperación.|  
|Seguridad|Especifica cómo se protege el canal:<br /><br /> -None: No se protege el mensaje SOAP y no se autentica el cliente.<br />-Transport: Requisitos de seguridad se satisfacen en la capa de transporte.<br />-Mensaje: Los requisitos de seguridad se satisfacen en la capa del mensaje.<br />-Mixto: Demandas se llevan en el mensaje. la capa de transporte cumple los requisitos de integridad y confidencialidad.|  
|Sesión|Especifica si este enlace admite contratos de sesión.|  
|Transacciones|Especifica si las transacciones están habilitadas.|  
|Dúplex|Especifica si se admiten los contratos dúplex. Observe que esta característica requiere que el enlace admita sesiones.|  
|Codificación|Especifica el formato de conexión del mensaje. Inclusión de valores permitida:<br /><br /> -Texto: por ejemplo, UTF-8.<br />-Binario<br />-Mecanismo de optimización de transmisión del mensaje (mensaje MTOM): Un método para codificar de forma eficaz elementos XML binarios dentro del contexto de una envoltura SOAP.|  
|Streaming|Especifica si se admite la transmisión por secuencias para mensajes de entrada y de salida. Utilice la propiedad `TransferMode` del enlace para establecer el valor. Entre los valores permitidos se incluyen:<br /><br /> -   <xref:System.ServiceModel.TransferMode.Buffered>: Los mensajes de solicitud y respuesta están almacenados en búfer.<br />-   <xref:System.ServiceModel.TransferMode.Streamed>: Los solicitud y respuesta se transmiten los mensajes.<br />-   <xref:System.ServiceModel.TransferMode.StreamedRequest>: El mensaje de solicitud se transmite por secuencias y se almacena en búfer el mensaje de respuesta.<br />-   <xref:System.ServiceModel.TransferMode.StreamedResponse>: El mensaje de solicitud se almacena en búfer y se transmite el mensaje de respuesta.|  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la creación de puntos finales](../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Utilización de enlaces para configurar servicios y clientes](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Programación básica de WCF](../../../docs/framework/wcf/basic-wcf-programming.md)
