---
title: Windows Communication Foundation a Message Queuing
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 78d0d0c9-648e-4d4a-8f0a-14d9cafeead9
caps.latest.revision: 32
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2ea59c7f1ef2ac6f22500a13eb9bb4456149b7c
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="windows-communication-foundation-to-message-queuing"></a>Windows Communication Foundation a Message Queuing
Este ejemplo muestra cómo una aplicación [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] puede enviar un mensaje a una aplicación de Message Queuing (MSMQ). El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola. El servicio y el cliente no tienen que estar ejecutándose al mismo tiempo.  
  
 El servicio recibe los mensajes de la cola y procesa las órdenes. El servicio crea una cola transaccional y establece un mensaje recibido por el controlador de mensajes, tal y como se muestra en el código de ejemplo siguiente.  

```csharp
static void Main(string[] args)  
{  
    if (!MessageQueue.Exists(  
              ConfigurationManager.AppSettings["queueName"]))  
       MessageQueue.Create(  
           ConfigurationManager.AppSettings["queueName"], true);  
        //Connect to the queue  
        MessageQueue Queue = new   
    MessageQueue(ConfigurationManager.AppSettings["queueName"]);  
    Queue.ReceiveCompleted +=   
                 new ReceiveCompletedEventHandler(ProcessOrder);  
    Queue.BeginReceive();  
    Console.WriteLine("Order Service is running");  
    Console.ReadLine();  
}  
```

 Cuando se recibe un mensaje en la cola, se invoca a `ProcessOrder` del controlador de mensajes.  

```csharp
public static void ProcessOrder(Object source,  
    ReceiveCompletedEventArgs asyncResult)  
{  
    try  
    {  
        // Connect to the queue.  
        MessageQueue Queue = (MessageQueue)source;  
        // End the asynchronous receive operation.  
        System.Messaging.Message msg =   
                     Queue.EndReceive(asyncResult.AsyncResult);  
        msg.Formatter = new System.Messaging.XmlMessageFormatter(  
                                new Type[] { typeof(PurchaseOrder) });  
        PurchaseOrder po = (PurchaseOrder) msg.Body;  
        Random statusIndexer = new Random();  
        po.Status = PurchaseOrder.OrderStates[statusIndexer.Next(3)];  
        Console.WriteLine("Processing {0} ", po);  
        Queue.BeginReceive();  
    }  
    catch (System.Exception ex)  
    {  
        Console.WriteLine(ex.Message);  
    }  
  
}  
```

 El servicio extrae `ProcessOrder` desde el cuerpo del mensaje de MSMQ y procesa la orden.  
  
 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.  
  
```xml  
<appSettings>  
    <add key="orderQueueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso.  
  
 El cliente crea una orden de compra y la envía dentro del ámbito de una transacción, tal y como se muestra en el código de ejemplo siguiente.  

```csharp
// Create the purchase order  
PurchaseOrder po = new PurchaseOrder();  
// Fill in the details  
...  
  
OrderProcessorClient client = new OrderProcessorClient("OrderResponseEndpoint");  
  
MsmqMessage<PurchaseOrder> ordermsg = new MsmqMessage<PurchaseOrder>(po);  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    client.SubmitPurchaseOrder(ordermsg);  
    scope.Complete();  
}  
Console.WriteLine("Order has been submitted:{0}", po);  
  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```

 El cliente utiliza un cliente personalizado en orden para enviar el mensaje de MSMQ a la cola. Dado que la aplicación que recibe y procesa el mensaje es una aplicación MSMQ y no una aplicación [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], no hay ningún contrato de servicios implícito entre las dos aplicaciones. Así que no podemos crear ningún proxy utilizando la herramienta Svcutil.exe en este escenario.  
  
 El cliente personalizado es esencialmente el mismo para todas las aplicaciones [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] que utilizan el enlace `MsmqIntegration` para enviar mensajes. A diferencia de otros clientes, no incluye ningún intervalo de operaciones de servicio. Solo es una operación de envío de mensaje.  

```csharp
[System.ServiceModel.ServiceContractAttribute(Namespace = "http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Action = "*")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
}  
  
public partial class OrderProcessorClient : System.ServiceModel.ClientBase<IOrderProcessor>, IOrderProcessor  
{  
    public OrderProcessorClient(){}  
  
    public OrderProcessorClient(string configurationName)  
        : base(configurationName)  
    { }  
  
    public OrderProcessorClient(System.ServiceModel.Channels.Binding binding, System.ServiceModel.EndpointAddress address)  
        : base(binding, address)  
    { }  
  
    public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
    {  
        base.Channel.SubmitPurchaseOrder(msg);  
    }  
}  
```

 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente. Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Por ejemplo, podría ejecutar el cliente, cerrarlo e iniciar el servicio y seguiría recibiendo sus mensajes.  
  
> [!NOTE]
>  Este ejemplo requiere la instalación de Message Queuing (MSMQ). Consulte las instrucciones de instalación de [Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=94968).  
  
### <a name="to-setup-build-and-run-the-sample"></a>Para configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.  
  
    1.  Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Expanda el **características** ficha.  
  
    3.  Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.  
  
    4.  Compruebe el **transaccional** cuadro.  
  
    5.  Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.  
  
3.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipo único, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1.  Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.  
  
2.  Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
3.  En el archivo Client.exe.config, cambie la dirección del extremo del cliente para especificar el nombre del equipo servidor en lugar de ".".  
  
4.  En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.  
  
5.  En el equipo cliente, inicie Client.exe desde un símbolo del sistema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\WcfToMsmq`  
  
## <a name="see-also"></a>Vea también  
 [Intercambio de mensajes con puntos de conexión de WCF y aplicaciones de Message Queue Server](../../../../docs/framework/wcf/feature-details/how-to-exchange-messages-with-wcf-endpoints-and-message-queuing-applications.md)  
 [Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=94968)
