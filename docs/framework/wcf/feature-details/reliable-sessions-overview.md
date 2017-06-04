---
title: "Informaci&#243;n general de sesiones confiables | Microsoft Docs"
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
ms.assetid: a7fc4146-ee2c-444c-82d4-ef6faffccc2d
caps.latest.revision: 30
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 30
---
# Informaci&#243;n general de sesiones confiables
La mensajería de confianza de SOAP de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] proporciona confiabilidad de transferencia de mensajes de un extremo a otro entre los extremos de SOAP.Hace esto en redes que no son confiables superando errores de transporte y errores del nivel de mensajes SOAP.En particular, proporciona una entrega basada en sesión, individual y \(opcionalmente\) ordenada de mensajes enviados a través de intermediarios de transporte o SOAP.La entrega basada en sesión agrupa los mensajes de una sesión con una ordenación opcional de mensajes.  
  
 La siguiente discusión explica el concepto de sesión confiable, cómo y cuándo utilizarla y cómo protegerla.  
  
## Sesiones confiables de WCF  
 Las sesiones confiables de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] son una implementación de mensajería confiable de SOAP tal y como la define el protocolo WS\-ReliableMessaging.  
  
 La mensajería confiable SOAP de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona una sesión confiable de un extremo a otro entre dos extremos, sin tener en cuenta el número o tipo de intermediarios que separan los extremos de la mensajería.Esto incluye a cualquier intermediario de transporte que no utilice SOAP \(por ejemplo, los servidores proxy HTTP\) o los intermediarios que utilicen SOAP \(por ejemplo, los puentes o enrutadores basados en SOAP\) que son necesarios para que los mensajes fluyan entre los extremos.Un canal de sesión confiable admite la comunicación "interactiva" para que los servicios conectados mediante este tipo de canal se ejecuten simultáneamente y puedan intercambiar y procesar mensajes bajo condiciones de latencia baja, es decir, dentro de intervalos de tiempo relativamente cortos.Este acoplamiento significa que estos componentes progresan o fallan de manera conjunta, de modo que no hay ningún aislamiento proporcionado entre ellos.  
  
 Una sesión confiable enmascara dos tipos de errores:  
  
-   Errores del nivel del mensaje de SOAP, que incluyen mensajes perdidos o duplicados y mensajes que llegan en un orden diferente del orden en el que se enviaron.  
  
-   Errores de transporte.  
  
 Una sesión confiable implementa el protocolo WS\-ReliableMessaging y una ventana de transferencia en memoria para enmascarar errores del nivel de mensaje de SOAP y restablece las conexiones en caso de errores de transporte.  
  
 Una sesión confiable proporciona para los mensajes SOAP lo que el TCP proporciona para los paquetes de IP.Una conexión de socket de TCP proporciona una transferencia única, en orden de paquetes IP entre nodos.El canal confiable proporciona el mismo tipo de transferencia confiable, pero difiere de la confiabilidad de socket de TCP de las siguientes maneras:  
  
-   La confiabilidad se produce en el nivel de mensaje de SOAP, no para un paquete de tamaño aleatorio de bytes.  
  
-   La confiabilidad se produce de una manera neutral con respecto al transporte, no solo para la transferencia sobre TCP.  
  
-   La confiabilidad no está ligada a una sesión de transporte determinada \(por ejemplo, la sesión que proporciona una conexión TCP\) y puede utilizar varias sesiones de transporte de manera simultánea o secuencial a lo largo de la duración de la sesión confiable.  
  
-   La sesión confiable se produce entre los extremos SOAP de envío y recepción, independientemente del número de conexiones de transporte requerido para la conectividad entre ellos.En resumen, la confiabilidad de TCP acaba donde lo hace la conexión de transporte, mientras que una sesión confiable proporciona confiabilidad de un extremo a otro.  
  
## Enlaces y sesiones confiables  
 Como se mencionó anteriormente, una sesión confiable es neutral con respecto al transporte y, como tal, se puede implementar sobre muchos transportes.Asimismo, una sesión confiable se puede establecer sobre muchos modelos de intercambio de mensajes, como solicitud\-respuesta o dúplex.Por consiguiente, la sesión confiable de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], se expone como una propiedad de un conjunto de enlaces.  
  
 Puede utilizar una sesión confiable en extremos que utilicen:  
  
-   Enlaces estándar de transporte basado en HTTP:  
  
    -   `WsHttpBinding` y exponen contratos de solicitud\-respuesta o unidireccionales.  
  
    -   Se puede utilizar al utilizar una sesión confiable sobre un contrato de servicio unidireccional único o de solicitud\-respuesta.  
  
    -   `WsDualHttpBinding` y exponen contratos dúplex, de solicitud\-respuesta o unidireccionales.  
  
    -   `WsFederationHttpBinding` y exponen contratos de solicitud\-respuesta o unidireccionales.  
  
-   Enlaces estándar de transporte basado en TCP:  
  
    -   `NetTcpBinding` y exponen contratos dúplex, de solicitud\-respuesta o unidireccionales.  
  
 También puede utilizar una sesión confiable en cualquier otro enlace creando un enlace personalizado, como HTTPS \(para obtener más información sobre los problemas, vea la sección "Sesiones confiables y seguridad" más adelante en este tema\) o un enlace de canalización con nombre.  
  
 Una sesión confiable se puede apilar en diferentes tipos de canal subyacentes y la forma de canal de sesión confiable resultante varía.En el cliente y el servidor, el tipo de canal de la sesión confiable admitido depende del tipo de canal subyacente que se utilice.La siguiente tabla enumera los tipos de canales de sesión admitidos en el cliente como una función del tipo de canal subyacente.  
  
|Tipos de canal de sesión confiable admitidos \(valores admitidos de `TChannel` para un tipo de canal subyacente determinado\)|`IRequestChannel`|`IRequestSessionChanne`l|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------------------------------------------------------------------------|-----------------------|------------------------------|----------------------|-----------------------------|  
|`IOutputSessionChannel`|Sí|Sí|Sí|Sí|  
|`IRequestSessionChannel`|Sí|Sí|No|No|  
|`IDuplexSessionChannel`|No|No|Sí|Sí|  
  
 Los tipos de canal admitidos son los valores disponibles para el valor del parámetro `TChannel` genérico que se pasa al método <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelFactory%60%601%28System.ServiceModel.Channels.BindingContext%29>.  
  
 La siguiente tabla enumera los tipos de canales de sesión admitidos en el servidor como una función del tipo de canal subyacente.  
  
|Tipos de canal de sesión confiable admitidos \(valores admitidos de `TChannel` para un tipo de canal subyacente determinado\)|`IReplyChannel`|`IReplySessionChannel`|`IDuplexChannel`|`IDuplexSessionChannel`|  
|-----------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------------|----------------------|-----------------------------|  
|`IInputSessionChannel`|Sí|Sí|Sí|Sí|  
|`IReplySessionChannel`|Sí|Sí|No|No|  
|`IDuplexSessionChannel`|No|No|Sí|Sí|  
  
 Los tipos de canal admitidos son los valores disponibles para el valor del parámetro `TChannel` genérico que se pasa al método <xref:System.ServiceModel.Channels.ReliableSessionBindingElement.BuildChannelListener%60%601%28System.ServiceModel.Channels.BindingContext%29>.  
  
## Sesiones confiables y seguridad  
 Proteger una sesión confiable es importante para asegurar que se autentiquen las partes que se comunican \(servicio y cliente\) y que los mensajes intercambiados en la sesión no se manipulan.Es más, es importante para garantizar la integridad de cada sesión confiable.Una sesión confiable se protege enlazándola a un contexto de seguridad que se representa y administrado mediante un canal de sesión de seguridad.El canal de seguridad proporciona una sesión de seguridad.Los tokens de seguridad intercambiados durante el establecimiento de la sesión se utilizan a continuación para proteger los mensajes de la sesión confiable.  
  
 Cuando la sesión confiable tiene lugar sobre TCP\-S, la sesión TCP está ligada a la sesión confiable y, como tal, la seguridad de transporte garantiza que la seguridad también esté ligada a la sesión confiable.En este caso, se desactiva el restablecimiento de la conexión.  
  
 La única excepción se produce al utilizar HTTPS.La sesión de capa de sockets seguros \(SSL\) no está enlazada a la sesión confiable.Esto supone una amenaza porque las sesiones que comparten un contexto de seguridad \(la sesión SSL\) no se protegen unas de otras; esto puede o no constituir una amenaza real dependiendo de la aplicación.  
  
## Uso de sesiones confiables  
 Para utilizar sesiones confiables de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], cree un extremo con un enlace que admita una sesión confiable.Utilice uno de los enlaces proporcionados por el sistema que [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] proporciona con la sesión confiable habilitada, o cree un enlace personalizado que lo haga.Los enlaces definidos por el sistema que admiten y permiten de forma predeterminada una sesión confiable incluyen:  
  
-   <xref:System.ServiceModel.WSDualHttpBinding>  
  
 Los enlaces proporcionados por el sistema que admiten una sesión confiable como una opción, pero no habilitan una de forma predeterminada, incluyen:  
  
-   <xref:System.ServiceModel.WSHttpBinding>  
  
-   <xref:System.ServiceModel.WSFederationHttpBinding>  
  
-   <xref:System.ServiceModel.NetTcpBinding>  
  
 Para obtener un ejemplo sobre cómo crear un enlace personalizado, vea [Creación de un enlace personalizado de sesión confiable con HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).  
  
 Para ver una discusión sobre los enlaces de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que admiten sesiones confiables, vea [Enlaces proporcionados por el sistema](../../../../docs/framework/wcf/system-provided-bindings.md).  
  
## Cuándo utilizar sesiones confiables  
 Es importante entender cuándo usar sesiones confiables en la aplicación.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] admite sesiones confiables entre los extremos que están activos y en funcionamiento al mismo tiempo.Si su aplicación requiere que uno de los extremos no esté disponible durante un tiempo, puede utilizar las colas para lograr la confiabilidad.  
  
 Si el escenario requiere que dos extremos estén conectados sobre TCP, puede que TCP sea suficiente para proporcionar el intercambio de mensajes confiable, aunque no es necesario utilizar una sesión confiable; TCP asegura que los paquetes llegan en orden y solo una vez.  
  
 Si su escenario tiene cualquiera de las características siguientes, debe considerar seriamente utilizar una sesión confiable:  
  
-   Intermediarios SOAP, como enrutadores SOAP.  
  
-   Intermediarios proxy o puentes de transporte.  
  
-   Conectividad intermitente.  
  
-   Sesiones sobre HTTP.  
  
## Vea también  
 [Utilización de enlaces para configurar servicios y clientes](../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)   
 [Sesión de confianza de WS](../../../../docs/framework/wcf/samples/ws-reliable-session.md)