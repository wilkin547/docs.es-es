---
title: Configuración de enlaces proporcionados por el sistema
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Windows Communication Foundation [WCF], system-provided bindings
- WCF [WCF], system-provided bindings
- bindings [WCF], system-provided
ms.assetid: 443f8d65-f1f2-4311-83b3-4d8fdf7ccf16
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9bbf04f549c492ddc392b429edf3a703f3c307a0
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="configuring-system-provided-bindings"></a>Configuración de enlaces proporcionados por el sistema
Los enlaces especifican el mecanismo de comunicación que se ha de utilizar al hablar con un punto de conexión e indican cómo conectarse a un punto de conexión. Los enlaces están compuestos de elementos que definen cómo se disponen en capa los canales de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] para proporcionar las características de comunicación necesarias. Un enlace contiene tres tipos de elementos:  
  
-   Elementos de enlace de canal protocolares, que determinan la seguridad, confiabilidad, valores de flujo de contexto o los protocolos definidos por el usuario que se han de utilizar con los mensajes que se envían al extremo.  
  
-   Elementos de enlace de canal de transporte, que determinan el protocolo de transporte subyacente que se ha de usar al enviar mensajes al extremo, por ejemplo, TCP o HTTP.  
  
-   Elementos de enlace de codificación de mensajes, que determinan la codificación de la conexión que se ha de utilizar para los mensajes que se envían al punto de conexión, como, por ejemplo, texto/XML, binaria o Mecanismo de optimización de transmisión de mensajes (MTOM).  
  
 En este tema se presentan todos los enlaces de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporcionados por el sistema. Si ninguno de ellos cumple los requisitos exactos de su aplicación, puede crear un enlace mediante la clase <xref:System.ServiceModel.Channels.CustomBinding>. Para obtener más información acerca de cómo crear enlaces personalizados, consulte [enlaces personalizados](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
> [!IMPORTANT]
>  Seleccione un enlace que tenga habilitada la seguridad. De forma predeterminada, todos los enlaces, salvo <xref:System.ServiceModel.BasicHttpBinding>, tienen habilitada la seguridad. Si no selecciona un enlace seguro, o si deshabilita la seguridad, asegúrese de que sus intercambios de red se protegen de alguna otra manera, como, por ejemplo, estando en un centro de procesamiento de datos seguro o en una red aislada.  
  
> [!IMPORTANT]
>  No utilice contratos dúplex con enlaces que no admiten la seguridad o que tienen la seguridad deshabilitada, a menos que el intercambio de red se proteja de alguna otra manera.  
  
## <a name="system-provided-bindings"></a>Enlaces proporcionados por el sistema  
 Los siguientes enlaces se distribuyen con [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
|Enlaces|Elemento de configuración |Descripción|  
|-------------|---------------------------|-----------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|[\<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|Un enlace que es útil para la comunicación con servicios web conformes con WS-Basic Profile, como, por ejemplo, servicios basados en servicios web de ASP.NET (ASMX). Este enlace utiliza HTTP como el transporte, y texto/XML como la codificación de mensajes predeterminada.|  
|<xref:System.ServiceModel.WSHttpBinding>|[\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|Un enlace seguro e interoperable, adecuado para contratos de servicio que no son dúplex.|  
|<xref:System.ServiceModel.WS2007HttpBinding>|[\<ws2007HttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|Un enlace seguro e interoperable que proporciona compatibilidad para las versiones correctas de los elementos de enlace <xref:System.ServiceModel.WSHttpBinding.Security%2A>, <xref:System.ServiceModel.ReliableSession> y <xref:System.ServiceModel.WSHttpBindingBase.TransactionFlow%2A>.|  
|<xref:System.ServiceModel.WSDualHttpBinding>|[\<wsDualHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|Un enlace seguro e interoperable adecuado para contratos de servicios dúplex o para la comunicación a través de intermediarios de SOAP.|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|[\<wsFederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|Un enlace seguro e interoperable que admite el protocolo WS-Federation, que permite a las organizaciones que están en una federación autenticar y autorizar eficazmente a los usuarios.|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|[\<ws2007FederationHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/ws2007federationhttpbinding.md)|Un enlace seguro e interoperable que deriva de <xref:System.ServiceModel.WS2007HttpBinding> y admite la seguridad federada.|  
|<xref:System.ServiceModel.NetTcpBinding>|[\<netTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|Un enlace seguro y optimizado adecuado para la comunicación entre equipos entre aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|[\<netNamedPipeBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netnamedpipebinding.md)|Un enlace seguro, confiable y optimizado que es adecuado para la comunicación en equipos entre aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetMsmqBinding>|[\<netMsmqBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|Un enlace en cola adecuado para la comunicación entre equipos entre aplicaciones de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|[\<netPeerTcpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md)|Un enlace que permite una comunicación segura entre múltiples equipos.|  
|<xref:System.ServiceModel.WebHttpBinding>|[\<webHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|Un enlace que se utiliza para configurar los extremos de los servicios web de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que se exponen mediante solicitudes HTTP en lugar de mensajes SOAP.|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|[\<msmqIntegrationBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/msmqintegrationbinding.md)|Un enlace adecuado para la comunicación entre equipos entre una aplicación de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] y aplicaciones de Message Queuing (también conocido como MSMQ) existentes.|  
  
## <a name="binding-features"></a>Características de los enlaces  
 La siguiente tabla muestra algunas de las características clave que ofrecen cada uno de los enlaces proporcionados por el sistema. Los enlaces se enumeran en la primera columna y se describe información con respecto a las características en la tabla. La siguiente tabla proporciona una clave para las abreviaturas de enlaces utilizadas. Para seleccionar un enlace, determine qué columna satisface todas las características de fila que necesite.  
  
|Enlaces|Interoperabilidad|Modo de Seguridad (valor predeterminado)|Sesión<br /><br /> (Predeterminado)|Transacciones|Dúplex|  
|-------------|----------------------|----------------------------------|-----------------------------|------------------|------------|  
|<xref:System.ServiceModel.BasicHttpBinding>|Basic Profile 1.1|(Ninguno), transporte, mensaje, mixto|Ninguno, (ninguno)|(Ninguno)|N/D|  
|<xref:System.ServiceModel.WSHttpBinding>|WS|Ninguno, transporte, (mensaje), mixto|(Ninguno), transporte, sesión confiable|(Ninguno), Sí|N/D|  
|<xref:System.ServiceModel.WS2007HttpBinding>|WS-Security, WS-Trust, WS-SecureConversation, WS-SecurityPolicy|Ninguno, transporte, (mensaje), mixto|(Ninguno), transporte, sesión confiable|(Ninguno), Sí|N/D|  
|<xref:System.ServiceModel.WSDualHttpBinding>|WS|Ninguno, (mensaje)|(Sesión confiable)|(Ninguno), Sí|Sí|  
|<xref:System.ServiceModel.WSFederationHttpBinding>|WS-Federation|Ninguno, (mensaje), mixto|(Ninguno), sesión confiable|(Ninguno), Sí|No|  
|<xref:System.ServiceModel.WS2007FederationHttpBinding>|WS-Federation|Ninguno, (mensaje), mixto|(Ninguno), sesión confiable|(Ninguno), Sí|No|  
|<xref:System.ServiceModel.NetTcpBinding>|.NET|Ninguno, (transporte), mensaje<br /><br /> Mixto|Sesión confiable, (transporte)|(Ninguno), Sí|Sí|  
|<xref:System.ServiceModel.NetNamedPipeBinding>|.NET|Ninguno,<br /><br /> (Transporte)|Ninguno, (transporte)|(Ninguno), Sí|Sí|  
|<xref:System.ServiceModel.NetMsmqBinding>|.NET|Ninguno, mensaje, (transporte), ambos|(Ninguno)|(Ninguno), Sí|No|  
|<xref:System.ServiceModel.NetPeerTcpBinding>|Del mismo nivel|Ninguno, mensaje, (transporte), mixto|(Ninguno)|(Ninguno)|Sí|  
|<xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>|MSMQ|Ninguno, (transporte)|(Ninguno)|(Ninguno), Sí|N/D|  
  
 La siguiente tabla explica las características que se encuentran en la tabla anterior.  
  
|Característica|Descripción|  
|-------------|-----------------|  
|Tipo de interoperabilidad|Nombra el protocolo o tecnología con la que el enlace asegura la interoperación.|  
|Seguridad|Especifica cómo se protege el canal:<br /><br /> -None: No se protege el mensaje SOAP y no se autentica el cliente.<br />-Transport: Requisitos de seguridad se satisfacen en la capa de transporte.<br />-Mensaje: Los requisitos de seguridad se satisfacen en la capa del mensaje.<br />-Mixto: Este modo de seguridad se conoce como `TransportWithMessageCredentials`. Administra las credenciales en el nivel de mensaje, y el nivel de transporte satisface los requisitos de integridad y confidencialidad.<br />-Ambos: Se usan ambos seguridad de nivel de transporte y del nivel de mensaje. Esta capacidad es única del <xref:System.ServiceModel.NetMsmqBinding>.|  
|Sesión|Especifica si este enlace admite contratos de sesión.|  
|Transacciones|Especifica si las transacciones están habilitadas.|  
|Dúplex|Especifica si se admiten los contratos dúplex. Observe que esta característica requiere que el enlace admita sesiones.|  
|Streaming|Especifica si se admite la transmisión por secuencias del mensaje.|  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre la creación de puntos finales](../../../../docs/framework/wcf/endpoint-creation-overview.md)  
 [Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [Programación básica de WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)
