---
title: Colas con problemas de entrega
ms.date: 03/30/2017
ms.assetid: ff664f33-ad02-422c-9041-bab6d993f9cc
ms.openlocfilehash: cf281ff08d56669d0257d693af93d8a9b5b2e81a
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292833"
---
# <a name="dead-letter-queues"></a>Colas con problemas de entrega

Este ejemplo muestra cómo administrar y procesar mensajes que han producido errores en la entrega. Se basa en el ejemplo de [enlace de MSMQ de transacciones](transacted-msmq-binding.md) . El ejemplo usa el enlace `netMsmqBinding`. El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!NOTE]
> Este ejemplo muestra cada cola de mensajes con problemas de entrega de la aplicación que solo está disponible en Windows Vista. El ejemplo se puede modificar para usar las colas predeterminadas de todo el sistema para MSMQ 3,0 en Windows Server 2003 y Windows XP.

 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.

 Dado que la comunicación en cola puede implicar una cierta cantidad de inactividad, quizá prefiera asociar un valor de período de vida en el mensaje para asegurarse de que el mensaje no se entrega a la aplicación si se ha pasado de hora. Hay también casos, donde si la entrega del mensaje ha fallado se debe notificar a la aplicación. En todos estos casos, como cuando el período de vida del mensaje ha expirado o la entrega del mensaje ha fallado, el mensaje se coloca en una cola de mensajes no enviados. La aplicación emisora puede leer en la cola mensajes no entregados y emprender acciones de corrección que van desde no realizar ninguna acción hasta corregir las razones del error de la entrega y reenviar el mensaje.

 La cola de mensajes no enviados en el enlace `NetMsmqBinding` se expresa en las propiedades siguientes:

- La propiedad <xref:System.ServiceModel.MsmqBindingBase.DeadLetterQueue%2A> expresa el tipo de cola de mensajes no enviados requerido por el cliente. Esta enumeración tiene los valores siguientes:

- `None`: el cliente no requiere la cola de mensajes no enviados.

- `System`: La cola de mensajes no enviados del sistema se utiliza para guardar los mensajes no entregados. Todas las aplicaciones que se ejecutan en el equipo comparten la cola de mensajes no enviados del sistema.

- `Custom`: una cola de mensajes no enviados personalizada especificada con la propiedad <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> se utiliza para almacenar los mensajes no entregados. Esta característica solo está disponible en Windows Vista. Se utiliza cuando la aplicación debe utilizar su propia cola de mensajes no enviados en lugar de compartirla con otras aplicaciones que se ejecutan en el mismo equipo.

- La propiedad <xref:System.ServiceModel.MsmqBindingBase.CustomDeadLetterQueue%2A> expresa la cola concreta que se debe utilizar como cola de mensajes no enviados. Solo está disponible en Windows Vista.

 En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción y especifica un valor arbitrariamente bajo para el "período de vida" para estos mensajes (aproximadamente 2 segundos). El cliente también especifica una cola de mensajes no enviados personalizada utilizada para poner en cola los mensajes que han expirado.

 La aplicación del cliente puede leer los mensajes en la cola de mensajes no enviados e intentar enviar el mensaje o corregir el error que causó que el mensaje original fuera colocado en la cola de mensajes no enviados y enviar el mensaje. En el ejemplo, el cliente muestra un mensaje de error.

 El contrato de servicios es `IOrderProcessor`, tal y como se muestra en el código de ejemplo siguiente.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

 El código de servicio en el ejemplo es el del [enlace MSMQ de transacción](transacted-msmq-binding.md).

 La comunicación con el servicio tiene lugar dentro del ámbito de una transacción. El servicio lee los mensajes de la cola, realiza la operación y, a continuación, muestra los resultados de la operación. La aplicación también crea una cola de mensajes no enviados para mensajes no enviados.

```csharp
//The service contract is defined in generatedClient.cs, generated from the service by the svcutil tool.

//Client implementation code.
class Client
{
    static void Main()
    {
        // Get MSMQ queue name from app settings in configuration
        string deadLetterQueueName = ConfigurationManager.AppSettings["deadLetterQueueName"];

        // Create the transacted MSMQ queue for storing dead message if necessary.
        if (!MessageQueue.Exists(deadLetterQueueName))
            MessageQueue.Create(deadLetterQueueName, true);

        // Create a proxy with given client endpoint configuration
        OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");

        // Create the purchase order
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

        //Create a transaction scope.
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            // Make a queued call to submit the purchase order
            client.SubmitPurchaseOrder(po);
            // Complete the transaction.
            scope.Complete();
        }

        client.Close();

        Console.WriteLine();
        Console.WriteLine("Press <ENTER> to terminate client.");
        Console.ReadLine();
    }
}
```

 La configuración del cliente especifica una duración corta para que el mensaje alcance el servicio. Si el mensaje no se puede transmitir dentro de la duración especificada, el mensaje expira y se mueve a la cola de mensajes no enviados.

> [!NOTE]
> Es posible que el cliente entregue el mensaje a la cola del servicio dentro de la hora especificada. Para asegurarse de ver el servicio de mensajes no enviados en acción, se debe ejecutar el cliente antes de iniciar el servicio. El mensaje espera y se entrega al servicio de mensajes no enviados.

 La aplicación debe definir qué cola utilizar como su cola de mensajes no enviados. Si no se especifica ninguna cola, la cola de mensajes transaccionales no enviados para todo el sistema predeterminada se utiliza para poner en la cola los mensajes no enviados. En este ejemplo, la aplicación cliente especifica su propia cola de mensajes no enviados de la aplicación.

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <appSettings>
    <!-- use appSetting to configure MSMQ Dead Letter queue name -->
    <add key="deadLetterQueueName" value=".\private$\ServiceModelSamplesOrdersAppDLQ"/>
  </appSettings>

  <system.serviceModel>
    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                binding="netMsmqBinding"
                bindingConfiguration="PerAppDLQBinding"
                contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="PerAppDLQBinding"
                 deadLetterQueue="Custom"
                 customDeadLetterQueue="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                 timeToLive="00:00:02"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>

</configuration>
```

 El servicio de mensajes no enviados lee los mensajes de la cola de mensajes no enviados. El servicio de mensajes no enviados implementa el contrato `IOrderProcessor`. Sin embargo, su implementación no es procesar las órdenes. El servicio de mensajes no enviados es un servicio del cliente y no tiene facilidad para procesar las órdenes.

> [!NOTE]
> La cola de mensajes no enviados es una cola del cliente y es local al administrador de cola del cliente.

 La implementación de servicio de mensajes no enviados comprueba la razón por la que un mensaje no se ha enviado y toma medidas de corrección. La razón de un error en el envío del mensaje se captura en dos enumeraciones, <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryFailure%2A> y <xref:System.ServiceModel.Channels.MsmqMessageProperty.DeliveryStatus%2A>. Se puede recuperar el <xref:System.ServiceModel.Channels.MsmqMessageProperty> de <xref:System.ServiceModel.OperationContext> como se muestra en el código muestra siguiente:

```csharp
public void SubmitPurchaseOrder(PurchaseOrder po)
{
    Console.WriteLine("Submitting purchase order did not succeed ", po);
    MsmqMessageProperty mqProp =
                  OperationContext.Current.IncomingMessageProperties[
                  MsmqMessageProperty.Name] as MsmqMessageProperty;
    Console.WriteLine("Message Delivery Status: {0} ",
                                                mqProp.DeliveryStatus);
    Console.WriteLine("Message Delivery Failure: {0}",
                                               mqProp.DeliveryFailure);
    Console.WriteLine();
    …
}
```

 Los mensajes en la cola de mensajes no enviados son mensajes que se dirigen al servicio que está procesando el mensaje. Por lo tanto, cuando el servicio de mensajes no enviados Lee los mensajes de la cola, el nivel de canal de Windows Communication Foundation (WCF) detecta la falta de coincidencia en los extremos y no envía el mensaje. En este caso, el mensaje se dirige al servicio de procesamiento de la orden, pero quien lo recibe es el servicio de mensajes no enviados. Para recibir un mensaje que se dirige a un punto de conexión diferente, una dirección se filtra para coincidir con cualquier dirección especificada en `ServiceBehavior`. Esto se exigen para procesar correctamente los mensajes que se leen de la cola de mensajes no enviados.

 En este ejemplo, el servicio de mensajes con problemas de entrega reenvía el mensaje si el motivo del error es que el mensaje ha agotado el tiempo de espera. Por todas las demás razones, muestra el error de entrega, tal como se muestra en el siguiente código de ejemplo:

```csharp
// Service class that implements the service contract.
// Added code to write output to the console window.
[ServiceBehavior(InstanceContextMode=InstanceContextMode.Single, ConcurrencyMode=ConcurrencyMode.Single, AddressFilterMode=AddressFilterMode.Any)]
public class PurchaseOrderDLQService : IOrderProcessor
{
    OrderProcessorClient orderProcessorService;
    public PurchaseOrderDLQService()
    {
        orderProcessorService = new OrderProcessorClient("OrderProcessorEndpoint");
    }

    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po)
    {
        Console.WriteLine("Submitting purchase order did not succeed ", po);
        MsmqMessageProperty mqProp = OperationContext.Current.IncomingMessageProperties[MsmqMessageProperty.Name] as MsmqMessageProperty;

        Console.WriteLine("Message Delivery Status: {0} ", mqProp.DeliveryStatus);
        Console.WriteLine("Message Delivery Failure: {0}", mqProp.DeliveryFailure);
        Console.WriteLine();

        // resend the message if timed out
        if (mqProp.DeliveryFailure == DeliveryFailure.ReachQueueTimeout ||
            mqProp.DeliveryFailure == DeliveryFailure.ReceiveTimeout)
        {
            // re-send
            Console.WriteLine("Purchase order Time To Live expired");
            Console.WriteLine("Trying to resend the message");

            // reuse the same transaction used to read the message from dlq to enqueue the message to app. queue
            orderProcessorService.SubmitPurchaseOrder(po);
            Console.WriteLine("Purchase order resent");
        }
    }

    // Host the service within this EXE console application.
    public static void Main()
    {
        // Create a ServiceHost for the PurchaseOrderDLQService type.
        using (ServiceHost serviceHost = new ServiceHost(typeof(PurchaseOrderDLQService)))
        {
            // Open the ServiceHostBase to create listeners and start listening for messages.
            serviceHost.Open();

            // The service can now be accessed.
            Console.WriteLine("The dead letter service is ready.");
            Console.WriteLine("Press <ENTER> to terminate service.");
            Console.WriteLine();
            Console.ReadLine();
        }
    }
}
```

 El ejemplo siguiente muestra la configuración para un mensaje no enviado:

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.PurchaseOrderDLQService">
        <!-- Define NetMsmqEndpoint in this case, DLQ end point to read messages-->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesOrdersAppDLQ"
                  binding="netMsmqBinding"
                  bindingConfiguration="DefaultBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                 address="net.msmq://localhost/private/ServiceModelSamplesDeadLetter"
                 binding="netMsmqBinding"
                 bindingConfiguration="SystemDLQBinding"
                 contract="IOrderProcessor" />
    </client>

    <bindings>
      <netMsmqBinding>
        <binding name="DefaultBinding" />
        <binding name="SystemDLQBinding"
                 deadLetterQueue="System"/>
      </netMsmqBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

 Para ejecutar el ejemplo, hay 3 aplicaciones ejecutables para ejecutar para ver cómo la cola de mensajes no enviados funciona para cada aplicación; el cliente, el servicio y el servicio de mensajes no enviados que lee de la cola de mensajes no enviados para cada aplicación y reenvían el mensaje al servicio. Todos son las aplicaciones de consola con el resultado de ventanas de consola.

> [!NOTE]
> Debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes. Se debe iniciar el servicio y apagarlo para que se pueda crear la cola.

 Al ejecutar el cliente, el cliente muestra el mensaje:

```console
Press <ENTER> to terminate client.
```

 El cliente intentó enviar el mensaje pero con un tiempo de espera corto, el mensaje expiró y se puso en la cola, y ahora se encuentra en la cola de mensajes no enviados para cada aplicación.

 Ejecute a continuación el servicio de mensajes no enviados, que lee el mensaje y muestra el código del error y reenvía de nuevo el mensaje al servicio.

```console
The dead letter service is ready.
Press <ENTER> to terminate service.

Submitting purchase order did not succeed
Message Delivery Status: InDoubt
Message Delivery Failure: ReachQueueTimeout

Purchase order Time To Live expired
Trying to resend the message
Purchase order resent
```

 El servicio se inicia y, a continuación, lee el mensaje reenviado y lo procesa.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 97897eff-f926-4057-a32b-af8fb11b9bf9
        Customer: somecustomer.com
        OrderDetails
                Order LineItem: 54 of Blue Widget @unit price: $29.99
                Order LineItem: 890 of Red Widget @unit price: $45.89
        Total cost of this order: $42461.56
        Order status: Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).

2. Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.

    1. Abra Administrador del servidor en Visual Studio 2012.

    2. Expanda la pestaña **características** .

    3. Haga clic con el botón secundario en **colas de mensajes privadas** y seleccione **nuevo**, **cola privada**.

    4. Active la casilla **transaccional** .

    5. Escriba `ServiceModelSamplesTransacted` como nombre de la nueva cola.

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Para ejecutar el ejemplo en una configuración de un solo equipo o entre equipos, cambie los nombres de cola de forma adecuada, reemplazando localhost por el nombre completo del equipo y siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo

1. Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding name="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

     Asegúrese de que el punto de conexión está asociado con el enlace definiendo el atributo `bindingConfiguration` del punto de conexión.

2. Asegúrese de que cambia la configuración en el servidor DeadLetterService y en el cliente antes de ejecutar el ejemplo.

    > [!NOTE]
    > Establecer `security mode` en `None` es equivalente a definir `MsmqAuthenticationMode`, `MsmqProtectionLevel` y la seguridad de `Message` en `None`.

## <a name="comments"></a>Comentarios

 De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada. Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte. De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`. Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio. Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\DeadLetter`  
