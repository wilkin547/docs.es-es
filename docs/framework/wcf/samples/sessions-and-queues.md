---
description: 'Más información acerca de: sesiones y colas'
title: Sesiones y colas
ms.date: 03/30/2017
ms.assetid: 47d7c5c2-1e6f-4619-8003-a0ff67dcfbd6
ms.openlocfilehash: 94ff58fca628e44b78b002291fa78a39cc10a14f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793017"
---
# <a name="sessions-and-queues"></a>Sesiones y colas

Este ejemplo muestra cómo enviar y recibir un conjunto de mensajes relacionados en comunicación en cola sobre el transporte de Message Queuing (MSMQ). El ejemplo usa el enlace `netMsmqBinding`. El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Session`  
  
 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.  
  
 A veces, un cliente envía un conjunto de mensajes relacionado con cada uno en un grupo. Cuando los mensajes deben procesarse juntos o en un orden especificado, se puede utilizar una cola para agruparlos, para que los procesen una aplicación receptora única. Esto es particularmente importante cuando hay varias aplicaciones receptoras en un grupo de servidores y es necesario garantizar que la misma aplicación receptora procesa un grupo de mensajes. Las sesiones en cola son un mecanismo utilizado para enviar y recibir un conjunto relacionado de mensajes que se deben procesar de repente. Las sesiones en cola necesitan que una transacción exhiba este patrón.  
  
 En el ejemplo, el cliente envía varios mensajes al servicio como parte de una sesión dentro del ámbito de una transacción única.  
  
 El contrato de servicio es `IOrderTaker`, que define un servicio unidireccional que es adecuado para usarse con colas. <xref:System.ServiceModel.SessionMode> utilizado en el contrato mostrado en el código de ejemplo siguiente indica que los mensajes forman parte de la sesión.  

```csharp
[ServiceContract(Namespace = "http://Microsoft.ServiceModel.Samples", SessionMode=SessionMode.Required)]  
public interface IOrderTaker  
{  
    [OperationContract(IsOneWay = true)]  
    void OpenPurchaseOrder(string customerId);  
  
    [OperationContract(IsOneWay = true)]  
    void AddProductLineItem(string productId, int quantity);  
  
    [OperationContract(IsOneWay = true)]  
    void EndPurchaseOrder();  
}  
```

 El servicio define las operaciones de servicio de tal manera que la primera operación da de alta en una transacción pero no la completa. Las operaciones subsiguientes también dan de alta en la misma transacción pero no se completan automáticamente. La última operación en la sesión completa automáticamente la transacción. Así, se utiliza la misma transacción para varias invocaciones de la operación en el contrato de servicios. Si cualquiera de las operaciones produce una excepción, a continuación, la transacción se revierte y la sesión se pone de nuevo en la cola. En la realización correcta de la última operación, la transacción se confirma. El servicio utiliza `PerSession` como <xref:System.ServiceModel.InstanceContextMode> para recibir todos los mensajes en una sesión en la misma instancia del servicio.  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
public class OrderTakerService : IOrderTaker  
{  
    PurchaseOrder po;  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                 TransactionAutoComplete = false)]  
    public void OpenPurchaseOrder(string customerId)  
    {  
        Console.WriteLine("Creating purchase order");  
        po = new PurchaseOrder(customerId);  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = false)]  
    public void AddProductLineItem(string productId, int quantity)  
    {  
        po.AddProductLineItem(productId, quantity);  
        Console.WriteLine("Product " + productId + " quantity " +
                            quantity + " added to purchase order");  
    }  
  
    [OperationBehavior(TransactionScopeRequired = true,
                                  TransactionAutoComplete = true)]  
    public void EndPurchaseOrder()  
    {  
       Console.WriteLine("Purchase Order Completed");  
       Console.WriteLine();  
       Console.WriteLine(po.ToString());  
    }  
}  
```

 El servicio se hospeda en sí mismo. Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano. Esto se puede hacer manualmente o a través de código. En este ejemplo, el servicio contiene el código <xref:System.Messaging> para comprobar la existencia de la cola y la crea, si fuera necesario. El nombre de la cola se lee del archivo de configuración utilizando la clase <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.  

```csharp
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Get MSMQ queue name from app settings in configuration.  
    string queueName = ConfigurationManager.AppSettings["queueName"];  
  
    // Create the transacted MSMQ queue if necessary.  
    if (!MessageQueue.Exists(queueName))  
        MessageQueue.Create(queueName, true);  
  
    // Create a ServiceHost for the OrderTakerService type.  
    using (ServiceHost serviceHost = new ServiceHost(typeof(OrderTakerService)))  
    {  
        // Open the ServiceHost to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHost to shutdown the service.  
        serviceHost.Close();
    }  
}  
```

 El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración. El extremo para el servicio se define en la sección system.ServiceModel del archivo de configuración y especifica el enlace `netMsmqBinding`.  
  
```xml  
<appSettings>  
  <!-- Use appSetting to configure MSMQ queue name. -->  
  <add key="queueName" value=".\private$\ServiceModelSamplesSession" />  
</appSettings>  
  
<system.serviceModel>  
  <services>  
    <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      ...  
      <!-- Define NetMsmqEndpoint -->  
      <endpoint address="net.msmq://localhost/private/ServiceModelSamplesSession"  
                binding="netMsmqBinding"  
                contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
      ...  
    </service>  
  </services>  
  ...  
</system.serviceModel>  
```  
  
 El cliente crea un ámbito de transacción. Se envían todos los mensajes en la sesión a la cola dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde todos los mensajes son correctos o se producen errores. La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A>.  

```csharp
//Create a transaction scope.  
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))  
{  
    // Create a client with given client endpoint configuration.  
    OrderTakerClient client = new OrderTakerClient("OrderTakerEndpoint");  
    // Open a purchase order.  
    client.OpenPurchaseOrder("somecustomer.com");  
    Console.WriteLine("Purchase Order created");  
  
    // Add product line items.  
    Console.WriteLine("Adding 10 quantities of blue widget");  
    client.AddProductLineItem("Blue Widget", 10);  
  
    Console.WriteLine("Adding 23 quantities of red widget");  
    client.AddProductLineItem("Red Widget", 23);  
  
    // Close the purchase order.  
    Console.WriteLine("Closing the purchase order");  
    client.EndPurchaseOrder();  
  
    //Closing the client gracefully closes the connection and cleans up resources.  
    client.Close();
  
    // Complete the transaction.  
    scope.Complete();  
}  
```

> [!NOTE]
> Puede utilizar solo una transacción única para todos los mensajes en la sesión y deben enviarse todos los mensajes en la sesión antes de confirmar la transacción. Al cerrar el cliente, se cierra la sesión. Por consiguiente, el cliente tiene que estar cerrado antes de que la transacción se complete para enviar todos los mensajes de la sesión a la cola.  
  
 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente. Debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.  
  
 En el cliente.  
  
```console  
Purchase Order created  
Adding 10 quantities of blue widget  
Adding 23 quantities of red widget  
Closing the purchase order  
  
Press <ENTER> to terminate client.  
```  
  
 En el servicio.  
  
```console  
The service is ready.  
Press <ENTER> to terminate service.  
  
Creating purchase order  
Product Blue Widget quantity 10 added to purchase order  
Product Red Widget quantity 23 added to purchase order  
Purchase Order Completed  
  
Purchase Order: 7c86fef0-2306-4c51-80e6-bcabcc1a6e5e  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 10 of Blue Widget @unit price: $2985  
                Order LineItem: 23 of Red Widget @unit price: $156  
        Total cost of this order: $33438  
        Order status: Pending  
```  
  
### <a name="set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar la edición de C#, C++ o Visual Basic .NET de la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
 De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada. Hay dos propiedades pertinentes para la seguridad de transporte de MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign` . Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ. Si ejecuta este ejemplo en un equipo que no satisface estos criterios, recibirá un error.  
  
### <a name="run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Ejecutar el ejemplo en un equipo unido a un grupo de trabajo  
  
1. Si su equipo no es parte de un dominio o no tiene instalada la integración del directorio activo, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente.  
  
    ```xml  
    <system.serviceModel>  
      <services>  
        <service name="Microsoft.ServiceModel.Samples.OrderTakerService"  
                 behaviorConfiguration="OrderTakerServiceBehavior">  
          <host>  
            <baseAddresses>  
              <add baseAddress=  
             "http://localhost:8000/ServiceModelSamples/service"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint  
              address=  
            "net.msmq://localhost/private/ServiceModelSamplesSession"  
              binding="netMsmqBinding"  
              bindingConfiguration="Binding1"  
           contract="Microsoft.ServiceModel.Samples.IOrderTaker" />  
          <!-- The mex endpoint is exposed at-->
          <!--http://localhost:8000/ServiceModelSamples/service/mex. -->  
          <endpoint address="mex"  
                    binding="mexHttpBinding"  
                    contract="IMetadataExchange" />  
        </service>  
      </services>  
  
      <bindings>  
        <netMsmqBinding>  
          <binding name="Binding1">  
            <security mode="None" />  
          </binding>  
        </netMsmqBinding>  
      </bindings>  
  
        <behaviors>  
          <serviceBehaviors>  
            <behavior name="OrderTakerServiceBehavior">  
              <serviceMetadata httpGetEnabled="True"/>  
            </behavior>  
          </serviceBehaviors>  
        </behaviors>  
  
      </system.serviceModel>  
    ```  
  
2. Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.  
  
    > [!NOTE]
    > Establecer el modo de seguridad en `None` es equivalente a establecer la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.  
