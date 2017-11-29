---
title: "Comunicación bidireccional"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fb64192d-b3ea-4e02-9fb3-46a508d26c60
caps.latest.revision: "24"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: b9d55087eb46cc304fa2a42a3e64208d9a4fec5d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="two-way-communication"></a>Comunicación bidireccional
Este ejemplo muestra cómo llevar a cabo la comunicación en cola bidireccional sobre MSMQ. El ejemplo usa el enlace `netMsmqBinding`. En este caso, el servicio es una aplicación de consola hospedada en sí misma que permite observar el servicio que recibe los mensajes en cola.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En este ejemplo se basa en el [transacciones enlace MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. El cliente envía los mensajes a una cola y el servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.  
  
 Este ejemplo muestra la comunicación bidireccional mediante las colas. El cliente envía los pedidos de compra a la cola desde dentro del ámbito de una transacción. El servicio recibe las órdenes, procesa la orden y, a continuación, llama de nuevo al cliente con el estado de la orden desde la cola dentro del ámbito de una transacción. Para facilitar la comunicación bidireccional, tanto el cliente como el servicio utilizan las colas para poner en cola los pedidos de compra y el estado de la orden.  
  
 El contrato de servicios `IOrderProcessor` define operaciones de servicio unidireccionales que satisfacen el uso de poner en cola. La operación del servicio incluye el extremo de la respuesta para utilizarlo para enviar los estados del orden. El extremo de la respuesta es el URI de la cola para devolver el estado de la orden al cliente. La aplicación de procesamiento de orden implementa este contrato.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po, string   
                                  reportOrderStatusTo);  
}  
```  
  
 El cliente especifica el contrato de la respuesta para enviar el estado de la orden. El cliente implementa el contrato del estado de la orden. El servicio utiliza el proxy generado de este contrato para devolver el estado de la orden al cliente.  
  
```  
[ServiceContract]  
public interface IOrderStatus  
{  
    [OperationContract(IsOneWay = true)]  
    void OrderStatus(string poNumber, string status);  
}  
```  
  
 La operación del servicio procesa el pedido de compra enviado. <xref:System.ServiceModel.OperationBehaviorAttribute> se aplica a la operación del servicio para especificar la inscripción automática en una transacción que se utiliza para recibir el mensaje de la cola y la realización automática de transacciones en la realización de la operación del servicio. La clase `Orders` encapsula la funcionalidad del procesamiento de la orden. En este caso, agrega el pedido de compra a un diccionario. La transacción en la que la operación del servicio se dio de alta está disponible para las operaciones en la clase `Orders`.  
  
 La operación del servicio, además de procesar el pedido de compra enviado, responde de nuevo al cliente en el estado de la orden.  
  
```  
[OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)  
{  
    Orders.Add(po);  
    Console.WriteLine("Processing {0} ", po);  
    Console.WriteLine("Sending back order status information");  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding("ClientCallbackBinding");  
    OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));  
  
    // Please note that the same transaction that is used to dequeue the purchase order is used  
    // to send back order status.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        client.OrderStatus(po.PONumber, po.Status);  
        scope.Complete();  
    }  
    //Close the client.  
    client.Close();  
}  
```  
  
 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración. Los extremos para el servicio se definen en la sección de System.ServiceModel del archivo de configuración.  
  
> [!NOTE]
>  El nombre de cola de MSMQ y la dirección de extremo utilizan convenciones de direccionamiento ligeramente diferentes. El nombre de la cola MSMQ utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso. La dirección de extremo [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] especifica net.msmq: el esquema utiliza el "host local" para el equipo local y utiliza barras diagonales en su ruta de acceso. Para leer de una cola que se hospeda en el equipo remoto, reemplace el "." y el “host local” por el nombre del equipo remoto.  
  
 El servicio se hospeda en sí mismo. Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano. Esto se puede hacer manualmente o a través de código. En este ejemplo, el servicio comprueba la existencia de la cola y la crea si es necesario. El nombre de la cola se lee del archivo de configuración. La dirección base es utilizada por la [la herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para generar el proxy para el servicio.  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from appSettings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderProcessorService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 El cliente crea un ámbito de transacción. La comunicación con la cola tiene lugar dentro del ámbito de la transacción, produciendo que se tratae como una unidad atómica donde todos los mensajes tienen éxito o no dan error.  
  
```  
// Create a ServiceHost for the OrderStatus service type.  
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))  
{  
  
    // Open the ServiceHostBase to create listeners and start listening for order status messages.  
    serviceHost.Open();  
  
    // Create the purchase order.  
    ...  
  
    // Create a client with given client endpoint configuration.  
    OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
    //Create a transaction scope.  
    using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
    {  
        string hostName = Dns.GetHostName();  
  
        // Make a queued call to submit the purchase order.  
        client.SubmitPurchaseOrder(po, "net.msmq://" + hostName + "/private/ServiceModelSamplesTwo-way/OrderStatus");  
  
        // Complete the transaction.  
        scope.Complete();  
    }  
  
    //Close down the client.  
    client.Close();  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
  
    // Close the ServiceHost to shutdown the service.  
    serviceHost.Close();  
}  
```  
  
 El código de cliente implementa el contrato`IOrderStatus` para recibir el estado de la orden del servicio. En este caso, imprime el estado de la orden.  
  
```  
[ServiceBehavior]  
public class OrderStatusService : IOrderStatus  
{  
    [OperationBehavior(TransactionAutoComplete = true,   
                        TransactionScopeRequired = true)]  
    public void OrderStatus(string poNumber, string status)  
    {  
        Console.WriteLine("Status of order {0}:{1} ", poNumber ,   
                                                           status);  
    }  
}  
```  
  
 La cola de estado de la orden se crea en el método `Main`. La configuración del cliente incluye la configuración del servicio del estado de la orden para hospedar el servicio del estado de la orden, tal y como se muestra en la configuración del ejemplo siguiente.  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
</appSettings>  
  
<system.serviceModel>  
  
  <services>  
    <service   
       name="Microsoft.ServiceModel.Samples.OrderStatusService">  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
    </service>  
  </services>  
  
  <client>  
    <!-- Define NetMsmqEndpoint -->  
    <endpoint name="OrderProcessorEndpoint"  
              address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
              binding="netMsmqBinding"   
              contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
  </client>  
  
</system.serviceModel>  
```  
  
 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.  
  
 El servicio muestra la información del pedido de compra e indica que se está devolviendo el estado de la orden a la cola de estado de la orden.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 124a1f69-3699-4b16-9bcc-43147a8756fc  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Sending back order status information  
```  
  
 El cliente muestra la información del estado de la orden enviada por el servicio.  
  
```  
Press <ENTER> to terminate client.  
Status of order 124a1f69-3699-4b16-9bcc-43147a8756fc:Pending  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
    > [!NOTE]
    >  Si utiliza Svcutil.exe para recompilar la configuración de este ejemplo, asegúrese de que modifica los nombres del punto de conexión en la configuración del cliente para que coincida con el código de cliente.  
  
 De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada. Hay dos propiedades relevantes para la seguridad de transporte MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` de forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign`. Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ. Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory  
  
1.  Si su equipo no es parte de un dominio o no tiene la integración del directorio activo instalada, desactive la seguridad de transporte, estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:  
  
    ```xml  
    <configuration>  
  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderProcessor" />  
      </appSettings>  
  
      <system.serviceModel>  
        <services>  
          <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding"   
                      contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
          </service>  
        </services>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
2.  Al desactivar la seguridad para una configuración del cliente, se genera lo siguiente:  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <appSettings>  
        <!-- Use appSetting to configure MSMQ queue name. -->  
        <add key="queueName" value=".\private$\ServiceModelSamplesTwo-way/OrderStatus" />  
      </appSettings>  
  
      <system.serviceModel>  
  
        <services>  
          <service   
             name="Microsoft.ServiceModel.Samples.OrderStatusService">  
            <!-- Define NetMsmqEndpoint -->  
            <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderStatus"  
                      binding="netMsmqBinding"  
                      bindingConfiguration="TransactedBinding" contract="Microsoft.ServiceModel.Samples.IOrderStatus" />  
          </service>  
        </services>  
  
        <client>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint name="OrderProcessorEndpoint"  
                    address="net.msmq://localhost/private/ServiceModelSamplesTwo-way/OrderProcessor"   
                    binding="netMsmqBinding"   
                    bindingConfiguration="TransactedBinding"  
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
        </client>  
  
        <bindings>  
          <netMsmqBinding>  
            <binding name="TransactedBinding" >  
             <security mode="None" />  
            </binding>  
          </netMsmqBinding>  
        </bindings>  
  
      </system.serviceModel>  
  
    </configuration>  
    ```  
  
3.  El servicio para este ejemplo crea un enlace en `OrderProcessorService`. Agregue una línea de código una vez se haya creado instancias para el enlace para establecer el modo de seguridad en `None`.  
  
    ```  
    NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();  
    msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;  
    ```  
  
4.  Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.  
  
    > [!NOTE]
    >  Establecer `security mode` en `None` es equivalente a definir la seguridad de la propiedad <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> o `Message` en `None`.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Binding\Net\MSMQ\Two-Way`  
  
## <a name="see-also"></a>Vea también
