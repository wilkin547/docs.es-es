---
description: 'Más información sobre: procesamiento por lotes de mensajes en una transacción'
title: Mensajes por lotes en una transacción
ms.date: 03/30/2017
helpviewer_keywords:
- batching messages [WCF]
ms.assetid: 53305392-e82e-4e89-aedc-3efb6ebcd28c
ms.openlocfilehash: 0c84d87bc043f4ce1ae4d0a7674e862aa10011ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99643701"
---
# <a name="batching-messages-in-a-transaction"></a>Mensajes por lotes en una transacción

Las aplicaciones en cola utilizan las transacciones para garantizar la exactitud y la entrega fiable de mensajes. Las transacciones, sin embargo, son operaciones caras y pueden reducir dramáticamente el rendimiento de los mensajes. Una manera de mejorar el rendimiento de los mensajes consiste en hacer que una aplicación lea y procese varios mensajes dentro de una transacción única. La balanza está entre el rendimiento y la recuperación: a medida que el número de mensajes de un lote aumenta, lo hace la cantidad de trabajo de recuperación requerida si se deshacen las transacciones. Es importante tener en cuenta la diferencia entre los mensajes por lotes en una transacción y en sesiones. Una *sesión* es una agrupación de mensajes relacionados que se procesan mediante una sola aplicación y se confirman como una sola unidad. Las sesiones se utilizan generalmente cuando se debe procesar conjuntamente un grupo de mensajes relacionados. Un ejemplo de esto es el sitio web de una tienda en línea. Los *lotes* se usan para procesar varios mensajes no relacionados de forma que aumente el rendimiento de los mensajes. Para obtener más información acerca de las sesiones, consulte [agrupar los mensajes en cola en una sesión](grouping-queued-messages-in-a-session.md). Los mensajes de un lote también se procesan mediante una aplicación única y se confirman como una sola unidad, pero no puede haber ninguna relación entre los mensajes del lote. Los mensajes por lotes en una transacción son una optimización que no cambia cómo se ejecuta la aplicación.  
  
## <a name="entering-batching-mode"></a>Introducción al modo de procesamiento por lotes  

 El comportamiento de punto de conexión <xref:System.ServiceModel.Description.TransactedBatchingBehavior> controla el procesamiento por lotes. Al agregar este comportamiento de extremo a un punto de conexión de servicio, se indica Windows Communication Foundation (WCF) para procesar por lotes los mensajes de una transacción. No todos los mensajes requieren una transacción, por lo que solo los mensajes que requieran una transacción se colocan en un lote y solo se tienen en cuenta los mensajes enviados desde las operaciones marcadas con `TransactionScopeRequired`  =  `true` y `TransactionAutoComplete`  =  `true` para un lote. Si todas las operaciones en el contrato de servicio se marcan con `TransactionScopeRequired`  =  `false` y `TransactionAutoComplete`  =  `false` , el modo de procesamiento por lotes nunca se escribe.  
  
## <a name="committing-a-transaction"></a>Confirmar una transacción  

 Una transacción por lotes se confirma en función de lo siguiente:  
  
- `MaxBatchSize`. Una propiedad del comportamiento <xref:System.ServiceModel.Description.TransactedBatchingBehavior>. Esta propiedad determina el número máximo de mensajes que se colocan en un lote. Cuando se alcanza este número, se confirma el lote. Esto valor no es un límite estricto, es posible confirmar un lote antes de recibir este número de mensajes.  
  
- `Transaction Timeout`. Después de que el 80 por ciento del tiempo de espera de la transacción haya transcurrido, se confirma el lote y se crea uno nuevo. Esto significa que si queda el 20 por ciento o menos del tiempo proporcionado para que una transacción se complete, se confirma el lote.  
  
- `TransactionScopeRequired`. Al procesar un lote de mensajes, si WCF encuentra uno que tiene `TransactionScopeRequired`  =  `false` , confirma el lote y vuelve a abrir un nuevo lote en la recepción del primer mensaje con `TransactionScopeRequired`  =  `true` y `TransactionAutoComplete`  =  `true` .  
  
- Si no existe ningún mensaje más en la cola, se confirma el lote actual, aunque no se haya alcanzado el `MaxBatchSize` o no haya transcurrido el 80 por ciento del tiempo de espera de la transacción.  
  
## <a name="leaving-batching-mode"></a>Salir del modo de procesamiento por lotes  

 Si un mensaje en un lote hace que la transacción se anule, se producen los pasos siguientes:  
  
1. Se deshace el lote completo de mensajes.  
  
2. Los mensajes se leen de uno en uno hasta que el número de mensajes leídos supera el doble del tamaño del lote máximo.  
  
3. Se vuelve a entrar en el modo de procesamiento por lotes.  
  
## <a name="choosing-the-batch-size"></a>Elección del tamaño del lote  

 El tamaño de un lote depende de la aplicación. El método empírico es la mejor manera de llegar a un tamaño de lote óptimo para la aplicación. Es importante recordar al elegir un tamaño de lote para elegir el tamaño según el modelo de implementación real de su aplicación. Por ejemplo, al implementar la aplicación, si necesita un servidor SQL en un equipo remoto y una transacción que abarque la cola y el servidor SQL, el tamaño del lote se determina mejor ejecutando esta configuración exacta.  
  
## <a name="concurrency-and-batching"></a>Simultaneidad y procesamiento por lotes  

 Para aumentar el rendimiento, puede hacer que se ejecuten muchos lotes de manera simultánea. Estableciendo `ConcurrencyMode.Multiple` en `ServiceBehaviorAttribute`, se habilita el procesamiento por lotes simultáneo.  
  
 La *limitación del servicio* es un comportamiento del servicio que se usa para indicar el número máximo de llamadas simultáneas que se pueden realizar en el servicio. Cuando se utiliza con procesamiento por lotes, esto se interpreta como cuántos lotes simultáneos se pueden ejecutar. Si no se establece la limitación del servicio, WCF toma como valor predeterminado el número máximo de llamadas simultáneas a 16. De este modo, si se agregara el comportamiento de procesamiento por lotes de forma predeterminada, podrían estar activos un máximo de 16 lotes al mismo tiempo. Es mejor ajustar la limitación de peticiones del servicio y el procesamiento por lotes en función de su capacidad. Por ejemplo, si la cola tiene 100 mensajes y se desea un lote de 20, tener el número máximo de llamadas simultáneas establecido en 16 no sería útil porque, dependiendo del rendimiento, 16 transacciones podrían estar activas, parecido a no tener el procesamiento por lotes activado. Por consiguiente, al afinar para mejorar el rendimiento, no tenga el procesamiento por lotes simultáneo o tenga el procesamiento por lotes simultáneo con el tamaño correcto de limitación de peticiones del servicio.  
  
## <a name="batching-and-multiple-endpoints"></a>Procesamiento por lotes y varios extremos  

 Un punto de conexión está compuesto por una dirección y un contrato. Puede haber varios puntos de conexión que comparten el mismo enlace. Es posible que dos puntos de conexión compartan el mismo enlace y escuchen al Identificador uniforme de recursos (URI) o dirección de la cola. Si dos puntos de conexión están leyendo desde la misma cola, y se agrega el comportamiento del procesamiento por lotes con transacciones a ambos puntos de conexión, podría surgir un conflicto en los tamaños de lotes especificados. Esto se resuelve implementando el procesamiento por lotes utilizando el tamaño de lote mínimo especificado entre los dos comportamientos de procesamiento por lotes con transacciones. En este escenario, si uno de los puntos de conexión no especifica el procesamiento por lotes con transacciones, ambos puntos de conexión no usarán el procesamiento por lotes.  
  
## <a name="example"></a>Ejemplo  

 El siguiente ejemplo muestra cómo especificar el `TransactedBatchingBehavior` en un archivo de configuración.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="TransactedBatchingBehavior"
              maxBatchSize="100" />
  </endpointBehaviors>
</behaviors>
```  
  
 En el siguiente ejemplo se muestra cómo especificar mediante código <xref:System.ServiceModel.Description.TransactedBatchingBehavior>.  
  
```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
     ServiceEndpoint sep = ServiceHost.AddServiceEndpoint(typeof(IOrderProcessor), new NetMsmqBinding(), "net.msmq://localhost/private/ServiceModelSamplesTransacted");
     sep.Behaviors.Add(new TransactedBatchingBehavior(100));

     // Open the ServiceHost to create listeners and start listening for messages.
    serviceHost.Open();
  
    // The service can now be accessed.
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.WriteLine();
    Console.ReadLine();
  
    // Close the ServiceHostB to shut down the service.
    serviceHost.Close();
}  
```  
  
## <a name="see-also"></a>Vea también

- [Información general de colas](queues-overview.md)
- [Las colas en WCF](queuing-in-wcf.md)
