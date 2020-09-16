---
title: Message Queuing a Windows Communication Foundation
ms.date: 03/30/2017
ms.assetid: 6d718eb0-9f61-4653-8a75-d2dac8fb3520
ms.openlocfilehash: 5132e0380aebd595e79429fab9df8a7fb94574a0
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90558698"
---
# <a name="message-queuing-to-windows-communication-foundation"></a>Message Queuing a Windows Communication Foundation

Este ejemplo muestra cómo una aplicación de Message Queuing (MSMQ) puede enviar un mensaje de MSMQ a un servicio de Windows Communication Foundation (WCF). El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.

 El contrato de servicio es `IOrderProcessor`, que define un servicio unidireccional que es adecuado para usarse con colas. Un mensaje de MSMQ no tiene un encabezado Acción, por lo que no es posible asignar automáticamente distintos mensajes de MSMQ a los contratos de operación. Además, solo puede haber un contrato de operación. Si desea definir más de un contrato de operación para el servicio, la aplicación debe proporcionar información como qué encabezado en el mensaje de MSMQ (por ejemplo, la etiqueta o correlationID) se puede utilizar para decidir qué contrato de operación distribuir.

 El mensaje de MSMQ no contiene información sobre qué encabezados están asignados a los distintos parámetros del contrato de operación. El parámetro es de tipo <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`), que contiene el mensaje de MSMQ subyacente. El tipo "T" en la clase <xref:System.ServiceModel.MsmqIntegration.MsmqMessage%601>(`MsmqMessage<T>`) representa los datos que se serializan en el cuerpo del mensaje de MSMQ. En este ejemplo, el tipo `PurchaseOrder` se serializa en el cuerpo del mensaje de MSMQ.

 El código de ejemplo siguiente muestra el contrato de servicio del servicio de procesamiento de órdenes.

```csharp
// Define a service contract.
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples")]
[ServiceKnownType(typeof(PurchaseOrder))]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true, Action = "*")]
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);
}
```

 El servicio se hospeda en sí mismo. Al utilizar MSMQ, la cola usada debe crearse de antemano. Esto se puede hacer manualmente o a través de código. En este ejemplo, el servicio comprueba la existencia de la cola y la crea si es necesario. El nombre de la cola se lee del archivo de configuración.

```csharp
public static void Main()
{
    // Get the MSMQ queue name from the application settings in
    // configuration.
    string queueName = ConfigurationManager.AppSettings["queueName"];
    // Create the MSMQ queue if necessary.
    if (!MessageQueue.Exists(queueName))
        MessageQueue.Create(queueName, true);
    …
}
```

 El servicio crea y abre un <xref:System.ServiceModel.ServiceHost> para `OrderProcessorService`, tal y como se muestra en el código de ejemplo siguiente.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))
{
    serviceHost.Open();
    Console.WriteLine("The service is ready.");
    Console.WriteLine("Press <ENTER> to terminate service.");
    Console.ReadLine();
    serviceHost.Close();
}
```

 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.

> [!NOTE]
> El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso. La dirección del extremo de WCF especifica un esquema MSMQ. FormatName y utiliza localhost para el equipo local. La dirección de la cola para las directrices de direccionamiento del nombre de formato de MSMQ sigue el esquema msmq.formatname.

```xml
<appSettings>
    <add key="orderQueueName" value=".\private$\Orders" />
</appSettings>
```

 La aplicación cliente es una aplicación MSMQ que utiliza el método <xref:System.Messaging.MessageQueue.Send%2A> para enviar un mensaje duradero y un mensaje transaccional a la cola, tal y como se muestra en el código de ejemplo siguiente.

```csharp
//Connect to the queue.
MessageQueue orderQueue = new MessageQueue(ConfigurationManager.AppSettings["orderQueueName"]);

// Create the purchase order.
PurchaseOrder po = new PurchaseOrder();
po.CustomerId = "somecustomer.com";
po.PONumber = Guid.NewGuid().ToString();

PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();
lineItem1.ProductId = "Blue Widget";
lineItem1.Quantity = 54;
lineItem1.UnitCost = 29.99F;

PurchaseOrderLineItem lineItem2 = new PurchaseOrderLineItem();
lineItem2.ProductId = "Red Widget";
lineItem2.Quantity = 890;
lineItem2.UnitCost = 45.89F;

po.orderLineItems = new PurchaseOrderLineItem[2];
po.orderLineItems[0] = lineItem1;
po.orderLineItems[1] = lineItem2;

// Submit the purchase order.
Message msg = new Message();
msg.Body = po;
//Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{

    orderQueue.Send(msg, MessageQueueTransactionType.Automatic);
    // Complete the transaction.
    scope.Complete();

}
Console.WriteLine("Placed the order:{0}", po);
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente. Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Por ejemplo, podría ejecutar el cliente, cerrarlo e iniciar el servicio y seguiría recibiendo sus mensajes.

## <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.

    1. Abra Administrador del servidor en Visual Studio 2012.

    2. Expanda la pestaña **características** .

    3. Haga clic con el botón secundario en **colas de mensajes privadas**y seleccione **nuevo**, **cola privada**.

    4. Active la casilla **transaccional** .

    5. Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

## <a name="run-the-sample-across-computers"></a>Ejecutar el ejemplo en todos los equipos

1. Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.

2. Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.

3. En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".

4. En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.

5. En el equipo cliente, inicie Client.exe desde un símbolo del sistema.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\MsmqToWcf`

## <a name="see-also"></a>Vea también

- [Colas en WCF](../feature-details/queues-in-wcf.md)
- [Procedimiento para intercambiar mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](../feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)
- [Message Queue Server](/previous-versions/windows/desktop/legacy/ms711472(v=vs.85))
