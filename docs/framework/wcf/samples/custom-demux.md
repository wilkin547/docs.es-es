---
title: Demux personalizado
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc54065c-518e-4146-b24a-0fe00038bfa7
caps.latest.revision: 41
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 45184c2d884347baef4090ed496e22e77aab5423
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="custom-demux"></a>Demux personalizado
Este ejemplo muestra cómo se pueden asignar los encabezados del mensaje MSMQ para diferentes operaciones de servicio para que [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] servicios que utilizan <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding> no están limitados a utilizar una operación de servicio como se muestra en el [Message Queue Server Windows Communication Foundation](../../../../docs/framework/wcf/samples/message-queuing-to-wcf.md) y [Windows Communication Foundation a Message Queue Server](../../../../docs/framework/wcf/samples/wcf-to-message-queuing.md) ejemplos.  
  
 El servicio de este ejemplo es una aplicación de consola autohospedada que permite observar el servicio que recibe los mensajes en cola.  
  
 El contrato de servicio es `IOrderProcessor`, y define un servicio unidireccional que es adecuado para usarse con colas.  

```csharp
[ServiceContract]  
[KnownType(typeof(PurchaseOrder))]  
[KnownType(typeof(String))]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true, Name = "SubmitPurchaseOrder")]  
    void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg);  
  
    [OperationContract(IsOneWay = true, Name = "CancelPurchaseOrder")]  
    void CancelPurchaseOrder(MsmqMessage<string> ponumber);  
}  
```

 Un mensaje de MSMQ no tiene un encabezado Acción. No es posible asignar automáticamente los mensajes de MSMQ diferentes a los contratos de operación. Además, solo puede haber un contrato de operación. Para superar esta limitación, el servicio implementa el método <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> de la interfaz <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector>. El método <xref:System.ServiceModel.Dispatcher.IDispatchOperationSelector.SelectOperation%2A> permite al servicio asignar un encabezado determinado del mensaje a una operación del servicio determinada. En este ejemplo, el encabezado de etiqueta del mensaje está asignado a las operaciones del servicio. El parámetro `Name` del contrato de operación determina qué operación del servicio se debe enviar para una etiqueta del mensaje determinada. Por ejemplo, si el encabezado de etiqueta del mensaje contiene "SubmitPurchaseOrder", se invoca la operación de servicio de "SubmitPurchaseOrder."  

```csharp
public class OperationSelector : IDispatchOperationSelector  
{  
    public string SelectOperation(ref System.ServiceModel.Channels.Message message)  
    {  
        MsmqIntegrationMessageProperty property = MsmqIntegrationMessageProperty.Get(message);  
        return property.Label;  
    }  
}  
```

 El servicio debe implementar el método <xref:System.ServiceModel.Description.IContractBehavior.ApplyDispatchBehavior%28System.ServiceModel.Description.ContractDescription%2CSystem.ServiceModel.Description.ServiceEndpoint%2CSystem.ServiceModel.Dispatcher.DispatchRuntime%29> de la interfaz <xref:System.ServiceModel.Description.IContractBehavior> como se muestra en el código muestra siguiente. Esto aplica el `OperationSelector` personalizado a la expedición del marco de trabajo del servicio en tiempo de ejecución.  

```csharp
void IContractBehavior.ApplyDispatchBehavior(ContractDescription description, ServiceEndpoint endpoint, DispatchRuntime dispatch)  
{  
    dispatch.OperationSelector = new OperationSelector();  
}  
```

 Un mensaje debe atravesar <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> del distribuidor antes de llegar al OperationSelector. De forma predeterminada se rechaza un mensaje si su acción no se puede buscar en cualquier contrato implementado por el servicio. Para evitar esta comprobación, implementamos un <xref:System.ServiceModel.Description.IEndpointBehavior> denominado `MatchAllFilterBehavior`, que permite a cualquier mensaje atravesar `ContractFilter` aplicando el <xref:System.ServiceModel.Dispatcher.MatchAllMessageFilter> como sigue.  

```csharp
public void ApplyDispatchBehavior(ServiceEndpoint serviceEndpoint, EndpointDispatcher endpointDispatcher)  
{  
    endpointDispatcher.ContractFilter = new MatchAllMessageFilter();  
}  
```
  
 Cuando el servicio recibe un mensaje, la operación del servicio adecuada se envía utilizando la información proporcionada por el encabezado de etiqueta. El cuerpo del mensaje se deserializa en un objeto `PurchaseOrder`, como se muestra en el código muestra siguiente.  

```csharp
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(MsmqMessage<PurchaseOrder> msg)  
{  
    PurchaseOrder po = (PurchaseOrder)msg.Body;  
    Random statusIndexer = new Random();  
    po.Status = (OrderStates)statusIndexer.Next(3);  
    Console.WriteLine("Processing {0} ", po);  
}  
```

 El servicio es autohospedado. Al utilizar el MSMQ, se debe crear la cola que se utiliza de antemano. Esto se puede hacer manualmente o a través de código. En este ejemplo, el servicio contiene el código para comprobar la existencia de la cola y crearla si no existe. El nombre de la cola se lee del archivo de configuración.  

```csharp
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration  
    string queueName = ConfigurationManager.AppSettings["orderQueueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {                 
        ServiceEndpoint endpoint = serviceHost.Description.Endpoints[0];  
        endpoint.Behaviors.Add(new MatchAllFilterBehavior());  
  
        //Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();  
    }  
}  
```

 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración.  
  
> [!NOTE]
>  El nombre de la cola utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso. La dirección de extremo de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] especifica un esquema msmq.formatname y utiliza localhost para el equipo local. Lo que sigue al esquema es una dirección de cola con el formato apropiado según las instrucciones de direccionamiento del nombre de formato de MSMQ.  
  
```xml  
<appSettings>  
    <!-- Use appSetting to configure the MSMQ queue name. -->  
    <add key="queueName" value=".\private$\Orders" />  
</appSettings>  
```  
  
> [!NOTE]
>  Este ejemplo requiere la instalación de [Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=95143).  
  
 Inicie el servicio y ejecute el cliente.  
  
 El siguiente resultado se ve en el cliente.  
  
```  
Placed the order:Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
Canceled the Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
Press <ENTER> to terminate client.  
```  
  
 El resultado siguiente se debe ver en el servicio.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
Processing Purchase Order: 28fc457a-1a56-4fe0-9dde-156965c21ed6  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Shipped  
Purchase Order 28fc457a-1a56-4fe0-9dde-156965c21ed6 is canceled  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.  
  
    1.  Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Expanda el **características** ficha.  
  
    3.  Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.  
  
    4.  Compruebe el **transaccional** cuadro.  
  
    5.  Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.  
  
3.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-across-computers"></a>Para ejecutar el ejemplo en varios equipos  
  
1.  Copie los archivos de programa del servicio de la carpeta \service\bin\, bajo la carpeta específica del lenguaje, al equipo del servicio.  
  
2.  Copie los archivos de programa del cliente de la carpeta \client\bin\, bajo la carpeta específica del lenguaje, al equipo cliente.  
  
3.  En el archivo Client.exe.config, cambie orderQueueName para especificar el nombre de equipo del servicio en lugar de ".".  
  
4.  En el equipo del servicio, inicie Service.exe desde un símbolo del sistema.  
  
5.  En el equipo cliente, inicie Client.exe desde un símbolo del sistema.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\MSMQIntegration\CustomDemux`  
  
## <a name="see-also"></a>Vea también  
 [Colas en WCF](../../../../docs/framework/wcf/feature-details/queuing-in-wcf.md)  
 [Message Queue Server](http://go.microsoft.com/fwlink/?LinkId=95143)
