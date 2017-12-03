---
title: Control de mensajes dudosos en MSMQ 4,0
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec8d59e3-9937-4391-bb8c-fdaaf2cbb73e
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 109b6e8e2bc678aa9f238840b7634bc20a2eb01b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="poison-message-handling-in-msmq-40"></a>Control de mensajes dudosos en MSMQ 4,0
Este ejemplo muestra cómo administrar los mensajes dudosos en un servicio. En este ejemplo se basa en el [transacciones enlace MSMQ](../../../../docs/framework/wcf/samples/transacted-msmq-binding.md) ejemplo. Este ejemplo utiliza `netMsmqBinding`. El servicio es una aplicación de consola autohospedada que le permite observar el servicio que recibe los mensajes en cola.  
  
 En la comunicación con colas, el cliente se comunica con el servicio mediante una cola. Más exactamente, el cliente envía los mensajes a una cola. El servicio recibe los mensajes de la cola. El servicio y el cliente no necesitan ejecutarse simultáneamente para comunicarse mediante una cola.  
  
 Un mensaje dudoso es aquel que se lee repetidamente desde una cola cuando el servicio que lo lee no puede procesarlo y, por consiguiente, termina la transacción en la que se lee el mensaje. En tales casos, se intenta de nuevo leer el mensaje. En teoría, esta acción puede continuar indefinidamente si hay un problema con el mensaje. Observe que esto solo puede ocurrir cuando se usan transacciones para leer desde la cola e invocar la operación del servicio.  
  
 Según la versión de MSMQ, NetMsmqBinding admite la detección limitada para detectar los mensajes dudosos. Una vez detectado el mensaje como dudoso, podrá administrarse de varias maneras. De nuevo, según la versión de MSMQ, NetMsmqBinding admite desde el manejo limitado hasta un manejo completo de mensajes dudosos.  
  
 Este ejemplo muestra los medios limitados para mensajes dudosos que se proporcionan en las plataformas [!INCLUDE[ws2003](../../../../includes/ws2003-md.md)] y [!INCLUDE[wxp](../../../../includes/wxp-md.md)], además de los medios completos proporcionados en [!INCLUDE[wv](../../../../includes/wv-md.md)]. En ambos casos, el objetivo es mover el mensaje dudoso de una cola a otra para que pueda ser reparado por un servicio de mensajes dudosos.  
  
## <a name="msmq-v40-poison-handling-sample"></a>MSMQ v4.0 Ejemplo de Manejo de Mensajes Dudosos  
 En [!INCLUDE[wv](../../../../includes/wv-md.md)], MSMQ proporciona un medio de sub-cola de mensajes dudosos que se puede utilizar para almacenar los mensajes dudosos. Este ejemplo muestra el procedimiento recomendado para tratar con mensajes dudosos utilizando [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 La detección del mensaje dudoso en [!INCLUDE[wv](../../../../includes/wv-md.md)] es bastante sofisticada. Hay 3 propiedades que ayudan con la detección. <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> es el número de veces que un mensaje determinado se relee de la cola y se envía a la aplicación para ser procesado. Un mensaje se relee de la cola cuando se pone de nuevo en la cola porque el mensaje no se puede enviar a la aplicación o la aplicación revierte la transacción en la operación del servicio. <xref:System.ServiceModel.MsmqBindingBase.MaxRetryCycles%2A> es el número de veces que el mensaje se mueve a la cola de reintento. Cuando se localiza <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A>, el mensaje se mueve a la cola de reintento. La propiedad <xref:System.ServiceModel.MsmqBindingBase.RetryCycleDelay%2A> es el retraso tras el que el mensaje se devuelve de la cola de reintento a la cola principal. La propiedad <xref:System.ServiceModel.MsmqBindingBase.ReceiveRetryCount%2A> se restablece en 0. El mensaje se vuelve a intentar. Si se ha producir un error en todos los intentos para leer el mensaje, entonces el mensaje se marca como dudoso.  
  
 Una vez marcado como dudoso, el mensaje se trata según los valores en la enumeración <xref:System.ServiceModel.MsmqBindingBase.ReceiveErrorHandling%2A>. Para reiterar los valores posibles:  
  
-   Fault (valor predeterminado): para indicar que el error está en el agente de escucha y en el host de servicio.  
  
-   Drop: para quitar el mensaje.  
  
-   Move: para mover el mensaje a la subcola de mensajes dudosos. Este valor solo está disponible en [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
-   Reject: para rechazar el mensaje, devolviéndolo a la cola de mensajes con problemas de entrega del remitente. Este valor solo está disponible en [!INCLUDE[wv](../../../../includes/wv-md.md)].  
  
 El ejemplo muestra cómo usar el desecho de `Move` para el mensaje dudoso. `Move` mueve el mensaje a la subcola de mensajes dudosos.  
  
 El contrato de servicio es `IOrderProcessor`, que define un servicio unidireccional que es adecuado para usarse con colas.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IOrderProcessor  
{  
    [OperationContract(IsOneWay = true)]  
    void SubmitPurchaseOrder(PurchaseOrder po);  
}  
```  
  
 La operación de servicio muestra un mensaje que indica que está procesando la orden. Para mostrar la funcionalidad del mensaje dudoso, la operación de servicio `SubmitPurchaseOrder` inicia una excepción para revertir la transacción en una invocación aleatoria del servicio. Esto provoca que el mensaje se vuelva a poner en la cola. Finalmente, el mensaje se marca como dudoso. La configuración se establece para mover el mensaje dudoso a la subcola de mensajes dudosos.  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
public class OrderProcessorService : IOrderProcessor  
{  
    static Random r = new Random(137);  
  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
  
        int randomNumber = r.Next(10);  
  
        if (randomNumber % 2 == 0)  
        {  
            Orders.Add(po);  
            Console.WriteLine("Processing {0} ", po);  
        }  
        else  
        {  
            Console.WriteLine("Aborting transaction, cannot process purchase order: " + po.PONumber);  
            Console.WriteLine();  
            throw new Exception("Cannot process purchase order: " + po.PONumber);  
        }  
    }  
  
    public static void OnServiceFaulted(object sender, EventArgs e)   
    {  
        Console.WriteLine("Service Faulted");  
    }  
  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
        // Get MSMQ queue name from app settings in configuration.  
        string queueName = ConfigurationManager.AppSettings["queueName"];  
  
        // Create the transacted MSMQ queue if necessary.  
        if (!System.Messaging.MessageQueue.Exists(queueName))  
            System.Messaging.MessageQueue.Create(queueName, true);  
  
        // Get the base address that is used to listen for WS-MetaDataExchange requests.  
        // This is useful to generate a proxy for the client.  
        string baseAddress = ConfigurationManager.AppSettings["baseAddress"];  
  
        // Create a ServiceHost for the OrderProcessorService type.  
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService), new Uri(baseAddress));  
  
        // Hook on to the service host faulted events.  
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);  
  
        // Open the ServiceHostBase to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        if(serviceHost.State != CommunicationState.Faulted) {  
            serviceHost.Close();  
        }  
  
    }  
}  
```  
  
 La configuración de servicio incluye las siguientes propiedades de mensaje dudoso: `receiveRetryCount`, `maxRetryCycles`, `retryCycleDelay`, y `receiveErrorHandling` tal y como se muestra en el archivo de configuración siguiente.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <appSettings>  
    <!-- Use appSetting to configure MSMQ queue name. -->  
    <add key="queueName" value=".\private$\ServiceModelSamplesPoison" />  
    <add key="baseAddress" value="http://localhost:8000/orderProcessor/poisonSample"/>  
  </appSettings>  
  <system.serviceModel>  
    <services>  
      <service   
              name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison"  
                  binding="netMsmqBinding"  
                  bindingConfiguration="PoisonBinding"   
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" />  
      </service>  
    </services>  
  
    <bindings>  
      <netMsmqBinding>  
        <binding name="PoisonBinding"   
                 receiveRetryCount="0"  
                 maxRetryCycles="1"  
                 retryCycleDelay="00:00:05"                        
                 receiveErrorHandling="Move">  
        </binding>  
      </netMsmqBinding>  
    </bindings>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="processing-messages-from-the-poison-message-queue"></a>Procesamiento de los mensajes de la cola de mensajes dudosos  
 El servicio de mensajes dudosos lee los mensajes desde la cola de mensajes dudosos final y los procesa.  
  
 Los mensajes en la cola de mensajes dudosos son los que se dirigen al servicio que está procesando el mensaje, que podría ser diferente del extremo de servicio de mensajes dudosos. Por consiguiente, cuando el servicio de mensajes dudosos lee los mensajes de la cola, el nivel de canal de [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] encuentra la desigualdad en los extremos y no envía el mensaje. En este caso, el mensaje se dirige al servicio de procesamiento de pedidos pero está siendo recibido por el servicio de mensajes dudosos. Para continuar recibiendo el mensaje aun cuando se dirige a un extremo diferente, debemos agregar `ServiceBehavior` para filtrar las direcciones en las que el criterio de coincidencia sea coincidir con cualquier extremo de servicio al que se dirija el mensaje. Esto es necesario para procesar correctamente los mensajes que lee desde la cola de mensajes dudosos.  
  
 La propia implementación de servicio de los mensajes dudosos es muy similar a la implementación del servicio. Implementa el contrato y procesa los pedidos. El ejemplo de código es el siguiente.  
  
```  
// Service class that implements the service contract.  
// Added code to write output to the console window.  
[ServiceBehavior(AddressFilterMode=AddressFilterMode.Any)]  
public class OrderProcessorService : IOrderProcessor  
{  
    [OperationBehavior(TransactionScopeRequired = true, TransactionAutoComplete = true)]  
    public void SubmitPurchaseOrder(PurchaseOrder po)  
    {  
        Orders.Add(po);  
        Console.WriteLine("Processing {0} ", po);  
    }  
  
    public static void OnServiceFaulted(object sender, EventArgs e)   
    {  
        Console.WriteLine("Service Faulted...exiting app");  
        Environment.Exit(1);  
    }  
  
    // Host the service within this EXE console application.  
    public static void Main()  
    {  
  
        // Create a ServiceHost for the OrderProcessorService type.  
        ServiceHost serviceHost = new ServiceHost(typeof(OrderProcessorService));  
  
        // Hook on to the service host faulted events.  
        serviceHost.Faulted += new EventHandler(OnServiceFaulted);  
  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The poison message service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
  
        // Close the ServiceHostBase to shutdown the service.  
        if(serviceHost.State != CommunicationState.Faulted)  
        {  
            serviceHost.Close();  
        }  
    }  
```  
  
 A diferencia del servicio de procesamiento de pedidos que lee los mensajes desde la cola de pedidos, el servicio de mensajes dudosos lee los mensajes desde la subcola de mensajes dudosos. La cola de mensajes dudosos es una subcola de la cola principal, se denomina "poison" y MSMQ la genera automáticamente. Para tener acceso a ella, proporcione el nombre de la cola principal seguido de un punto y coma (";") y el nombre de la subcola, en este caso "poison", tal y como se muestra en la configuración del ejemplo siguiente.  
  
> [!NOTE]
>  En el ejemplo para MSMQ v3.0, el nombre de la cola de mensajes dudosos no es ninguna subcola, sino la cola a la que movimos el mensaje.  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.OrderProcessorService">  
        <!-- Define NetMsmqEndpoint -->  
        <endpoint address="net.msmq://localhost/private/ServiceModelSamplesPoison;poison"  
                  binding="netMsmqBinding"  
                  contract="Microsoft.ServiceModel.Samples.IOrderProcessor" >  
        </endpoint>  
      </service>  
    </services>  
  
  </system.serviceModel>  
</configuration>  
```  
  
 Al ejecutar el ejemplo, se muestra el cliente, el servicio y las actividades del servicio de mensajes dudosos en las ventanas de la consola. Puede ver los mensajes recibidos por el servicio desde el cliente. Presione ENTRAR en cada ventana de la consola para cerrar los servicios.  
  
 El servicio empieza ejecutándose, procesando los pedidos y, de forma aleatoria, se inicia para terminar el procesamiento. Si el mensaje indica que ha procesado el pedido, puede ejecutar de nuevo el cliente para enviar otro mensaje hasta que vea que el servicio ha terminado realmente un mensaje. Según los valores configurados para los mensajes dudosos, se intenta una vez el procesamiento del mensaje antes de moverlo a la cola final de mensajes dudosos.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 0f063b71-93e0-42a1-aa3b-bca6c7a89546  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Processing Purchase Order: 5ef9a4fa-5a30-4175-b455-2fb1396095fa  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
  
Aborting transaction, cannot process purchase order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89  
```  
  
 Inicie el servicio de mensajes dudosos para leer el mensaje dudoso de la cola de mensajes dudosos. En este ejemplo, el servicio de mensajes dudosos lee el mensaje y lo procesa. Podría ver que el servicio de mensajes dudosos lee el pedido de compra terminado y dudoso.  
  
```  
The service is ready.  
Press <ENTER> to terminate service.  
  
Processing Purchase Order: 23e0b991-fbf9-4438-a0e2-20adf93a4f89  
        Customer: somecustomer.com  
        OrderDetails  
                Order LineItem: 54 of Blue Widget @unit price: $29.99  
                Order LineItem: 890 of Red Widget @unit price: $45.89  
        Total cost of this order: $42461.56  
        Order status: Pending  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Si se ejecuta el servicio primero, comprobará que la cola esté presente. Si la cola no está presente, el servicio creará una. Puede ejecutar primero el servicio para crear la cola, o puede crear una a través del administrador de cola de MSMQ. Siga estos pasos para crear una cola en Windows 2008.  
  
    1.  Abra el Administrador del servidor en [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].  
  
    2.  Expanda el **características** ficha.  
  
    3.  Haga clic en **cola de mensajes privados**y seleccione **New**, **cola privada**.  
  
    4.  Compruebe el **transaccional** cuadro.  
  
    5.  Escriba `ServiceModelSamplesTransacted` como el nombre de la nueva cola.  
  
3.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
4.  Para ejecutar el ejemplo en una configuración de equipo único o varios, cambie los nombres de cola para reflejar el nombre de host real en lugar de localhost y siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
 De forma predeterminada, con el transporte de enlace `netMsmqBinding`, la seguridad está habilitada. Dos propiedades, `MsmqAuthenticationMode` y `MsmqProtectionLevel`, determinan juntas el tipo de seguridad de transporte. De manera predeterminada, el modo de autenticación está definido en `Windows` y el nivel de protección está definido en `Sign`. Para MSMQ, proporcionar la característica de autenticación y firma, debe formar parte de un dominio. Si ejecuta este ejemplo en un equipo que no forma parte de un dominio, recibirá el error siguiente: "No existe el certificado de Message Queuing interno del usuario".  
  
#### <a name="to-run-the-sample-on-a-computer-joined-to-a-workgroup"></a>Para ejecutar el ejemplo en un equipo unido a un grupo de trabajo  
  
1.  Si su equipo no forma parte de un dominio, desactive la seguridad de transporte estableciendo el modo de autenticación y el nivel de protección en `None`, tal y como se muestra en la configuración de ejemplo siguiente:  
  
    ```xml  
    <bindings>  
        <netMsmqBinding>  
            <binding name="TransactedBinding">  
                <security mode="None"/>  
            </binding>  
        </netMsmqBinding>  
    </bindings>  
    ```  
  
     Asegúrese de que el extremo está asociado al enlace definiendo el atributo bindingConfiguration del extremo.  
  
2.  Asegúrese de que cambia la configuración en PoisonMessageServer, el servidor y el cliente antes de ejecutar el ejemplo.  
  
    > [!NOTE]
    >  Establecer `security mode` en `None` es equivalente a definir la seguridad de `MsmqAuthenticationMode`, `MsmqProtectionLevel` y `Message` en `None`.  
  
3.  Para que el intercambio de metadatos para funcionar, registramos una dirección URL con enlace de http. Esto requiere que el servicio se ejecute en una ventana de comandos elevada. De lo contrario, obtiene una excepción como: Excepción no controlada: System.ServiceModel.AddressAccessDeniedException: HTTP no pudo registrar URL http://+:8000/ServiceModelSamples/service/. Su proceso no tiene los derechos de acceso a este espacio de nombres (vea http://go.microsoft.com/fwlink/? LinkId=70353 para más detalles). ---> System.Net.HttpListenerException: se deniega el acceso.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\Poison\MSMQ4`  
  
## <a name="see-also"></a>Vea también
