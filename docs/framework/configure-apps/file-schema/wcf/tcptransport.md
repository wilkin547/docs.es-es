---
title: "&lt;tcpTransport&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;tcpTransport&gt;
Define un transporte del TCP que puede ser utilizado por un canal para la transferencia de mensajes de un enlace personalizado.  
  
## Sintaxis  
  
```  
  
<tcpTransport   
    listenBacklog="Integer"  
        portSharingEnabled="Boolean"  
    teredoEnabled="Boolean"  
    transferMode=”Buffered/Streamed”  
        <connectionPoolSettings  
          groupName=”String”  
        idleTimeout"TimeSpan"  
        leaseTimeout="TimeSpan"  
        maxOutboundConnectionsPerEndpopint=”Integer” />  
/>  
```  
  
## Atributos y elementos  
 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### Atributos  
  
|Atributo|Descripción|  
|--------------|-----------------|  
|channelInitializationTimeout|El tiempo máximo que un canal puede estar en el estado de inicialización antes de que se desconecte, en segundos.  Esta cuota contiene el tiempo que una conexión TCP puede tardar en autenticarse a sí misma mediante el protocolo de trama de mensajes de .Net.  Un cliente debe enviar algunos datos iniciales antes de que el servidor tenga información suficiente para realizar la autenticación.  El valor predeterminado es 30 segundos.|  
|listenBacklog|El número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web.  El atributo `connectionLeaseTimeout` limita el tiempo durante el cual el cliente espera a ser conectado antes de iniciar una excepción de conexión.  Esta es una propiedad del nivel de socket que controla el número máximo de solicitudes de conexión en cola que pueden estar pendientes para un servicio web.  Cuando ListenBacklog es demasiado bajo, WCF dejará de aceptar solicitudes y por consiguiente quitará las conexiones nuevas hasta que el servidor confirme algunas de las conexiones en cola existentes. El valor predeterminado es 16 \* número de procesadores.|  
|portSharingEnabled|Un valor booleano que especifica si el uso compartido de puerto TCP está habilitado para esta conexión.  Si éste es `false`, cada enlace utilizará su propio puerto exclusivo.  De manera predeterminada, es `false`.<br /><br /> Este valor sólo es pertinente a los servicios.  Los clientes no se ven afectados.<br /><br /> Para usar esta configuración se necesita que se habilite el servicio de puerto TCP compartido Windows Communication Foundation \(WCF\), cambiando su tipo de inicio a manual o automático.|  
|teredoEnabled|Un valor booleano que especifica si Teredo \(una tecnología para direccionar clientes que están detrás de firewalls\) está habilitada.  De manera predeterminada, es `false`.<br /><br /> Esta propiedad habilita Teredo para el socket TCP subyacente.  Para obtener más información, vea la [información general sobre Teredo](http://go.microsoft.com/fwlink/?LinkId=95339).<br /><br /> Esta propiedad solo se aplica en [!INCLUDE[wxpsp2](../../../../../includes/wxpsp2-md.md)] y [!INCLUDE[ws2003](../../../../../includes/ws2003-md.md)].  [!INCLUDE[wv](../../../../../includes/wv-md.md)] tiene una opción de configuración del equipo para Teredo, por lo que al ejecutar Vista, se omite esta propiedad.  Teredo requiere que los equipos de servicio y del cliente tengan la pila de Microsoft IPv6 instalada y correctamente configurada para el uso de Teredo.  Para obtener más información sobre cómo configurar Teredo, vea la [información general sobre Teredo](http://go.microsoft.com/fwlink/?LinkId=95339).  Para obtener más información, vea [Centros de tecnología de Windows Server 2003](http://go.microsoft.com/fwlink/?LinkId=49888).|  
  
### Elementos secundarios  
 Ninguna  
  
### Elementos primarios  
  
|Elemento|Descripción|  
|--------------|-----------------|  
|[\<enlace\>](../../../../../docs/framework/misc/binding.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## Comentarios  
 Este transporte utiliza los URI del formulario "net.tcp:\/\/hostname:port\/path."  Otros componentes URI son opcionales.  
  
 El elemento `tcpTransport` es el punto inicial para crear un enlace personalizado que implementa el protocolo de transporte TCP.  Este transporte está optimizado para la comunicación de WCF a WCF.  
  
## Vea también  
 <xref:System.ServiceModel.Configuration.TcpTransportElement>   
 <xref:System.ServiceModel.Channels.TcpTransportBindingElement>   
 <xref:System.ServiceModel.Channels.TransportBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Transportes](../../../../../docs/framework/wcf/feature-details/transports.md)   
 [Elección del transporte](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)   
 [Enlaces](../../../../../docs/framework/wcf/bindings.md)   
 [Extensión de enlaces](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Enlaces personalizados](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)