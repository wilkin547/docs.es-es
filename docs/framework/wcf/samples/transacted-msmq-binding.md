---
description: 'Más información sobre: enlace de MSMQ con transacciones'
title: Enlace MSMQ por transacciones
ms.date: 03/30/2017
ms.assetid: 71f5cb8d-f1df-4e1e-b8a2-98e734a75c37
ms.openlocfilehash: 17fdcdb169c9e57c1a95d5aea4c79654e3739664
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668535"
---
# <a name="transacted-msmq-binding"></a>Enlace MSMQ por transacciones

Este ejemplo muestra cómo llevar a cabo la comunicación en cola por transacciones utilizando Message Queuing (MSMQ).

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no se tienen que estar ejecutando simultáneamente para comunicarse mediante una cola.

Cuando las transacciones se utilizan para enviar y recibir los mensajes, hay en realidad dos transacciones independientes. Cuando el cliente envía los mensajes dentro del ámbito de una transacción, la transacción es local para el cliente y el administrador de cola del cliente. Cuando el servicio recibe los mensajes dentro del ámbito de la transacción, la transacción es local para el servicio y el administrador de cola receptor. Es muy importante recordar que el cliente y el servicio no están participando en la misma transacción; más bien, están utilizando distintas transacciones al realizar sus operaciones (como enviar y recibir) con la cola.

En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción. El servicio recibe a continuación los mensajes enviados a la cola dentro del ámbito de la transacción definido por el servicio.

El contrato de servicios es `IOrderProcessor`, tal y como se muestra en el código de ejemplo siguiente. La interfaz define un servicio unidireccional que es conveniente para su uso con las colas.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po);
}
```

El comportamiento del servicio define un comportamiento de la operación con `TransactionScopeRequired` definido en `true`. Esto garantiza que los administradores de recursos a los que el método tiene acceso utilizan el mismo ámbito de la transacción usado para recuperar el mensaje de la cola. También garantiza que si el método produce una excepción, el mensaje se devuelva a la cola. Sin establecer este comportamiento de operación, un canal en cola crea una transacción para leer el mensaje de la cola y lo confirma automáticamente antes de la expedición de tal manera que si se produce un error en la operación, el mensaje se pierde. El escenario más común es para que las operaciones de servicio den de alta en la transacción que se utiliza para leer el mensaje de la cola, tal y como se muestra en el código siguiente.

```csharp
 // This service class that implements the service contract.
 // This added code writes output to the console window.
 public class OrderProcessorService : IOrderProcessor
 {
     [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
     public void SubmitPurchaseOrder(PurchaseOrder po)
     {
         Orders.Add(po);
         Console.WriteLine("Processing {0} ", po);
     }
  …
}
```

El servicio se hospeda en sí mismo. Al utilizar el transporte de MSMQ, se debe crear la cola utilizada de antemano. Esto se puede hacer manualmente o a través de código. En este ejemplo, el servicio contiene el código para comprobar la existencia de la cola y crearla si no existe. El nombre de la cola se lee del archivo de configuración. La [herramienta de utilidad de metadatos de ServiceModel (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) utiliza la dirección base para generar el proxy en el servicio.

```csharp
// Host the service within this EXE console application.
public static void Main()
{
    // Get the MSMQ queue name from appSettings in configuration.
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

        // Close the ServiceHost to shut down the service.
        serviceHost.Close();
    }
}
```

El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración, tal y como se muestra en la configuración de ejemplo siguiente.

```xml
<appSettings>
    <add key="queueName" value=".\private$\ServiceModelSamplesTransacted" />
</appSettings>
```

> [!NOTE]
> El nombre de la cola usa un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso al crear la cola mediante <xref:System.Messaging>. El extremo Windows Communication Foundation (WCF) utiliza la dirección de la cola con el esquema net. MSMQ, usa "localhost" para indicar el equipo local y utiliza barras diagonales en su ruta de acceso.

El cliente crea un ámbito de transacción. La comunicación con la cola tiene lugar dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde se envían todos los mensajes a la cola o no se envía ninguno. La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A> en el ámbito de la transacción.

```csharp
// Create a client.
OrderProcessorClient client = new OrderProcessorClient();

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

// Create a transaction scope.
using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
{
    // Make a queued call to submit the purchase order.
    client.SubmitPurchaseOrder(po);
    // Complete the transaction.
    scope.Complete();
}

// Closing the client gracefully closes the connection and cleans up resources.
client.Close();

Console.WriteLine();
Console.WriteLine("Press <ENTER> to terminate client.");
Console.ReadLine();
```

Para comprobar que las transacciones están funcionando, modifique el cliente marcando como comentario el ámbito de transacción tal y como se muestra en el siguiente código de ejemplo, recompile la solución y ejecute el cliente.

```csharp
//scope.Complete();
```

Dado que no se completa la transacción, los mensajes no se envían a la cola.

Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente. Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes.

```console
The service is ready.
Press <ENTER> to terminate service.

Processing Purchase Order: 7b31ce51-ae7c-4def-9b8b-617e4288eafd
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

4. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).

De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada. Hay dos propiedades importantes para la seguridad del transporte de MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A>. De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`. Para MSMQ proporcionar la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de Active Directory para MSMQ. Si ejecuta este ejemplo en un equipo que no satisface estos criterios, recibirá un error.

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin la integración de Active Directory

1. Si su equipo no es parte de un dominio o no tiene la integración Active Directory instalada, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en el código de configuración de ejemplo siguiente:

    ```xml
    <system.serviceModel>
      <services>
        <service name="Microsoft.ServiceModel.Samples.OrderProcessorService"
                 behaviorConfiguration="OrderProcessorServiceBehavior">
          <host>
            <baseAddresses>
              <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>
            </baseAddresses>
          </host>
          <!-- Define NetMsmqEndpoint. -->
          <endpoint
              address="net.msmq://localhost/private/ServiceModelSamplesTransacted"
              binding="netMsmqBinding"
              bindingConfiguration="Binding1"
           contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
          <!-- The mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex. -->
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
            <behavior name="OrderProcessorServiceBehavior">
              <serviceMetadata httpGetEnabled="True"/>
            </behavior>
          </serviceBehaviors>
        </behaviors>

      </system.serviceModel>
    ```

2. Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.

    > [!NOTE]
    > Establecer `security mode` en `None` es equivalente a definir la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.

> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Transacted`
