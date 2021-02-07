---
description: 'Más información acerca de: <msmqIntegrationBinding>'
title: <msmqIntegrationBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- msmqIntegrationBinding Element
ms.assetid: edf277f3-e3bf-4ed8-9f55-83b5788430a7
ms.openlocfilehash: 2745fdf1576d66e3e7c0c74d9b7d6f008fac88b8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99684248"
---
# \<msmqIntegrationBinding>

Define un enlace que proporciona la compatibilidad de uso de colas enrutando los mensajes a través de MSMQ.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqIntegrationBinding>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<msmqIntegrationBinding>
  <binding closeTimeout="TimeSpan"
           customDeadLetterQueue="Uri"
           deadLetterQueue="Uri"
           durable="Boolean"
           exactlyOnce="Boolean"
           maxReceivedMessageSize="Integer"
           maxRetryCycles="Integer"
           name="String"
           openTimeout="TimeSpan"
           receiveContextEnabled="Boolean"
           receiveErrorHandling="Drop/Fault/Move/Reject"
           receiveTimeout="TimeSpan"
           receiveRetryCount="Integer"
           retryCycleDelay="TimeSpan"
           sendTimeout="TimeSpan"
           serializationFormat="XML/Binary/ActiveX/ByteArray/Stream"
           timeToLive="TimeSpan"
           useMsmqTracing="Boolean"
           useSourceJournal="Boolean">
  </binding>
</msmqIntegrationBinding>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|closeTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de cierre para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|customDeadLetterQueue|Un URI que contiene la ubicación de la cola de componentes con problemas de entrega por aplicación, donde se colocan los mensajes que han expirado o cuya transferencia o envío han fallado.<br /><br /> La cola de componentes con problemas de entrega es una cola en el administrador de colas de la aplicación de envío para los mensajes caducados que no se hayan entregado.<br /><br /> El URI que es especificado por <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> debe utilizar el esquema de net.msmq.|  
|deadLetterQueue|<xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A>. Valor que especifica qué tipo de cola de componentes con problemas de entrega hay que usar, si hay alguna.<br /><br /> La cola de componentes con problemas de entrega es la ubicación a la que se transfieren los mensajes que no han podido ser entregados a la aplicación.<br /><br /> Para los mensajes que requieren la convicción exactlyOnce (por ejemplo, el atributo `exactlyOnce` está establecido en `true`), este atributo tiene como valor predeterminado la cola de mensajes transaccionales no enviados para todo el sistema en MSMQ.<br /><br /> Para los mensajes que no requieren convicciones, este atributo tiene como valor predeterminado `null`.|  
|durable|Valor de tipo booleano que indica si el mensaje es duradero o volátil en la cola. Un mensaje duradero sobrevive un bloqueo de administrador de cola, mientras que un mensaje volátil no. Los mensajes volátiles son útiles cuando las aplicaciones requieren la menor latencia y toleran la pérdida de mensajes ocasional. Si el atributo `exactlyOnce` está establecido en `true`, los mensajes deben ser duraderos. De manera predeterminada, es `true`.|  
|exactlyOnce|Valor de tipo booleano que indica si cada mensaje se entrega sólo una vez. Se notificará al remitente a continuación de los errores de la entrega. Cuando `durable` es `false`, se omite este atributo y los mensajes se transfieren sin convicción de la entrega. De manera predeterminada, es `true`. Para obtener más información, vea <xref:System.ServiceModel.MsmqBindingBase.ExactlyOnce%2A>.|  
|maxReceivedMessageSize|Un entero positivo que define el tamaño del mensaje máximo, en bytes, incluyendo encabezados, que está procesado por este enlace. El remitente de un mensaje que supere este límite recibirá un error SOAP. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536. Este límite en el tamaño del mensaje tiene como objetivo limitar la exposición a ataques de denegación de servicio (DoS).|  
|maxRetryCycles|Un entero que indica el número de ciclos de reintento utilizado por la característica de detección de mensaje dudoso. Un mensaje se vuelve un mensaje dudoso cuando produce un error en todos los intentos de entrega de todos los ciclos. El valor predeterminado es 2. Para obtener más información, vea <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A>.|  
|name|Cadena que contiene el nombre de configuración del enlace. Este valor debe ser único porque se usa como identificación del enlace. A partir de .NET Framework 4, no es necesario que los enlaces y los comportamientos tengan un nombre. Para obtener más información sobre la configuración predeterminada y los enlaces y comportamientos sin nombre, vea [configuración simplificada](../../../wcf/simplified-configuration.md) y [configuración simplificada para servicios WCF](../../../wcf/samples/simplified-configuration-for-wcf-services.md).|  
|openTimeout|Valor de la estructura <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de apertura para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|receiveErrorHandling|Un valor <xref:System.ServiceModel.ReceiveErrorHandling> que especifica cómo se administran mensajes dudosos y que no se pueden enviar.|  
|receiveRetryCount|Un entero que especifica el número máximo de intentos inmediatos que el administrador de cola debería intentar si se produce un error en la transmisión de un mensaje de la cola de aplicación a la aplicación.<br /><br /> Si se alcanza el número máximo de intentos de entrega y la aplicación no tiene acceso al mensaje, a continuación, el mensaje se envía a una cola de reintento para intentar la entrega más tarde. La duración antes de que el mensaje se transfiera de vuelta a la cola emisora es controlada por `retryCycleDelay`. Si los ciclos de reintento alcanzan el valor `maxRetryCycles`, entonces el mensaje se envía a la cola de mensajes dudosos o se envía al remitente una confirmación de que no se pudo realizar la acción.|  
|receiveTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de recepción para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:10:00.|  
|receiveContextEnabled|Valor de tipo booleano que especifica si está habilitado el contexto de recepción para procesar los mensajes en colas. Cuando se establece en `true` , un servicio puede "inspeccionar" un mensaje en la cola para empezar a procesarlo y, si algo sale mal y se produce una excepción, permanece en la cola. Los servicios también pueden "bloquear" los mensajes para volver a intentar el procesamiento en un momento posterior. ReceiveContext proporciona un mecanismo para "completar" el mensaje una vez procesado de modo que se pueda quitar de la cola. Los mensajes ya no se leen ni se reescriben en las colas a través de la red, y los mensajes individuales no se devuelven entre las distintas instancias de servicio durante el procesamiento.|  
|retryCycleDelay|Un valor TimeSpan que especifica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente. El valor define sólo el tiempo de espera mínimo porque el tiempo de espera real puede ser más largo. El valor predeterminado es 00:30:00. Para obtener más información, vea <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A>.|  
|sendTimeout|Un valor <xref:System.TimeSpan> que especifica el intervalo de tiempo del que dispone una operación de envío para completarse. Este valor debe ser mayor o igual que <xref:System.TimeSpan.Zero>. El valor predeterminado es 00:01:00.|  
|serializationFormat|Define el formato usado para la serialización del cuerpo del mensaje. Este atributo es del tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessageSerializationFormat>.|  
|timeToLive|Un valor TimeSpan que especifica cuánto tiempo son válidos los mensajes antes de expirar y ser colocados en la cola de mensajes no enviados. El valor predeterminado es 1.00:00:00.<br /><br /> Este atributo se establece para asegurarse de que los mensajes que dependen del tiempo no se vuelvan obsoletos antes de ser procesados por las aplicaciones receptoras. Un mensaje en una cola expira si no es consumido por la aplicación receptora dentro del intervalo de tiempo especificado. Los mensajes caducados se envían a la cola especial llamada cola de mensajes no enviados. La ubicación de la cola de mensajes no enviados se establece con el atributo `DeadLetterQueue` o con el valor predeterminado adecuado, basado en garantías.|  
|useMsmqTracing|Valor de tipo booleano que especifica si los mensajes procesados por este enlace se deberían seguir paso a paso. De manera predeterminada, es `false`. Si se habilita la traza, los mensajes de informe se crean y envían a la cola de informes cada vez que el mensaje sale o llega a un equipo Message Queuing.|  
|useSourceJournal|Valor de tipo booleano que especifica las copias de mensajes procesadas por este enlace debería estar almacenado en el diario de origen. De manera predeterminada, es `false`.<br /><br /> Las aplicaciones en cola que quieran mantener un registro de mensajes que han dejado la cola de salida del equipo pueden copiar los mensajes a una cola del diario. Cuando un mensaje deja la cola de salida y se recibe una confirmación de que se ha recibido el mensaje en el equipo de destino, se mantiene una copia del mensaje en la cola del diario de sistema del equipo remitente.|  
  
## <a name="serializationformat-attribute"></a>Atributo {serializationFormat}  
  
|Value|Descripción|  
|-----------|-----------------|  
|Xml|Formato XML|  
|Binary|Formato binario|  
|ActiveX|Formato ActiveX|  
|ByteArray|Serializa el objeto a una matriz de bytes.|  
|STREAM|El cuerpo con formato como una secuencia|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<security>](security-of-msmqintegrationbinding.md)|Define la configuración de seguridad del enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqIntegrationSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|Este elemento contiene una colección de enlaces estándar y personalizados.|  
  
## <a name="remarks"></a>Observaciones  

 Este elemento de enlace se puede usar para permitir que las aplicaciones de Windows Communication Foundation (WCF) envíen y reciban mensajes desde aplicaciones MSMQ existentes que utilicen COM, API nativas de MSMQ o los tipos definidos en el <xref:System.Messaging?displayProperty=nameWithType> espacio de nombres. puede utilizar este elemento de configuración para especificar las maneras de direccionar la cola, las garantías de transferencia, si los mensajes deben estar almacenados de forma duradera y cómo deben proteger Para obtener más información, consulte [Cómo: intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](../../../wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md).  
  
## <a name="example"></a>Ejemplo  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <msmqIntegrationBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 deadLetterQueue="net.msmq://localhost/blah"
                 durable="true"
                 exactlyOnce="true"
                 maxReceivedMessageSize="1000"
                 maxImmediateRetries="11"
                 maxRetryCycles="12"
                 poisonMessageHandling="Disabled"
                 rejectAfterLastRetry="false"
                 retryCycleDelay="00:05:55"
                 timeToLive="00:11:11"
                 useSourceJournal="true"
                 useMsmqTracing="true"
                 serializationFormat="Binary">
          <security mode="None" />
        </binding>
      </msmqIntegrationBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Configuration.MsmqIntegrationBindingElement>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>
- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBindingElement>
- [\<binding>](bindings.md)
- [Enlaces](../../../wcf/bindings.md)
- [Configuración de enlaces proporcionados por el sistema](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Utilización de enlaces para configurar servicios y clientes](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
