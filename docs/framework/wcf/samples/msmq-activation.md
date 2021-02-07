---
description: 'Más información sobre: activación de MSMQ'
title: Activación MSMQ
ms.date: 03/30/2017
ms.assetid: e3834149-7b8c-4a54-806b-b4296720f31d
ms.openlocfilehash: 3360ae560cba9c3b42551617beb295154668814b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99752249"
---
# <a name="msmq-activation"></a>Activación MSMQ

Este ejemplo muestra cómo hospedar aplicaciones en el servicio de activación del proceso de Windows (WAS) que se lee en una cola de mensajes. Este ejemplo utiliza `netMsmqBinding` y se basa en el ejemplo de [comunicación bidireccional](two-way-communication.md) . El servicio en este caso es una aplicación hospedada en web y el cliente es autohospedado y proporciona resultados a la consola para observar el estado de pedidos de compra enviados.

> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.

> [!NOTE]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.
>
> \<InstallDrive>: \ WF_WCF_Samples
>
> Si este directorio no existe, vaya a los [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos y WCF. Este ejemplo se encuentra en el siguiente directorio.
>
> \<InstallDrive>:\Samples\WCFWFCardSpace\WCF\Basic\Services\Hosting\WASHost\MsmqActivation.

Windows Process Activation Service (WAS), el nuevo mecanismo de activación de procesos para Windows Server 2008, proporciona características similares a las de IIS que anteriormente solo estaban disponibles para aplicaciones basadas en HTTP a aplicaciones que usan protocolos que no son HTTP. Windows Communication Foundation (WCF) usa la interfaz del adaptador del agente de escucha para comunicar las solicitudes de activación que se reciben a través de los protocolos no HTTP admitidos por WCF, como TCP, canalizaciones con nombre y MSMQ. La funcionalidad para recibir solicitudes a través de protocolos no http está hospedada por servicios de Windows administrados que se ejecutan en SMSvcHost.exe.

El servicio Net.Msmq Listener Adapter (NetMsmqActivator) activa aplicaciones en cola basadas en mensajes en la cola.

El cliente envía los pedidos de compra al servicio desde dentro del ámbito de una transacción. El servicio recibe las órdenes en una transacción y las procesa. El servicio llama a continuación de nuevo al cliente con el estado del orden. Para facilitar la comunicación bidireccional, tanto el cliente como el servicio utilizan las colas para poner en cola los pedidos de compra y el estado de la orden.

El contrato de servicio `IOrderProcessor` define operaciones de servicio unidireccionales que funcionan en cola. La operación del servicio utiliza el extremo de respuesta para enviar estados de orden al cliente. La dirección de punto de conexión de la respuesta es el URI de la cola utilizado para devolver el estado del orden al cliente. La aplicación de procesamiento de orden implementa este contrato.

```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
public interface IOrderProcessor
{
    [OperationContract(IsOneWay = true)]
    void SubmitPurchaseOrder(PurchaseOrder po,
                                           string reportOrderStatusTo);
}
```

El cliente especifica el contrato de la respuesta para enviar el estado de la orden. El cliente implementa el contrato del estado de la orden. El servicio utiliza el cliente generado de este contrato para devolver el estado de la orden al cliente.

```csharp
[ServiceContract]
public interface IOrderStatus
{
    [OperationContract(IsOneWay = true)]
    void OrderStatus(string poNumber, string status);
}
```

La operación del servicio procesa el pedido de compra enviado. <xref:System.ServiceModel.OperationBehaviorAttribute> se aplica a la operación del servicio para especificar la inscripción automática en la transacción que se utiliza para recibir el mensaje de la cola y la realización automática de la transacción en la realización de la operación del servicio. La clase `Orders` encapsula la funcionalidad del procesamiento de la orden. En este caso, agrega el pedido de compra a un diccionario. La transacción en la que la operación del servicio se dio de alta está disponible para las operaciones en la clase `Orders`.

La operación del servicio, además de procesar el pedido de compra enviado, responde de nuevo al cliente acerca del estado de la orden.

```csharp
public class OrderProcessorService : IOrderProcessor
{
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]
    public void SubmitPurchaseOrder(PurchaseOrder po, string reportOrderStatusTo)
    {
        Orders.Add(po);
        Console.WriteLine("Processing {0} ", po);
        Console.WriteLine("Sending back order status information");
        NetMsmqBinding msmqCallbackBinding = new NetMsmqBinding();
        msmqCallbackBinding.Security.Mode = NetMsmqSecurityMode.None;
        OrderStatusClient client = new OrderStatusClient(msmqCallbackBinding, new EndpointAddress(reportOrderStatusTo));
        // please note that the same transaction that is used to dequeue purchase order is used
        // to send back order status
        using (TransactionScope scope = new TransactionScope(TransactionScopeOption.Required))
        {
            client.OrderStatus(po.PONumber, po.Status);
            scope.Complete();
        }
    }
}
```

El enlace de cliente que se ha de utilizar se especifica utilizando un archivo de configuración.

El nombre de cola de MSMQ se especifica en una sección appSettings del archivo de configuración. El punto de conexión para el servicio se define en la sección de System.ServiceModel del archivo de configuración.

> [!NOTE]
> El nombre de cola de MSMQ y la dirección de extremo utilizan convenciones de direccionamiento ligeramente diferentes. El nombre de la cola de MSMQ utiliza un punto (.) para el equipo local y separadores con barra diagonal inversa en su ruta de acceso. La dirección del extremo de WCF especifica un esquema net. MSMQ:, usa el "localhost" para el equipo local y utiliza barras diagonales en su ruta de acceso. Para leer de una cola que se hospeda en el equipo remoto, reemplace "." y “localhost” con el nombre del equipo remoto.

Se utiliza un archivo .svc con el nombre de la clase para hospedar el código del servicio en WAS.

El propio archivo Service.svc contiene una directiva para crear `OrderProcessorService`.

`<%@ServiceHost language="c#" Debug="true" Service="Microsoft.ServiceModel.Samples.OrderProcessorService"%>`

El archivo Service.svc también contiene una directiva de ensamblado para asegurar que se carga System.Transactions.dll.

`<%@Assembly name="System.Transactions, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"%>`

El cliente crea un ámbito de transacción. La comunicación con el servicio tiene lugar dentro del ámbito de la transacción, produciendo que se trate como una unidad atómica donde todos los mensajes tienen éxito o dan error. La transacción se confirma llamando a `Complete` en el ámbito de la transacción.

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(OrderStatusService)))
{
    // Open the ServiceHostBase to create listeners and start listening
    // for order status messages.
    serviceHost.Open();

    // Create a proxy with given client endpoint configuration
    OrderProcessorClient client = new OrderProcessorClient();

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
    using (TransactionScope scope = new
        TransactionScope(TransactionScopeOption.Required))
    {
        // Make a queued call to submit the purchase order
        client.SubmitPurchaseOrder(po,
       "net.msmq://localhost/private/ServiceModelSamplesOrder/OrderStatus");
        // Complete the transaction.
        scope.Complete();
    }

    //Closing the client gracefully closes the connection and cleans up
    //resources
    client.Close();

    Console.WriteLine();
    Console.WriteLine("Press <ENTER> to terminate client.");
    Console.ReadLine();

    // Close the ServiceHostBase to shutdown the service.
    serviceHost.Close();
    }
```

El código de cliente implementa el contrato`IOrderStatus` para recibir el estado de la orden del servicio. En este caso, imprime el estado de la orden.

```csharp
[ServiceBehavior]
public class OrderStatusService : IOrderStatus
{
    [OperationBehavior(TransactionAutoComplete = true,
                        TransactionScopeRequired = true)]
    public void OrderStatus(string poNumber, string status)
    {
        Console.WriteLine("Status of order {0}:{1} ",
                                         poNumber , status);
    }
}
```

La cola de estado de la orden se crea en el método `Main`. La configuración del cliente incluye la configuración del servicio del estado de la orden para hospedar el servicio del estado de la orden, tal y como se muestra en la configuración del ejemplo siguiente.

```xml
<appSettings>
    <!-- use appSetting to configure MSMQ queue name -->
    <add key="targetQueueName" value=".\private$\ServiceModelSamples/service.svc" />
    <add key="responseQueueName" value=".\private$\ServiceModelSamples/OrderStatus" />
  </appSettings>

<system.serviceModel>

    <services>
      <service
         name="Microsoft.ServiceModel.Samples.OrderStatusService">
        <!-- Define NetMsmqEndpoint -->
        <endpoint address="net.msmq://localhost/private/ServiceModelSamples/OrderStatus"
                  binding="netMsmqBinding"
                  contract="Microsoft.ServiceModel.Samples.IOrderStatus" />
      </service>
    </services>

    <client>
      <!-- Define NetMsmqEndpoint -->
      <endpoint name="OrderProcessorEndpoint"
                address="net.msmq://localhost/private/ServiceModelSamples/service.svc"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />
    </client>

  </system.serviceModel>
```

Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servidor. Puede ver que el servidor recibe mensajes desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servidor y el cliente.

El cliente muestra la información del estado de la orden enviada por el servidor.

```console
Press <ENTER> to terminate client.
Status of order 70cf9d63-3dfa-4e69-81c2-23aa4478ebed :Pending
```

### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo

1. Asegúrese de que IIS 7,0 está instalado, ya que es necesario para la activación WAS.

2. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md). Además, debe instalar los componentes de activación que no son HTTP de WCF:

    1. En el menú **Inicio**, elija **Panel de control**.

    2. Seleccione **programas y características**.

    3. Haga clic en **activar o desactivar las características de Windows**.

    4. En **Resumen de características**, haga clic en **Agregar características**.

    5. Expanda el nodo **Microsoft .NET Framework 3,0** y compruebe la **Windows Communication Foundation característica activación no http** .

3. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).

4. Ejecute el cliente ejecutando client.exe de una ventana de comandos. Esto crea la cola y envía un mensaje a la misma. Deje que el cliente se ejecute para ver el resultado del servicio que lee el mensaje

5. El servicio de activación MSMQ se ejecuta como servicio de red de manera predeterminada. Por consiguiente, la cola que se utiliza para activar la aplicación debe tener permisos de recepción y lectura para el Servicio de la Red. Esto se puede agregar utilizando el MMC de Message Queuing:

    1. En el menú **Inicio** , haga clic en **Ejecutar**, escriba `Compmgmt.msc` y presione Entrar.

    2. En **servicios y aplicaciones**, expanda **Message Queue Server**.

    3. Haga clic en **colas privadas**.

    4. Haga clic con el botón secundario en la cola (servicemodelsamples/Service. SVC) y elija **propiedades**.

    5. En la pestaña **seguridad** , haga clic en **Agregar** y proporcione permisos de lectura y recepción al servicio de red.

6. Configure el Windows Process Activation Service (WAS) para admitir la activación de MSMQ.

    Para su comodidad, los dos pasos siguientes se implementan en un archivo por lotes denominado AddMsmqSiteBinding.cmd que se encuentra en el directorio de ejemplo.

    1. Para admitir la activación de net.msmq, el sitio web predeterminado debe enlazarse primero al protocolo net.msmq. Esto se puede hacer utilizando appcmd.exe, que se instala con el conjunto de herramientas de administración de IIS 7.0. Desde un símbolo del sistema con permisos elevados (administrador), ejecute el comando siguiente.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"
        -+bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > Este comando es una sola línea de texto.

        Este comando agrega un enlace del sitio de net.msmq al sitio web predeterminado.

    2. Aunque todas las aplicaciones dentro de un sitio comparten un enlace net.msmq común, cada aplicación puede habilitar la compatibilidad con net.msmq individualmente. Para habilitar net.msmq para la aplicación /servicemodelsamples, ejecute el comando siguiente desde un símbolo del sistema con permisos elevados.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.msmq
        ```

        > [!NOTE]
        > Este comando es una sola línea de texto.

        Este comando permite tener acceso a la aplicación/servicemodelsamples mediante `http://localhost/servicemodelsamples` y `net.msmq://localhost/servicemodelsamples` .

7. Si no lo ha hecho previamente, asegúrese de que el servicio de activación MSMQ está habilitado. En el menú **Inicio** , haga clic en **Ejecutar** y escriba `Services.msc` . Busque en la lista de servicios el **adaptador de escucha net. MSMQ**. Haga clic con el botón secundario y seleccione **Propiedades**. Establezca el **tipo de inicio** en **automático**, haga clic en **aplicar** y haga clic en el botón **iniciar** . Este paso solo debe realizarse una vez antes del primer uso del servicio de Adaptador de escucha Net.Msmq.

8. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md). Además, cambie el código en el cliente que envía el pedido de compra para reflejar el nombre de equipo en el URI de la cola al enviar el pedido de compra. Use el código siguiente:

    ```csharp
    client.SubmitPurchaseOrder(po, "net.msmq://localhost/private/ServiceModelSamples/OrderStatus");
    ```

9. Quite el enlace del sitio de net.msmq que ha agregado para este ejemplo.

    Para su comodidad, los pasos siguientes se implementan en un archivo de información denominado RemoveMsmqSiteBinding.cmd que se encuentra en el directorio de ejemplo:

    1. Quite net.msmq de la lista de protocolos habilitados ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http
        ```

        > [!NOTE]
        > Este comando es una sola línea de texto.

    2. Quitar el enlace del sitio de net.msmq ejecutando el comando siguiente desde un símbolo del sistema con permisos elevados.

        ```console
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.msmq',bindingInformation='localhost']
        ```

        > [!NOTE]
        > Este comando es una sola línea de texto.

    > [!WARNING]
    > Al ejecutar el archivo por lotes, se restablecerá DefaultAppPool para que se ejecute utilizando la versión 2.0 de .NET Framework.

De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada. Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte. De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`. Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio. Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".

### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo

1. Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en cero, tal y como se muestra en la configuración de ejemplo siguiente.

    ```xml
    <bindings>
        <netMsmqBinding>
            <binding configurationName="TransactedBinding">
                <security mode="None"/>
            </binding>
        </netMsmqBinding>
    </bindings>
    ```

2. Cambie la configuración en el servidor y el cliente antes de ejecutar el ejemplo.

    > [!NOTE]
    > Establecer `security mode` en `None` es equivalente a definir `MsmqAuthenticationMode`, `MsmqProtectionLevel` y la seguridad de `Message` en `None`.

3. Para habilitar la activación en un equipo combinado a un grupo de trabajo, el servicio de activación y el proceso de trabajador se deben ejecutar con una cuenta de usuario concreta (debe ser la misma para ambos) y la cola debe tener ACL para la cuenta de usuario concreta.

     Para cambiar la identidad bajo la que el proceso de trabajador se ejecuta:

    1. Ejecute Inetmgr.exe.

    2. En **grupos de aplicaciones**, haga clic con el botón derecho en el **AppPool** (normalmente, **DefaultAppPool**) y elija **establecer valores predeterminados de grupo de aplicaciones..**..

    3. Cambie las propiedades Identity para utilizar la cuenta de usuario concreta.

     Para cambiar la identidad bajo la que el Servicio de Activación se ejecuta:

    1. Ejecute Services.msc.

    2. Haga clic con el botón secundario en el **adaptador net. MsmqListener** y elija **propiedades**.

4. Cambie la cuenta en la pestaña **Inicio de sesión** .

5. En un grupo de trabajo, el servicio se debe ejecutar también utilizando un token sin restricciones. Para ello, ejecute lo siguiente en una ventana de comandos:

    ```console
    sc sidtype netmsmqactivator unrestricted
    ```

## <a name="see-also"></a>Vea también

- [Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))
