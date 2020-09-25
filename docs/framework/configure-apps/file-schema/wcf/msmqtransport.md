---
title: <msmqTransport>
ms.date: 03/30/2017
ms.assetid: 19d89f35-76ac-49dc-832b-e8bec2d5e33b
ms.openlocfilehash: 6117a2d4323dce8c2772da46096164639b27032a
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204663"
---
# \<msmqTransport>

Produce un canal a los mensajes de las transferencias en el transporte de MSMQ cuando está incluido en un enlace personalizado.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<msmqTransport>**  
  
## <a name="syntax"></a>Sintaxis  
  
```xml  
<msmqTransport customDeadLetterQueue="Uri"
               deadLetterQueue="Custom/None/System"
               durable="Boolean"
               exactlyOnce="Boolean"
               manualAddressing="Boolean"
               maxBufferPoolSize="Integer"
               maxImmediateRetries="Integer"
               maxPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               maxRetryCycles="Integer"
               queueTransferProtocol="Native/Srmp/SrmpSecure"
               rejectAfterLastRetry="Boolean"
               retryCycleDelay="TimeSpan"
               timeToLive="TimeSpan"
               useActiveDirectory="Boolean"
               useSourceJournal="Boolean"
               useMsmqTracing="Boolean"
               ...>
  <msmqTransportSecurity>
  </msmqTransportSecurity>
</msmqTransport>
```  
  
## <a name="attributes-and-elements"></a>Atributos y elementos  

 En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.  
  
### <a name="attributes"></a>Atributos  
  
|Atributo|Descripción|  
|---------------|-----------------|  
|customDeadLetterQueue|URI que indica la ubicación de la cola de mensajes con problemas de entrega por aplicación, donde se transfieren los mensajes que han expirado o cuya entrega a la aplicación ha tenido errores.<br /><br /> Para los mensajes que requieren la convicción ExactlyOnce (es decir, `exactlyOnce` está establecido en `true`), este atributo tiene como valor predeterminado la cola de mensajes transaccionales no enviados para todo el sistema en MSMQ.<br /><br /> Para los mensajes que no requieren convicciones (está disponible decir, `exactlyOnce` está establecido en `false`), este atributo tiene como valor predeterminado `null`.<br /><br /> El valor debe usar el esquema de net.msmq. El valor predeterminado es `null`.<br /><br /> Si `deadLetterQueue` se establece en `None` o `System`, este atributo debe establecerse en `null`. Si este atributo no es `null`, `deadLetterQueue` debe establecerse en `Custom`.|  
|deadLetterQueue|Especifica el tipo de cola de mensajes con problemas de entrega que se va a usar.<br /><br /> Los valores válidos incluyen<br /><br /> -Custom: cola de mensajes fallidos personalizada.<br />-None: no se utilizará ninguna cola de mensajes fallidos.<br />-System: Use la cola mensajes fallidos del sistema.<br /><br /> Este atributo es del tipo DeadLetterQueue.|  
|durable|Un valor booleano que especifica si los mensajes procesados por este enlace son duraderos o volátiles. De manera predeterminada, es `true`.<br /><br /> Un mensaje duradero sobrevive un bloqueo de administrador de cola, mientras que un mensaje volátil no. Los mensajes volátiles son útiles cuando las aplicaciones requieren la menor latencia y toleran la pérdida de mensajes ocasional.<br /><br /> Si `exactlyOnce` está establecido en `true`, los mensajes deben ser duraderos.|  
|exactlyOnce|Un valor booleano que especifica si los mensajes procesados por este enlace se recibirán sólo una vez. De manera predeterminada, es `true`.<br /><br /> Un mensaje se puede enviar con o sin garantías. Una garantía permite a una aplicación asegurarse de que un mensaje enviado alcanza la cola de mensajes receptora, o si no lo hiciera, la aplicación puede determinarlo leyendo la cola de mensajes con problemas de entrega.<br /><br /> `exactlyOnce`, cuando se establece en `true`, indica que MSMQ garantizará que un mensaje enviado se entrega una única vez a la cola de mensajes receptora, y si se produce un error en la entrega, el mensaje se envía a la cola de mensajes con problemas de entrega.<br /><br /> Los mensajes enviados con `exactlyOnce` establecidos en `true` sólo se deben enviar a una cola transaccional.|  
|manualAddressing|Un valor booleano que permite al usuario tomar el control del direccionamiento del mensaje. Esta propiedad normalmente se usa en escenarios del enrutador, donde la aplicación determina a cuál de los destinos va a enviar un mensaje.<br /><br /> Si se establece en `true`, el canal supone que el mensaje ya se ha direccionado y no le agrega ninguna información adicional. El usuario puede direccionar a continuación individualmente cada mensaje.<br /><br /> Cuando se establece en `false`, la Windows Communication Foundation predeterminada (WCF) que direcciona el mecanismo crea automáticamente las direcciones para todos los mensajes.<br /><br /> El valor predeterminado es `false`.|  
|maxBufferPoolSize|Un entero positivo que especifica el tamaño máximo del grupo de búferes. El valor predeterminado es 524288.<br /><br /> Muchas partes de los búferes de uso WCF. Crear y destruir búferes cada vez que se usan es caro, y la recolección de elementos no utilizados para los búferes también es cara. Con grupos de búferes, puede tomar un búfer del grupo, usarlo y devolverlo al grupo una vez haya terminado. Así se evita la sobrecarga al crear y destruir búferes.|  
|maxImmediateRetries|Un entero que especifica el número máximo de reintentos inmediatos en un mensaje que se lee desde la cola de la aplicación. El valor predeterminado es 5.<br /><br /> Si se alcanza el número máximo de reintentos inmediatos para el mensaje y la aplicación no consume el mensaje, a continuación, el mensaje se envía a una cola de reintento para volver a intentar su entrega más tarde. Si no se especifican ciclos de reintento, entonces el mensaje se envía a la cola de mensajes dudosos o se envía al remitente una confirmación de que no se pudo realizar la acción.|  
|maxPoolSize|Un entero positivo que especifica el tamaño máximo del grupo. El valor predeterminado es 524288.|  
|maxReceivedMessageSize|Un entero positivo que especifica el tamaño de mensaje máximo en bytes incluidas los encabezados . El remitente de un mensaje recibe un error SOAP cuando el mensaje es demasiado grande para el receptor. El destinatario quita el mensaje y crea una entrada del evento en el registro de seguimiento. El valor predeterminado es 65536.|  
|maxRetryCycles|Un entero que especifica el número máximo de ciclos de reintento para intentar la entrega de mensajes a la aplicación receptora. El valor predeterminado es <xref:System.Int32.MaxValue>.<br /><br /> Un ciclo de reintento único intenta entregar un mensaje a una aplicación un número especificado de veces. El atributo `maxImmediateRetries` establece el número de intentos realizados. Si la aplicación no consigue consumir el mensaje una vez agotados los intentos en la entrega, el mensaje se envía a una cola de reintento. Los ciclos de reintento subsiguientes consisten en que el mensaje vuelva de la cola de reintento a la cola de aplicación para intentar de nuevo la entrega a la aplicación, después de un retraso especificado por el atributo `retryCycleDelay`. El atributo `maxRetryCycles` especifica el número de ciclos de reintento que la aplicación usa para intentar entregar el mensaje.|  
|queueTransferProtocol|Especifica el transporte del canal de comunicación en cola que usa este enlace. Los valores válidos son<br /><br /> -Native: usar el protocolo MSMQ nativo.<br />-SRMP: usar el protocolo de mensajería confiable de SOAP (SRMP).<br />-SrmpSecure: Use el transporte seguro del Protocolo de mensajería confiable de SOAP (SRMPS).<br /><br /> Este atributo es del tipo <xref:System.ServiceModel.QueueTransferProtocol>.<br /><br /> Puesto que MSMQ no admite el direccionamiento de Active Directory cuando se usa el protocolo de mensajería confiable de SOAP, no debe establecer este atributo en SRMP o Srmps cuando `useActiveDirectory` se establece en `true` .|  
|rejectAfterLastRetry|Un valor booleano que especifica los que la acción va a realizar para un mensaje en el que se ha producido un error tras haber intentado el número máximo de reintentos.<br /><br /> `true` significa que se devuelve al remitente una confirmación de que no se pudo realizar la acción y se coloca el mensaje; `false` significa que el mensaje se envía a la cola de mensajes dudosos. El valor predeterminado es `false`.<br /><br /> Si el valor es `false`, la aplicación receptora puede leer la cola de mensajes dudosos para procesarlos (es decir, mensajes que han producido un error en la entrega).<br /><br /> MSMQ 3.0 no permite devolver al remitente una confirmación de que no se pudo realizar la acción, por lo que este atributo se omitirá en MSMQ 3.0.|  
|retryCycleDelay|Un <xref:System.TimeSpan> que especifica el tiempo de retardo entre los ciclos de reintento al intentar entregar un mensaje que no se pudo entregar inmediatamente. El valor predeterminado es 00:10:00.<br /><br /> Un ciclo de reintento único intenta entregar un mensaje a una aplicación receptora un número especificado de veces. El atributo `maxImmediateRetries` especifica el número de intentos realizados. Si la aplicación no consigue consumir el mensaje después del número especificado de intentos inmediatos, el mensaje se envía a una cola de reintento. Los ciclos de reintento subsiguientes consisten en que el mensaje vuelva de la cola de reintento a la cola de aplicación para intentar de nuevo la entrega a la aplicación, después de un retraso especificado por el atributo `retryCycleDelay`. El atributo `maxRetryCycles` especifica el número de ciclos de reintento.|  
|timeToLive|Un <xref:System.TimeSpan> que especifica cuánto tiempo son válidos los mensajes antes de expirar y ser colocados en la cola de mensajes no enviados. El valor predeterminado es 1.00:00:00 (que significa 1 día).<br /><br /> Este atributo se establece para asegurarse de que los mensajes que dependen del tiempo no se vuelvan obsoletos antes de ser procesados por las aplicaciones receptoras. Un mensaje en una cola expira si no es consumido por la aplicación receptora dentro del intervalo de tiempo especificado. Los mensajes caducados se envían a la cola especial llamada cola de mensajes no enviados. La ubicación de la cola de mensajes no enviados se establece con el atributo `customDeadLetterQueue` o con el valor predeterminado adecuado, basado en garantías.|  
|UseActiveDirectory|Un valor booleano que especifica si las direcciones de la cola deberían convertirse utilizando Active Directory.<br /><br /> Las direcciones de la cola de MSMQ pueden estar compuestas de nombres de ruta o nombres de formato directos. Con un nombre de formato directo, MSMQ resuelve el nombre del equipo mediante DNS, NetBIOS o IP. Con un nombre de ruta, MSMQ resuelve el nombre del equipo mediante Active Directory. De forma predeterminada, el transporte de colas de Windows Communication Framework (WCF) convierte el URI de una cola de mensajes en un nombre de formato directo. Al establecer este atributo en `true`, una aplicación puede especificar que el transporte en cola debería resolver el nombre del equipo mediante Active Directory en lugar de DNS, NetBIOS o IP.|  
|useMsmqTracing|Valor de tipo booleano que especifica si los mensajes procesados por este enlace se deberían seguir paso a paso. El valor predeterminado es `false`.<br /><br /> Si se habilita la traza, los mensajes de informe se crean y envían a la cola de informes cada vez que el mensaje sale o llega a un equipo Message Queuing.|  
|useSourceJournal|Un valor booleano que especifica si las copias de mensajes procesados por este enlace deberían almacenarse en la cola de diario de origen. El valor predeterminado es `false`.<br /><br /> Las aplicaciones en cola que quieran mantener un registro de mensajes que han dejado la cola de salida del equipo pueden copiar los mensajes a una cola del diario. Cuando un mensaje deja la cola de salida y se recibe una confirmación de que se ha recibido el mensaje en el equipo de destino, se mantiene una copia del mensaje en la cola del diario de sistema del equipo remitente.|  
  
### <a name="child-elements"></a>Elementos secundarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<msmqTransportSecurity>](msmqtransportsecurity.md)|Especifica la configuración de seguridad de transporte para este enlace. Este elemento es del tipo <xref:System.ServiceModel.Configuration.MsmqTransportSecurityElement>.|  
  
### <a name="parent-elements"></a>Elementos primarios  
  
|Elemento|Descripción|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|Define todas las funcionalidades de enlace del enlace personalizado.|  
  
## <a name="remarks"></a>Observaciones  

 El elemento `msmqTransport` permite al usuario establecer las propiedades del canal de comunicación en cola. El canal de comunicación en cola utiliza Message Queuing para su transporte.  
  
 Este elemento de enlace es el elemento de enlace predeterminado utilizado por el enlace estándar de Message Queuing (`netMsmqBinding`).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.ServiceModel.Configuration.MsmqTransportElement>
- <xref:System.ServiceModel.Channels.MsmqTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [Colas en WCF](../../../wcf/feature-details/queues-in-wcf.md)
- [Transportes](../../../wcf/feature-details/transports.md)
- [Elección del transporte](../../../wcf/feature-details/choosing-a-transport.md)
- [Enlaces](../../../wcf/bindings.md)
- [Extensión de enlaces](../../../wcf/extending/extending-bindings.md)
- [Enlaces personalizados](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
