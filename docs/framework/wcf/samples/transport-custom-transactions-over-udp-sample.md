---
title: 'Transporte: transacciones personalizadas sobre ejemplo UDP'
ms.date: 03/30/2017
ms.assetid: 6cebf975-41bd-443e-9540-fd2463c3eb23
ms.openlocfilehash: 09ce715da4cf4d4fb4c959f63af3bb2c8c68b841
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74712003"
---
# <a name="transport-custom-transactions-over-udp-sample"></a><span data-ttu-id="41a00-102">Transporte: transacciones personalizadas sobre ejemplo UDP</span><span class="sxs-lookup"><span data-stu-id="41a00-102">Transport: Custom Transactions over UDP Sample</span></span>
<span data-ttu-id="41a00-103">Este ejemplo se basa en el ejemplo [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) en la[extensibilidad de transporte](../../../../docs/framework/wcf/samples/transport-extensibility.md)Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="41a00-103">This sample is based on the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample in the Windows Communication Foundation (WCF)[Transport Extensibility](../../../../docs/framework/wcf/samples/transport-extensibility.md).</span></span> <span data-ttu-id="41a00-104">Extiende el ejemplo de transporte UDP para admitir el flujo de transacciones personalizado y muestra el uso de la propiedad <xref:System.ServiceModel.Channels.TransactionMessageProperty>.</span><span class="sxs-lookup"><span data-stu-id="41a00-104">It extends the UDP Transport sample to support custom transaction flow and demonstrates the use of the <xref:System.ServiceModel.Channels.TransactionMessageProperty> property.</span></span>  
  
## <a name="code-changes-in-the-udp-transport-sample"></a><span data-ttu-id="41a00-105">Cambios de código en el ejemplo de transporte de UDP</span><span class="sxs-lookup"><span data-stu-id="41a00-105">Code Changes in the UDP Transport Sample</span></span>  
 <span data-ttu-id="41a00-106">Para mostrar el flujo de transacciones, el ejemplo cambia el contrato de servicio para `ICalculatorContract` con objeto de exigir un ámbito de transacción para `CalculatorService.Add()`.</span><span class="sxs-lookup"><span data-stu-id="41a00-106">To demonstrate transaction flow, the sample changes the service contract for `ICalculatorContract` to require a transaction scope for `CalculatorService.Add()`.</span></span> <span data-ttu-id="41a00-107">El ejemplo también agrega un parámetro `System.Guid` adicional al contrato de la operación `Add`.</span><span class="sxs-lookup"><span data-stu-id="41a00-107">The sample also adds an extra `System.Guid` parameter to the contract of the `Add` operation.</span></span> <span data-ttu-id="41a00-108">Este parámetro se utiliza para pasar el identificador de la transacción del cliente al servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-108">This parameter is used to pass the identifier of the client transaction to the service.</span></span>  
  
```csharp  
class CalculatorService : IDatagramContract, ICalculatorContract  
{  
    [OperationBehavior(TransactionScopeRequired=true)]  
    public int Add(int x, int y, Guid clientTransactionId)  
    {  
        if(Transaction.Current.TransactionInformation.DistributedIdentifier == clientTransactionId)  
    {  
        Console.WriteLine("The client transaction has flowed to the service");  
    }  
    else  
    {  
     Console.WriteLine("The client transaction has NOT flowed to the service");  
    }  
  
    Console.WriteLine("   adding {0} + {1}", x, y);              
    return (x + y);  
    }  
  
    [...]  
}  
```  
  
 <span data-ttu-id="41a00-109">El ejemplo [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) usa paquetes UDP para pasar mensajes entre un cliente y un servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-109">The [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample uses UDP packets to pass messages between a client and a service.</span></span> <span data-ttu-id="41a00-110">El [ejemplo Transport: Custom Transport](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) usa el mismo mecanismo para transportar mensajes, pero cuando se transmite una transacción, se inserta en el paquete UDP junto con el mensaje codificado.</span><span class="sxs-lookup"><span data-stu-id="41a00-110">The [Transport: Custom Transport Sample](../../../../docs/framework/wcf/samples/transport-custom-transactions-over-udp-sample.md) uses the same mechanism to transport messages, but when a transaction is flowed, it is inserted into the UDP packet along with the encoded message.</span></span>  
  
```csharp  
byte[] txmsgBuffer = TransactionMessageBuffer.WriteTransactionMessageBuffer(txPropToken, messageBuffer);  
  
int bytesSent = this.socket.SendTo(txmsgBuffer, 0, txmsgBuffer.Length, SocketFlags.None, this.remoteEndPoint);  
```  
  
 <span data-ttu-id="41a00-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` es un método del asistente que contiene la nueva funcionalidad para combinar el token de propagación para la transacción actual con la entidad del mensaje y lo coloca en un búfer.</span><span class="sxs-lookup"><span data-stu-id="41a00-111">`TransactionMessageBuffer.WriteTransactionMessageBuffer` is a helper method that contains new functionality to merge the propagation token for the current transaction with the message entity and place it into a buffer.</span></span>  
  
 <span data-ttu-id="41a00-112">Para el transporte de flujo de transacciones personalizado, la implementación del cliente debe saber qué operaciones de servicio requieren el flujo de la transacción y pasar esta información a WCF.</span><span class="sxs-lookup"><span data-stu-id="41a00-112">For custom transaction flow transport, the client implementation must know what service operations require transaction flow and to pass this information to WCF.</span></span> <span data-ttu-id="41a00-113">Debería haber también un mecanismo para transmitir la transacción del usuario en el nivel de transporte.</span><span class="sxs-lookup"><span data-stu-id="41a00-113">There should also be a mechanism for transmitting the user transaction to the transport layer.</span></span> <span data-ttu-id="41a00-114">Este ejemplo utiliza "inspectores de mensajes de WCF" para obtener esta información.</span><span class="sxs-lookup"><span data-stu-id="41a00-114">This sample uses "WCF message inspectors" to obtain this information.</span></span> <span data-ttu-id="41a00-115">El inspector de mensaje de cliente implementado aquí, que se denomina `TransactionFlowInspector`, realiza las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="41a00-115">The client message inspector implemented here, which is called `TransactionFlowInspector`, performs the following tasks:</span></span>  
  
- <span data-ttu-id="41a00-116">Determina si se debe hacer fluir una transacción o no para una acción de mensaje determinada (esto tiene lugar en `IsTxFlowRequiredForThisOperation()`).</span><span class="sxs-lookup"><span data-stu-id="41a00-116">Determines whether a transaction must be flowed for a given message action (this takes place in `IsTxFlowRequiredForThisOperation()`).</span></span>  
  
- <span data-ttu-id="41a00-117">Asocia la transacción de ambiente actual con el mensaje utilizando `TransactionFlowProperty`, si es necesario hacer fluir una transacción (esto se hace en `BeforeSendRequest()`).</span><span class="sxs-lookup"><span data-stu-id="41a00-117">Attaches the current ambient transaction to the message using `TransactionFlowProperty`, if a transaction is required to be flowed (this is done in `BeforeSendRequest()`).</span></span>  
  
```csharp  
public class TransactionFlowInspector : IClientMessageInspector  
{  
   void IClientMessageInspector.AfterReceiveReply(ref           System.ServiceModel.Channels.Message reply, object correlationState)  
  {  
  }  
  
   public object BeforeSendRequest(ref System.ServiceModel.Channels.Message request, System.ServiceModel.IClientChannel channel)  
   {  
       // obtain the tx propagation token  
       byte[] propToken = null;             
       if (Transaction.Current != null && IsTxFlowRequiredForThisOperation(request.Headers.Action))  
       {  
           try  
           {  
               propToken = TransactionInterop.GetTransmitterPropagationToken(Transaction.Current);  
           }  
           catch (TransactionException e)  
           {  
              throw new CommunicationException("TransactionInterop.GetTransmitterPropagationToken failed.", e);  
           }  
       }  
  
      // set the propToken on the message in a TransactionFlowProperty  
       TransactionFlowProperty.Set(propToken, request);  
  
       return null;              
    }  
  }  
  
  static bool IsTxFlowRequiredForThisOperation(String action)  
 {  
       // In general, this should contain logic to identify which operations (actions)      require transaction flow.  
      [...]  
 }  
}  
```  
  
 <span data-ttu-id="41a00-118">El `TransactionFlowInspector` se pasa al marco utilizando un comportamiento personalizado: `TransactionFlowBehavior`.</span><span class="sxs-lookup"><span data-stu-id="41a00-118">The `TransactionFlowInspector` itself is passed to the framework using a custom behavior: the `TransactionFlowBehavior`.</span></span>  
  
```csharp  
public class TransactionFlowBehavior : IEndpointBehavior  
{  
       public void AddBindingParameters(ServiceEndpoint endpoint,            System.ServiceModel.Channels.BindingParameterCollection bindingParameters)  
      {  
      }  
  
       public void ApplyClientBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.ClientRuntime clientRuntime)  
      {  
            TransactionFlowInspector inspector = new TransactionFlowInspector();  
            clientRuntime.MessageInspectors.Add(inspector);  
      }  
  
      public void ApplyDispatchBehavior(ServiceEndpoint endpoint, System.ServiceModel.Dispatcher.EndpointDispatcher endpointDispatcher)  
     {  
     }  
  
      public void Validate(ServiceEndpoint endpoint)  
      {  
      }  
}  
```  
  
 <span data-ttu-id="41a00-119">Con el mecanismo anterior en su lugar, el código de usuario crea `TransactionScope` antes de llamar a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-119">With the preceding mechanism in place, the user code creates a `TransactionScope` before calling the service operation.</span></span> <span data-ttu-id="41a00-120">El inspector del mensaje garantiza que la transacción se pasa al transporte en caso de que sea necesaria para que fluya a la operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-120">The message inspector ensures that the transaction is passed to the transport in case it is required to be flowed to the service operation.</span></span>  
  
```csharp  
CalculatorContractClient calculatorClient = new CalculatorContractClient("SampleProfileUdpBinding_ICalculatorContract");  
calculatorClient.Endpoint.Behaviors.Add(new TransactionFlowBehavior());               
  
try  
{  
       for (int i = 0; i < 5; ++i)  
      {  
              // call the 'Add' service operation under a transaction scope  
             using (TransactionScope ts = new TransactionScope())  
             {  
        [...]  
        Console.WriteLine(calculatorClient.Add(i, i * 2));  
         }  
      }               
       calculatorClient.Close();  
}  
catch (TimeoutException)  
{  
    calculatorClient.Abort();  
}  
catch (CommunicationException)  
{  
    calculatorClient.Abort();  
}  
catch (Exception)  
{  
    calculatorClient.Abort();  
    throw;  
}  
```  
  
 <span data-ttu-id="41a00-121">Al recibir un paquete UDP del cliente, el servicio lo deserializa para extraer el mensaje y posiblemente una transacción.</span><span class="sxs-lookup"><span data-stu-id="41a00-121">Upon receiving a UDP packet from the client, the service deserializes it to extract the message and possibly a transaction.</span></span>  
  
```csharp  
count = listenSocket.EndReceiveFrom(result, ref dummy);  
  
// read the transaction and message                       TransactionMessageBuffer.ReadTransactionMessageBuffer(buffer, count, out transaction, out msg);  
```  
  
 <span data-ttu-id="41a00-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` es el método del asistente que invierte el proceso de serialización realizado por `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span><span class="sxs-lookup"><span data-stu-id="41a00-122">`TransactionMessageBuffer.ReadTransactionMessageBuffer()` is the helper method that reverses the serialization process performed by `TransactionMessageBuffer.WriteTransactionMessageBuffer()`.</span></span>  
  
 <span data-ttu-id="41a00-123">Si se fluye una transacción, se anexa al mensaje en `TransactionMessageProperty`.</span><span class="sxs-lookup"><span data-stu-id="41a00-123">If a transaction was flowed in, it is appended to the message in the `TransactionMessageProperty`.</span></span>  
  
```csharp  
message = MessageEncoderFactory.Encoder.ReadMessage(msg, bufferManager);  
  
if (transaction != null)  
{  
       TransactionMessageProperty.Set(transaction, message);  
}  
```  
  
 <span data-ttu-id="41a00-124">Esto garantiza que el distribuidor escoja la transacción en el momento de la distribución y lo utilice al llamar a la operación de servicio dirigida por el mensaje.</span><span class="sxs-lookup"><span data-stu-id="41a00-124">This ensures that the dispatcher picks up the transaction at dispatch time and uses it when calling the service operation addressed by the message.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="41a00-125">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="41a00-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="41a00-126">Para compilar la solución, siga las instrucciones de [creación de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="41a00-126">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="41a00-127">El ejemplo actual se debe ejecutar de forma similar al ejemplo [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) .</span><span class="sxs-lookup"><span data-stu-id="41a00-127">The current sample should be run similarly to the [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md) sample.</span></span> <span data-ttu-id="41a00-128">Para ejecutarlo, inicie el servicio con UdpTestService.exe.</span><span class="sxs-lookup"><span data-stu-id="41a00-128">To run it, start the service with UdpTestService.exe.</span></span> <span data-ttu-id="41a00-129">Si está ejecutando [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], debe iniciar el servicio con privilegios elevados.</span><span class="sxs-lookup"><span data-stu-id="41a00-129">If you are running [!INCLUDE[windowsver](../../../../includes/windowsver-md.md)], you must start the service with elevated privileges.</span></span> <span data-ttu-id="41a00-130">Para ello, haga clic con el botón secundario en UdpTestService. exe en el explorador de archivos y haga clic en **Ejecutar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="41a00-130">To do so, right-click UdpTestService.exe in File Explorer and click **Run as administrator**.</span></span>  
  
3. <span data-ttu-id="41a00-131">Esto produce el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="41a00-131">This produces the following output.</span></span>  
  
    ```console  
    Testing Udp From Code.  
    Service is started from code...  
    Press <ENTER> to terminate the service and start service from config...  
    ```  
  
4. <span data-ttu-id="41a00-132">En este momento puede iniciar el cliente ejecutando UdpTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="41a00-132">At this time, you can start the client by running UdpTestClient.exe.</span></span> <span data-ttu-id="41a00-133">El resultado producido por el cliente es el siguiente.</span><span class="sxs-lookup"><span data-stu-id="41a00-133">The output produced by the client is as follows.</span></span>  
  
    ```console 
    0  
    3  
    6  
    9  
    12  
    Press <ENTER> to complete test.  
    ```  
  
5. <span data-ttu-id="41a00-134">El resultado del servicio es como sigue.</span><span class="sxs-lookup"><span data-stu-id="41a00-134">The service output is as follows.</span></span>  
  
    ```console 
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    Hello, world!  
    The client transaction has flowed to the service  
       adding 0 + 0  
    The client transaction has flowed to the service  
       adding 1 + 2  
    The client transaction has flowed to the service  
       adding 2 + 4  
    The client transaction has flowed to the service  
       adding 3 + 6  
    The client transaction has flowed to the service  
       adding 4 + 8  
    ```  
  
6. <span data-ttu-id="41a00-135">La aplicación de servicio muestra `The client transaction has flowed to the service` del mensaje si puede coincidir con el identificador de la transacción enviado por el cliente, en el parámetro `clientTransactionId` de la operación `CalculatorService.Add()`, con el identificador de la transacción del servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-135">The service application displays the message `The client transaction has flowed to the service` if it can match the transaction identifier sent by the client, in the `clientTransactionId` parameter of the `CalculatorService.Add()` operation, to the identifier of the service transaction.</span></span> <span data-ttu-id="41a00-136">Se obtiene una coincidencia solo si la transacción del cliente ha fluido hacia el servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-136">A match is obtained only if the client transaction has flowed to the service.</span></span>  
  
7. <span data-ttu-id="41a00-137">Para ejecutar la aplicación cliente en los puntos de conexión publicados utilizando la configuración, presione Entrar en la ventana de la aplicación de servicio y después ejecute de nuevo el cliente de pruebas.</span><span class="sxs-lookup"><span data-stu-id="41a00-137">To run the client application against endpoints published using configuration, press ENTER on the service application window and then run the test client again.</span></span> <span data-ttu-id="41a00-138">Debería ver el siguiente resultado en el servicio.</span><span class="sxs-lookup"><span data-stu-id="41a00-138">You should see the following output on the service.</span></span>  
  
    ```console  
    Testing Udp From Config.  
    Service is started from config...  
    Press <ENTER> to terminate the service and exit...  
    ```  
  
8. <span data-ttu-id="41a00-139">Ejecutar el cliente con el servicio genera ahora un resultado similar al anterior.</span><span class="sxs-lookup"><span data-stu-id="41a00-139">Running the client against the service now produces similar output as before.</span></span>  
  
9. <span data-ttu-id="41a00-140">Para regenerar el código de cliente y la configuración utilizando Svcutil.exe, inicie la aplicación de servicio y, a continuación, ejecute el comando Svcutil.exe siguiente desde el directorio raíz del ejemplo.</span><span class="sxs-lookup"><span data-stu-id="41a00-140">To regenerate the client code and configuration using Svcutil.exe, start the service application and then run the following Svcutil.exe command from the root directory of the sample.</span></span>  
  
    ```console  
    svcutil http://localhost:8000/udpsample/ /reference:UdpTransport\bin\UdpTransport.dll /svcutilConfig:svcutil.exe.config  
    ```  
  
10. <span data-ttu-id="41a00-141">Observe que Svcutil.exe no genera la configuración de la extensión de enlace `sampleProfileUdpBinding`; debe agregarla manualmente.</span><span class="sxs-lookup"><span data-stu-id="41a00-141">Note that Svcutil.exe does not generate the binding extension configuration for the `sampleProfileUdpBinding`; you must add it manually.</span></span>  
  
    ```xml  
    <configuration>  
        <system.serviceModel>      
            …  
            <extensions>  
                <!-- This was added manually because svcutil.exe does not add this extension to the file -->  
                <bindingExtensions>  
                    <add name="sampleProfileUdpBinding" type="Microsoft.ServiceModel.Samples.SampleProfileUdpBindingCollectionElement, UdpTransport" />  
                </bindingExtensions>  
            </extensions>  
        </system.serviceModel>  
    </configuration>  
    ```  
  
> [!IMPORTANT]
> <span data-ttu-id="41a00-142">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="41a00-142">The samples may already be installed on your machine.</span></span> <span data-ttu-id="41a00-143">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="41a00-143">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="41a00-144">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="41a00-144">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="41a00-145">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="41a00-145">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Transactions\TransactionMessagePropertyUDPTransport`  
  
## <a name="see-also"></a><span data-ttu-id="41a00-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="41a00-146">See also</span></span>

- [<span data-ttu-id="41a00-147">Transporte: UDP</span><span class="sxs-lookup"><span data-stu-id="41a00-147">Transport: UDP</span></span>](../../../../docs/framework/wcf/samples/transport-udp.md)
