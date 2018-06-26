---
title: Enlaces proporcionados por el sistema
description: Obtenga información sobre todos los enlaces de Windows Communication Foundation (WCF) proporcionados por el sistema.
ms.date: 06/05/2018
helpviewer_keywords:
- bindings [WCF], system-provided
ms.assetid: 2c243746-45ce-4588-995e-c17126a579a6
ms.openlocfilehash: 6730238a73b41faa4409fdfc75af1de36f31d13e
ms.sourcegitcommit: fc70fcb9c789b6a4aefcdace46f3643fd076450f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2018
ms.locfileid: "34805651"
---
# <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema

Los enlaces especifican el mecanismo de comunicación que se ha de utilizar al hablar con un punto de conexión e indican cómo conectarse a un punto de conexión. Un enlace contiene los siguientes elementos:

- La pila de protocolos determina la seguridad, confiabilidad y valores de flujo de contexto que se han de utilizar para los mensajes que se envían al extremo.

- El transporte determina el protocolo de transporte subyacente que se ha de utilizar al enviar mensajes al punto de conexión, como, por ejemplo, TCP o HTTP.

- La codificación determina la codificación de la conexión que se va a usar para los mensajes que se envían al punto de conexión. Por ejemplo, texto/XML, binaria o Mecanismo de optimización de transmisión de mensajes (MTOM).

 En este artículo se presentan todos los enlaces de Windows Communication Foundation (WCF) proporcionados por el sistema. Si ninguno de estos enlaces cumplen los criterios exactos de la aplicación, puede crear un enlace personalizado. Para obtener más información sobre cómo crear enlaces personalizados, vea [Enlaces personalizados](./extending/custom-bindings.md).

 Un enlace seguro e interoperable que admite el protocolo WS-Federation permite a las organizaciones que están en una federación autenticar y autorizar eficazmente a los usuarios.

> [!IMPORTANT]
> Siempre seleccione un enlace que incluya seguridad. De forma predeterminada, todos los enlaces salvo el elemento [\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md) tienen habilitada la seguridad. Si no selecciona un enlace seguro o deshabilita la seguridad, asegúrese de proteger sus datos de alguna otra manera, como realizar el almacenamiento en un centro de datos seguro o en una red aislada.

> [!IMPORTANT]
> Nunca utilice contratos dúplex con enlaces que no admiten la seguridad o que tienen la seguridad deshabilitada, a menos que proteja los datos de algún otro modo.

Los enlaces siguientes vienen con WCF:

|Enlaces|Elemento de configuración |Description|
|-------------|---------------------------|-----------------|
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding>](../configure-apps/file-schema/wcf/basichttpbinding.md)|Un enlace que es útil para la comunicación con servicios web conformes con WS-Basic Profile, como, por ejemplo, servicios basados en servicios web de ASP.NET (ASMX). Este enlace utiliza HTTP como el transporte, y texto/XML como la codificación de mensajes predeterminada.|
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md)|Un enlace seguro e interoperable, adecuado para contratos de servicio que no son dúplex.|
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Un enlace seguro e interoperable adecuado para contratos de servicios dúplex o para la comunicación a través de intermediarios de SOAP.|
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding>](../configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Un enlace seguro e interoperable que admite el protocolo WS-Federation que permite a las organizaciones que están en una federación autenticar y autorizar eficazmente a los usuarios.|
|<xref:System.ServiceModel.NetHttpBinding>|[\<netHttpBinding>](../configure-apps/file-schema/wcf/nethttpbinding.md)|Enlace diseñado para consumir servicios HTTP o WebSocket que usa la codificación binaria de forma predeterminada.|
|<xref:System.ServiceModel.NetHttpsBinding>|[\<netHttpsBinding>](../configure-apps/file-schema/wcf/nethttpsbinding.md)|Enlace protegido diseñado para consumir servicios HTTP o WebSocket que usa la codificación binaria de forma predeterminada.|
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding>](../configure-apps/file-schema/wcf/nettcpbinding.md)|Un enlace seguro y optimizado adecuado para la comunicación entre equipos entre aplicaciones de WCF.|
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding>](../configure-apps/file-schema/wcf/netnamedpipebinding.md)|Un enlace seguro, confiable y optimizado que es adecuado para la comunicación en equipos entre aplicaciones de WCF.|
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding>](../configure-apps/file-schema/wcf/netmsmqbinding.md)|Un enlace en cola adecuado para la comunicación entre equipos entre aplicaciones de WCF.|
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding>](../configure-apps/file-schema/wcf/netpeertcpbinding.md)|Un enlace que permite una comunicación segura entre múltiples equipos.|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding>](../configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Un enlace adecuado para la comunicación entre equipos entre una aplicación de WCF y aplicaciones de Message Queuing existentes.|
|<xref:System.ServiceModel.BasicHttpContextBinding>|[\<basicHttpContextBinding>](../configure-apps/file-schema/wcf/basichttpcontextbinding.md)|Un enlace adecuado para la comunicación con los servicios web compatibles con el perfil WS-Basic que permite el uso de cookies HTTP para intercambiar el contexto.|
|<xref:System.ServiceModel.NetTcpContextBinding>|[\<netTcpContextBinding>](../configure-apps/file-schema/wcf/nettcpcontextbinding.md)|Un enlace seguro y optimizado adecuado para la comunicación entre aplicaciones de WCF en distintos equipos que permite usar encabezados SOAP para intercambiar el contexto.|
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../configure-apps/file-schema/wcf/webhttpbinding.md)|Un enlace que se usa para configurar los puntos de conexión de los servicios web de WCF que se exponen mediante solicitudes HTTP en lugar de mensajes SOAP.|
|<xref:System.ServiceModel.WSHttpContextBinding>|[\<wsHttpContextBinding>](../configure-apps/file-schema/wcf/wshttpcontextbinding.md)|Un enlace seguro e interoperable adecuado para los contratos de servicios no dúplex que permite usar encabezados SOAP para intercambiar el contexto.|
|<xref:System.ServiceModel.UdpBinding>|[\<udpBinding>](../configure-apps/file-schema/wcf/udpbinding.md)|Enlace que se usará al enviar una ráfaga de mensajes simples a un gran número de clientes simultáneamente.|

 La siguiente tabla muestra las características de cada uno de los enlaces proporcionados por el sistema. Los enlaces se encuentran en las columnas de la tabla; las características se enumeran en las filas y se describen en una segunda tabla. La siguiente tabla proporciona una clave para las abreviaturas de enlaces utilizadas. Para seleccionar un enlace, determine qué columna satisface todas las características de fila que necesite.

|Enlaces|Interoperabilidad|Seguridad (valor predeterminado)|Sesión<br />(Predeterminado)|Transacciones|Dúplex|Codificación (valor predeterminado)|Streaming<br />(Predeterminado)|
|-------------|----------------------|--------------------------|-----------------------------|------------------|------------|--------------------------|-------------------------------|
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Ninguno), transporte, mensaje, mixto|(Ninguno)|(Ninguno)|N/D|Texto, (MTOM)|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.WSHttpBinding>|WS|Transporte, (mensaje), mixto|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|N/D|(Texto), MTOM|No|
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|(Mensaje), ninguno|(Sesión confiable), sesión de seguridad|(Ninguno), Sí|Sí|(Texto), MTOM|No|
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|(Mensaje), mixto, ninguno|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|No|(Texto), MTOM|No|
|<xref:System.ServiceModel.NetHttpBinding>|.NET|(Ninguno), Transporte, Mensaje, TransportWithMessageCredential, TransportCredentialOnly|Vea la nota siguiente|Ninguna|Vea la nota siguiente|(Binario), Texto, MTOM|Sí (almacenado en búfer)|
|<xref:System.ServiceModel.NetHttpsBinding>|.NET|(Transporte), TransportWithMessageCredential|Vea la nota siguiente|Ninguna|Vea la nota siguiente|(Binario), Texto, MTOM|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.NetTcpBinding>|.NET|(Transporte), mensaje, ninguno, mixto|(Transporte), sesión confiable, sesión de seguridad|(Ninguno), Sí|Sí|Binary|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|(Transporte), ninguno|Ninguno, (transporte)|(Ninguno), Sí|Sí|Binary|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Mensaje, (Transporte), Ninguno|(Ninguno), transporte|Ninguno, (Sí)|No|Binary|No|
|<xref:System.ServiceModel.NetPeerTcpBinding>|Del mismo nivel|(Transporte)|(Ninguno)|(Ninguno)|Sí||No|
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|(Transporte)|(Ninguno)|Ninguno, (Sí)|N/D|N/D|No|
|<xref:System.ServiceModel.BasicHttpContextBinding>|Basic Profile 1.1|(Ninguno), transporte, mensaje, mixto|(Ninguno)|(Ninguno)|N/D|Texto, (MTOM)|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.NetTcpContextBinding>|.NET|(Transporte), mensaje, ninguno, mixto|(Transporte), sesión confiable, sesión de seguridad|(Ninguno), Sí|Sí|Binary|Sí<br />(almacenado en búfer)|
|<xref:System.ServiceModel.WSHttpContextBinding>|WS|Transporte, (mensaje), mixto|(Ninguno), sesión confiable, sesión de seguridad|(Ninguno), Sí|N/D|Texto, (MTOM)|No|
|<xref:System.ServiceModel.UdpBinding> <br /><br /> **Nota:** Se puede lograr la interoperabilidad mediante la implementación de la especificación estándar de SOAP-sobre-UDP que este enlace implementa.|.NET|(Ninguno)|(Ninguno)|(Ninguno)|N/D|(Texto)|No|

> [!IMPORTANT]
> <xref:System.ServiceModel.NetHttpBinding> es un enlace diseñado para consumir servicios HTTP o WebSocket y usa la codificación binaria de forma predeterminada. <xref:System.ServiceModel.NetHttpBinding> detecta si se usa con un contrato de solicitud-respuesta o dúplex, y cambia su comportamiento para que coincida; usa HTTP para los contratos de solicitud-respuesta y WebSockets para los dúplex. Este comportamiento se puede reemplazar mediante el valor de enlace de <xref:System.ServiceModel.Channels.WebSocketTransportUsage>: WhenDuplex. Es el valor predeterminado y se comporta como se describió antes. Nunca: evita que se use WebSockets. Si se intenta usar un contrato dúplex con este valor se produce una excepción. Siempre: obliga a usar WebSockets incluso para los contratos de solicitud-respuesta. NetHttpBinding admite sesiones confiables en modo HTTP y en modo WebSocket. En el modo WebSocket, el transporte proporciona las sesiones.

 La siguiente tabla explica las características enumeradas en la tabla anterior.

|Característica|Description|
|-------------|-----------------|
|Tipo de interoperabilidad|Nombra el protocolo o tecnología con la que el enlace asegura la interoperación.|
|Seguridad|Especifica cómo se protege el canal:<br />- Ninguno: el mensaje SOAP no se protege y no se autentica el cliente.<br />- Transporte: los requisitos de seguridad se satisfacen en el nivel de transporte.<br />- Mensaje: los requisitos de seguridad se satisfacen en la capa del mensaje.<br />- Mixto: las notificaciones se transmiten en el mensaje; el nivel de transporte cumple los requisitos de integridad y confidencialidad.|
|Sesión|Especifica si este enlace admite contratos de sesión.|
|Transacciones|Especifica si las transacciones están habilitadas.|
|Dúplex|Especifica si se admiten los contratos dúplex. Observe que esta característica requiere que el enlace admita sesiones.|
|Codificación|Especifica el formato de conexión del mensaje. Inclusión de valores permitida:<br />- Texto: por ejemplo, UTF-8.<br />- Binario<br />- Mecanismo de optimización de transmisión del mensaje (MTOM): método para codificar de forma eficaz elementos XML binarios dentro del contexto de un sobre SOAP.|
|Streaming|Especifica si se admite la transmisión por secuencias para mensajes de entrada y de salida. Utilice la propiedad `TransferMode` del enlace para establecer el valor. Entre los valores permitidos se incluyen:<br />- <xref:System.ServiceModel.TransferMode.Buffered>: los mensajes de respuesta y solicitud se almacenan en búfer.<br />- <xref:System.ServiceModel.TransferMode.Streamed>: los mensajes de solicitud y respuesta se transmiten por secuencias.<br />- <xref:System.ServiceModel.TransferMode.StreamedRequest>: el mensaje de solicitud se transmite por secuencias y el mensaje de respuesta se almacena en búfer.<br />- <xref:System.ServiceModel.TransferMode.StreamedResponse>: el mensaje de solicitud se almacena en búfer y el mensaje de respuesta se transmite por secuencias.|

## <a name="see-also"></a>Vea también

[Información general sobre la creación de puntos finales](endpoint-creation-overview.md)  
[Utilización de enlaces para configurar servicios y clientes](using-bindings-to-configure-services-and-clients.md)  
[Programación básica de WCF](basic-wcf-programming.md)  
