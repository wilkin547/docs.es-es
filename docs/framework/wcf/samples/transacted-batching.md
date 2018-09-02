---
title: Procesamiento por lotes con transacciones
ms.date: 03/30/2017
ms.assetid: ecd328ed-332e-479c-a894-489609bcddd2
ms.openlocfilehash: abada9aaf5fac8f05599467f385e708e1898832f
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43416653"
---
# <a name="transacted-batching"></a>Procesamiento por lotes con transacciones
Este ejemplo muestra cómo procesar por lotes transacciones leídas mediante Message Queuing (MSMQ). El procesamiento por lotes con transacciones es una característica de optimización de rendimiento para las transacciones leídas en comunicación en cola.  
  
> [!NOTE]
>  El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.  
  
 Este ejemplo muestra el procesamiento por lotes con transacciones. El procesamiento por lotes con transacciones es un comportamiento que habilita el uso de una transacción única cuando se leen y se procesan muchos mensajes en la cola.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.  
  
    1.  Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Expanda el **características** ficha.  
  
    3.  Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.  
  
    4.  Compruebe el **transaccional** cuadro.  
  
    5.  Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.  
  
    > [!NOTE]
    >  En este ejemplo, el cliente envía cientos de mensajes como parte del lote. Es normal que la aplicación del servicio tarde algún tiempo en procesarlos.  
  
3.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup-or-without-active-directory-integration"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo o sin integración con Active Directory  
  
1.  De forma predeterminada con <xref:System.ServiceModel.NetMsmqBinding>, la seguridad de transporte está habilitada. Hay dos propiedades pertinentes para la seguridad de transporte MSMQ, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A> y <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> `.` de forma predeterminada, el modo de autenticación se establece en `Windows` y el nivel de protección se establece en `Sign`. Para que MSMQ proporcione la autenticación y la característica de firma, debe formar parte de un dominio y debe instalarse la opción de integración de directorio activo para MSMQ. Si ejecuta este ejemplo en un equipo que no cumple estos criterios, recibirá un error.  
  
2.  Si su equipo no es parte de un dominio o no tiene la integración del directorio activo instalada, desactive la seguridad de transporte, estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:  
  
    ```xml  
    <system.serviceModel>  
      <behaviors>  
        <serviceBehaviors>  
          <behavior name="ThrottlingBehavior">  
            <serviceMetadata httpGetEnabled="true"/>  
            <serviceThrottling maxConcurrentCalls="5"/>  
          </behavior>  
        </serviceBehaviors>  
  
        <endpointBehaviors>  
          <behavior name="BatchingBehavior">  
            <transactedBatching maxBatchSize="100"/>  
          </behavior>  
        </endpointBehaviors>  
      </behaviors>  
      <services>  
        <service   
            behaviorConfiguration="ThrottlingBehavior"   
            name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
          <host>  
            <baseAddresses>  
              <add baseAddress="http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
            </baseAddresses>  
          </host>  
          <!-- Define NetMsmqEndpoint -->  
          <endpoint address="net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                    binding="netMsmqBinding"  
                    bindingConfiguration="Binding1"   
                    behaviorConfiguration="BatchingBehavior"   
                    contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
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
  
    </system.serviceModel>  
    ```  
  
3.  Asegúrese de que cambia la configuración en el servidor y el cliente antes de ejecutar el ejemplo.  
  
    > [!NOTE]
    >  Establecer `security``mode` en `None` es equivalente a definir la seguridad de <xref:System.ServiceModel.MsmqTransportSecurity.MsmqAuthenticationMode%2A>, <xref:System.ServiceModel.MsmqTransportSecurity.MsmqProtectionLevel%2A> y `Message` en `None`.  
  
4.  Para ejecutar la base de datos en un equipo remoto, cambie la cadena de conexión para que señale al equipo en el que reside la base de datos.  
  
## <a name="requirements"></a>Requisitos  
 Para ejecutar este ejemplo, MSMQ debe estar instalado, y se necesitan SQL o SQL Express.  
  
## <a name="demonstrates"></a>Demostraciones  
 El ejemplo muestra el comportamiento del procesamiento por lotes con transacciones. El procesamiento por lotes con transacciones es una característica de optimización de rendimiento proporcionada con el transporte por colas de MSMQ.  
  
 Cuando las transacciones se utilizan para enviar y recibir mensajes, hay en realidad 2 transacciones independientes. Cuando el cliente envía los mensajes dentro del ámbito de una transacción, la transacción es local para el cliente y el administrador de cola del cliente. Cuando el servicio recibe los mensajes dentro del ámbito de la transacción, la transacción es local para el servicio y el administrador de cola receptor. Es muy importante recordar que el cliente y el servicio no están participando en la misma transacción; más bien, están utilizando distintas transacciones al realizar sus operaciones (como enviar y recibir) con la cola.  
  
 En el ejemplo utilizamos una transacción única para la ejecución de varias operaciones del servicio. Esto se utiliza solo como una característica de optimización de rendimiento y no tiene afecta a la semántica de la aplicación. El ejemplo se basa en [transacciones enlace MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md).  
  
## <a name="comments"></a>Comentarios  
 En este ejemplo, el cliente envía un lote de mensajes al servicio desde dentro del ámbito de una transacción. Enviamos un número grande de mensajes que muestre la optimización de rendimiento; en este caso, hasta 2500 mensajes.  
  
 El servicio recibe a continuación los mensajes enviados a la cola dentro del ámbito de la transacción definido por el servicio. Sin el procesamiento por lotes, esto produce 2500 transacciones para cada invocación de la operación del servicio. Esto afecta el rendimiento del sistema. Dado que dos administradores de recursos están implicados, la cola de MSMQ y la base de datos `Orders`- cada transacción de este tipo es una transacción de DTC. Optimizamos esto utilizando un número mucho menor de transacciones asegurando que un lote de mensajes e invocaciones de operación de servicio pasan en una transacción única.  
  
 Utilizamos la característica por lotes mediante:  
  
-   La especificación del comportamiento del procesamiento por lotes con transacciones en configuración.  
  
-   La especificación del tamañao de un lote en términos del número de mensajes que se leen utilizando una transacción única.  
  
-   La especificación del número máximo de lotes simultáneos ejecutados.  
  
 En este ejemplo, mostramos ganancias en el rendimiento reduciendo el número de transacciones asegurando que 100 operaciones del servicio se invocan en una transacción única antes de confirmar la transacción.  
  
 El comportamiento del servicio define un comportamiento de la operación con `TransactionScopeRequired` definido en `true`. Esto garantiza que los administradores de recursos a los que el método tiene acceso utilizan el mismo ámbito de la transacción usado para recuperar el mensaje de la cola. En este ejemplo, utilizamos una base de datos básica para almacenar la información del pedido de compra contenida en el mensaje. El ámbito de la transacción también garantiza que si el método produce una excepción, el mensaje se devuelva a la cola. Sin establecer este comportamiento de operación, un canal en cola crea una transacción para leer el mensaje de la cola y lo confirma automáticamente antes de la expedición de tal manera que si se produce un error en la operación, el mensaje se pierde. El escenario más común es que las operaciones de servicio se inscriban en la transacción que se utiliza para leer el mensaje de la cola, tal y como se muestra en el código siguiente.  
  
 Observe que `ReleaseServiceInstanceOnTransactionComplete` está establecido en `false`. Éste es un requisito importante para el procesamiento por lotes. La propiedad `ReleaseServiceInstanceOnTransactionComplete` en `ServiceBehaviorAttribute` indica qué hacer con la instancia del servicio una vez la transacción se completa. De forma predeterminada, la instancia del servicio se lanza al completar la transacción. El aspecto básico del procesamiento por lotes es el uso de una transacción única para leer y enviar muchos mensajes en la cola. Por consiguiente, al lanzar la instancia del servicio, se acaba completando la transacción prematuramente, lo que niega el mismo uso del procesamiento por lotes. Si esta propiedad está establecida en `true` y el comportamiento del procesamiento por lotes con transacciones se agrega al extremo, el comportamiento de la validación por lotes produce una excepción.  

```csharp
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(ReleaseServiceInstanceOnTransactionComplete=false,   
TransactionIsolationLevel=  
System.Transactions.IsolationLevel.Serializable, ConcurrencyMode=ConcurrencyMode.Multiple)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true,  
                       TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
    …  
}  
```

 La clase `Orders` encapsula el procesamiento de la orden. En el ejemplo, actualiza la base de datos con información del pedido de compra.  

```csharp
// Order Processing Logic  
public class Orders  
{  
    public static void Add(PurchaseOrder po)  
    {  
        // Insert purchase order.  
        SqlCommand insertPurchaseOrderCommand =   
        new SqlCommand(  
        "insert into PurchaseOrders(poNumber, customerId)   
                               values(@poNumber, @customerId)");  
        insertPurchaseOrderCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        insertPurchaseOrderCommand.Parameters.Add("@customerId",   
                                         SqlDbType.VarChar, 50);  
  
        // Insert product line item.  
        SqlCommand insertProductLineItemCommand =   
             new SqlCommand("insert into ProductLineItems(productId,   
                    unitCost, quantity, poNumber) values(@productId,   
                    @unitCost, @quantity, @poNumber)");  
        insertProductLineItemCommand.Parameters.Add("@productId",   
                                           SqlDbType.VarChar, 50);  
        insertProductLineItemCommand.Parameters.Add("@unitCost",   
                                                  SqlDbType.Float);  
        insertProductLineItemCommand.Parameters.Add("@quantity",   
                                                     SqlDbType.Int);  
        insertProductLineItemCommand.Parameters.Add("@poNumber",   
                                           SqlDbType.VarChar, 50);  
        int rowsAffected = 0;  
        using (TransactionScope scope =   
              new TransactionScope(TransactionScopeOption.Required))  
        {  
             using (SqlConnection conn = new   
                 SqlConnection(  
                 ConfigurationManager.AppSettings["connectionString"]))  
             {  
                 conn.Open();  
  
                // Insert into purchase order table.  
               insertPurchaseOrderCommand.Connection = conn;  
               insertPurchaseOrderCommand.Parameters["@poNumber"].Value   
                                                       = po.PONumber;  
             insertPurchaseOrderCommand.Parameters["@customerId"].Value   
                                                    =po.CustomerId;  
             insertPurchaseOrderCommand.ExecuteNonQuery();  
  
            // Insert into product line item table.  
            insertProductLineItemCommand.Connection = conn;  
            foreach (PurchaseOrderLineItem orderLineItem in   
                                        po.orderLineItems) {  
            insertProductLineItemCommand.Parameters["@poNumber"].Value   
                                                          =po.PONumber;  
            insertProductLineItemCommand.Parameters["@productId"].Value   
                                             = orderLineItem.ProductId;  
            insertProductLineItemCommand.Parameters["@unitCost"].Value   
                                             = orderLineItem.UnitCost;  
            insertProductLineItemCommand.Parameters["@quantity"].Value   
                                             = orderLineItem.Quantity;  
            rowsAffected +=   
            insertProductLineItemCommand.ExecuteNonQuery();  
            }  
            scope.Complete();  
        }  
     }  
     Console.WriteLine(  
     "Updated database with {0} product line items  for purchase order   
                                     {1} ", rowsAffected, po.PONumber);  
    }  
}  
```

 El comportamiento del procesamiento por lotes y su configuración se especifican en la configuración de la aplicación del servicio.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName"   
     value=".\private$\ServiceModelSamplesTransactedBatching" />  
    <add key="baseAddress"   
     value=  
     "http://localhost:8000/orderProcessor/transactedBatchingSample"/>  
    <add key="connectionString" value="Data Source=.\SQLEXPRESS;AttachDbFilename=|DataDirectory|orders.mdf;Integrated Security=True;User Instance=True;" />  
  </appSettings>  
  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ThrottlingBehavior">  
          <serviceThrottling maxConcurrentCalls="5"/>  
        </behavior>  
      </serviceBehaviors>  
  
      <endpointBehaviors>  
        <behavior name="BatchingBehavior">  
          <transactedBatching maxBatchSize="100"/>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <services>  
      <service   
          behaviorConfiguration="ThrottlingBehavior"   
          name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address=  
"net.msmq://localhost/private/ServiceModelSamplesTransactedBatching"  
                  binding="netMsmqBinding"  
                  behaviorConfiguration="BatchingBehavior"   
                  contract=  
                    "Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
> [!NOTE]
>  El tamaño del lote es una pista para el sistema. Por ejemplo, si especifica un tamaño del lote de 20, entonces se leerían y se enviarían 20 mensajes utilizando una transacción única y, a continuación, se confirmaría la transacción. Pero hay casos donde la transacción puede confirmar el lote antes del tamaño del lote se alcanza.  
>   
>  Se asocia a cada transacción un tiempo de espera, que se inicia una vez se crea la transacción. Cuando este tiempo de espera expira se anula la transacción. Es posible que este tiempo de espera incluso expire antes de que se alcance el tamaño del lote. Para evitar tener que trabajar de nuevo sobre el lote debido a la interrupción, `TransactedBatchingBehavior` comprueba para ver cuánto tiempo queda en la transacción. Si se agota el 80% del tiempo de espera de la transacción, entonces se confirma la transacción.  
>   
>  Si no hay ningún mensaje más en la cola, en lugar de esperar a que se alcance el tamaño del lote <xref:System.ServiceModel.Description.TransactedBatchingBehavior> confirma la transacción.  
>   
>  La opción del tamaño del lote depende de su aplicación. Si el tamaño del lote es demasiado pequeño, puede no obtener el rendimiento deseado. Por otro lado si el tamaño del lote es demasiado grande, puede deteriorar el rendimiento. Por ejemplo, su transacción podría durar mucho más tiempo y realizar bloqueos en su base de datos o su transacción se podría bloquear, lo que podría hacer que el lote se revierta y rehacer el trabajo.  
  
 El cliente crea un ámbito de transacción. La comunicación con la cola tiene lugar dentro del ámbito de la transacción, provocando que se trate como una unidad atómica donde se envían todos los mensajes a la cola o no se envía ninguno. La transacción se confirma llamando a <xref:System.Transactions.TransactionScope.Complete%2A> en el ámbito de la transacción.  

```csharp
//Client implementation code.  
class Client  
{  
    static void Main()  
    {  
        Random randomGen = new Random();  
        for (int i = 0; i < 2500; i++)  
        {  
            // Create a client with given client endpoint configuration.  
            OrderProcessorClient client = new OrderProcessorClient("OrderProcessorEndpoint");  
  
            // Create the purchase order.  
            PurchaseOrder po = new PurchaseOrder();  
            po.CustomerId = "somecustomer" + i + ".com";  
            po.PONumber = Guid.NewGuid().ToString();  
  
            PurchaseOrderLineItem lineItem1 = new PurchaseOrderLineItem();  
            lineItem1.ProductId = "Blue Widget";  
            lineItem1.Quantity = randomGen.Next(1, 100);  
            lineItem1.UnitCost = (float)randomGen.NextDouble() * 10;  
  
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
                // Make a queued call to submit the purchase order.  
                client.SubmitPurchaseOrder(po);  
                // Complete the transaction.  
                scope.Complete();  
            }  
  
            client.Close();  
        }  
        Console.WriteLine();  
        Console.WriteLine("Press <ENTER> to terminate client.");  
        Console.ReadLine();  
    }  
}  
```

 Al ejecutar el ejemplo, las actividades del servicio y del cliente se muestran en las ventanas de la consola del cliente y del servicio. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente. Observe que debido a que se está usando el proceso de poner en cola, el cliente y el servicio no tienen que estar activados y ejecutándose simultáneamente. Puede ejecutar el cliente, cerrarlo e iniciar el servicio y seguir recibiendo mensajes. Puede observar un gran resultado cuando los mensajes se leen en un lote y se procesan.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Updated database with 2 product line items for purchase order 493ac832-d216-4e94-b2a5-d7f492fb5e39  
Processing Purchase Order: 8b567f5b-0661-4662-aae2-6cef1bd6d278  
        Customer: somecustomer849.com  
        OrderDetails  
               Order LineItem: 80 of Blue Widget @unit price: $9.751623  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41622.23  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 41130b95-4ea8-40a9-91c3-2e129117fcb8  
Processing Purchase Order: 5ce2699d-9a31-4cc2-a8c5-64cda614b3c7  
        Customer: somecustomer850.com  
        OrderDetails  
               Order LineItem: 89 of Blue Widget @unit price: $6.369128  
               Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $41408.95  
        Order status: Pending  
  
Updated database with 2 product line items for purchase order 8b567f5b-0661-4662-aae2-6cef1bd6d278  
Processing Purchase Order: ea94486b-7c86-4309-a42d-2f06c00656cd  
        Customer: somecustomer851.com  
        OrderDetails  
             Order LineItem: 47 of Blue Widget @unit price: $0.9391424  
             Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $40886.24  
        Order status: Pending  
```  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Batching`  
  
## <a name="see-also"></a>Vea también
