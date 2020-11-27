---
title: Stream
ms.date: 03/30/2017
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
ms.openlocfilehash: 04bc5db4172d9052b45f63a2f7ed0fb997dc4c6c
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96257203"
---
# <a name="stream"></a><span data-ttu-id="280d6-102">STREAM</span><span class="sxs-lookup"><span data-stu-id="280d6-102">Stream</span></span>

<span data-ttu-id="280d6-103">El ejemplo de la secuencia muestra el uso de la comunicación de modos de transferencias por secuencia.</span><span class="sxs-lookup"><span data-stu-id="280d6-103">The Stream sample demonstrates the use of streaming transfer mode communication.</span></span> <span data-ttu-id="280d6-104">El servicio expone varias operaciones que envían y reciben secuencias.</span><span class="sxs-lookup"><span data-stu-id="280d6-104">The service exposes several operations that send and receive streams.</span></span> <span data-ttu-id="280d6-105">Este ejemplo se autohospeda.</span><span class="sxs-lookup"><span data-stu-id="280d6-105">This sample is self-hosted.</span></span> <span data-ttu-id="280d6-106">Tanto el cliente como el servicio son los programas de la consola.</span><span class="sxs-lookup"><span data-stu-id="280d6-106">Both the client and service are console programs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="280d6-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="280d6-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="280d6-108">Windows Communication Foundation (WCF) puede comunicarse en dos modos de transferencia: almacenado en búfer o en streaming.</span><span class="sxs-lookup"><span data-stu-id="280d6-108">Windows Communication Foundation (WCF) can communicate in two transfer modes—buffered or streaming.</span></span> <span data-ttu-id="280d6-109">En el modo de transferencia almacenado en búfer (predeterminado), se debe entregar completamente un mensaje para que un receptor pueda leerlo.</span><span class="sxs-lookup"><span data-stu-id="280d6-109">In the default buffered transfer mode, a message must be completely delivered before a receiver can read it.</span></span> <span data-ttu-id="280d6-110">En el modo de transferencia de transmisión por secuencias, el receptor puede empezar a procesar el mensaje antes de se entregue completamente.</span><span class="sxs-lookup"><span data-stu-id="280d6-110">In the streaming transfer mode, the receiver can begin to process the message before it is completely delivered.</span></span> <span data-ttu-id="280d6-111">El modo de transmisión por secuencias es útil cuando la información que se pasa es larga y puede procesarse en serie.</span><span class="sxs-lookup"><span data-stu-id="280d6-111">The streaming mode is useful when the information that is passed is lengthy and can be processed serially.</span></span> <span data-ttu-id="280d6-112">El modo de transmisión por secuencias también es útil cuando el mensaje es demasiado grande para que se almacene en búfer completamente.</span><span class="sxs-lookup"><span data-stu-id="280d6-112">Streaming mode is also useful when the message is too large to be entirely buffered.</span></span>  
  
## <a name="streaming-and-service-contracts"></a><span data-ttu-id="280d6-113">Transmisión por secuencias y contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="280d6-113">Streaming and Service Contracts</span></span>  

 <span data-ttu-id="280d6-114">La transmisión por secuencias es algo a tener en cuenta cuando se diseña un contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="280d6-114">Streaming is something to be considered when designing a service contract.</span></span> <span data-ttu-id="280d6-115">Si una operación recibe o devuelve grandes cantidades de datos, debería considerar transmitir por secuencias estos datos para evitar la utilización de mucha memoria debido al almacenamiento en búfer de mensajes de entrada o de salida.</span><span class="sxs-lookup"><span data-stu-id="280d6-115">If an operation receives or returns large amounts of data, you should consider streaming this data to avoid high memory utilization due to buffering of input or output messages.</span></span> <span data-ttu-id="280d6-116">Para transmitir los en secuencias, el parámetro que contiene los datos deben ser los únicos parámetros del mensaje.</span><span class="sxs-lookup"><span data-stu-id="280d6-116">To stream data, the parameter that holds that data must be the only parameter in the message.</span></span> <span data-ttu-id="280d6-117">Por ejemplo, si el mensaje de entrada es el que se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de entrada.</span><span class="sxs-lookup"><span data-stu-id="280d6-117">For example, if the input message is the one to be streamed, the operation must have exactly one input parameter.</span></span> <span data-ttu-id="280d6-118">De igual forma, si el mensaje de salida se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de salida o un valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="280d6-118">Similarly, if the output message is to be streamed, the operation must have either exactly one output parameter or a return value.</span></span> <span data-ttu-id="280d6-119">En cualquier caso, el tipo de valor de parámetro o devuelvo debe ser `Stream`, `Message` o `IXmlSerializable`.</span><span class="sxs-lookup"><span data-stu-id="280d6-119">In either case, the parameter or return value type must be either `Stream`, `Message`, or `IXmlSerializable`.</span></span> <span data-ttu-id="280d6-120">A continuación se muestra el contrato de servicio utilizado en este ejemplo de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="280d6-120">The following is the service contract used in this streaming sample.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface IStreamingSample  
{  
    [OperationContract]  
    Stream GetStream(string data);  
    [OperationContract]  
    bool UploadStream(Stream stream);  
    [OperationContract]  
    Stream EchoStream(Stream stream);  
    [OperationContract]  
    Stream GetReversedStream();  
  
}  
```  
  
 <span data-ttu-id="280d6-121">La operación `GetStream` recibe algunos datos de entrada como una cadena, que está almacenada en búfer, y devuelve `Stream`, que se transmite por secuencia.</span><span class="sxs-lookup"><span data-stu-id="280d6-121">The `GetStream` operation receives some input data as a string, which is buffered, and returns a `Stream`, which is streamed.</span></span> <span data-ttu-id="280d6-122">A la inversa, `UploadStream` admite una `Stream` (transmitida por secuencias) y devuelve un `bool` (almacenado en búfer).</span><span class="sxs-lookup"><span data-stu-id="280d6-122">Conversely, `UploadStream` takes in a `Stream` (streamed) and returns a `bool` (buffered).</span></span> <span data-ttu-id="280d6-123">`EchoStream` toma y devuelve `Stream` y es un ejemplo de una operación cuyos mensajes de entrada y salida se transmiten por secuencias.</span><span class="sxs-lookup"><span data-stu-id="280d6-123">`EchoStream` takes and returns `Stream` and is an example of an operation whose input and output messages are both streamed.</span></span> <span data-ttu-id="280d6-124">Finalmente, `GetReversedStream` no toma ninguna entrada y devuelve un `Stream` (transmitido por secuencia).</span><span class="sxs-lookup"><span data-stu-id="280d6-124">Finally, `GetReversedStream` takes no inputs and returns a `Stream` (streamed).</span></span>  
  
## <a name="enabling-streamed-transfers"></a><span data-ttu-id="280d6-125">Habilitación de transferencias por secuencias</span><span class="sxs-lookup"><span data-stu-id="280d6-125">Enabling Streamed Transfers</span></span>  

 <span data-ttu-id="280d6-126">Definir los contratos de operación tal y como se han descrito anteriormente proporciona una transmisión por secuencias en el nivel de modelo de programación.</span><span class="sxs-lookup"><span data-stu-id="280d6-126">Defining operation contracts as previously described provides streaming at the programming model level.</span></span> <span data-ttu-id="280d6-127">Si se detiene allí, el transporte todavía almacena en búfer el contenido completo del mensaje.</span><span class="sxs-lookup"><span data-stu-id="280d6-127">If you stop there, the transport still buffers the entire message content.</span></span> <span data-ttu-id="280d6-128">Para habilitar la transmisión por secuencias de transporte, seleccione un modo de transferencia en el elemento de enlace del transporte.</span><span class="sxs-lookup"><span data-stu-id="280d6-128">To enable transport streaming, select a transfer mode on the binding element of the transport.</span></span> <span data-ttu-id="280d6-129">El elemento de enlace tiene una propiedad `TransferMode` que puede establecerse en `Buffered`, `Streamed`, `StreamedRequest`o `StreamedResponse`.</span><span class="sxs-lookup"><span data-stu-id="280d6-129">The binding element has a `TransferMode` property that can be set to `Buffered`, `Streamed`, `StreamedRequest`, or `StreamedResponse`.</span></span> <span data-ttu-id="280d6-130">Establecer el modo de transferencia en `Streamed` habilita la comunicación de transmisión por secuencias en ambas direcciones.</span><span class="sxs-lookup"><span data-stu-id="280d6-130">Setting the transfer mode to `Streamed` enables streaming communication in both directions.</span></span> <span data-ttu-id="280d6-131">Establecer el modo de transferencia en `StreamedRequest` o `StreamedResponse` habilita la comunicación de transmisión por secuencias en la solicitud o la respuesta, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="280d6-131">Setting the transfer mode to `StreamedRequest` or `StreamedResponse` enables streaming communication in only the request or response, respectively.</span></span>  
  
 <span data-ttu-id="280d6-132">`basicHttpBinding` expone la propiedad `TransferMode` en el enlace tal y como hace `NetTcpBinding` y `NetNamedPipeBinding`.</span><span class="sxs-lookup"><span data-stu-id="280d6-132">The `basicHttpBinding` exposes the `TransferMode` property on the binding as does `NetTcpBinding` and `NetNamedPipeBinding`.</span></span> <span data-ttu-id="280d6-133">Para otros transportes, debe crear un enlace personalizado para establecer el modo de transferencia.</span><span class="sxs-lookup"><span data-stu-id="280d6-133">For other transports, you must create a custom binding to set the transfer mode.</span></span>  
  
 <span data-ttu-id="280d6-134">El código de configuración siguiente del ejemplo muestra cómo establecer la propiedad `TransferMode` en la transmisión por secuencias en `basicHttpBinding` y un enlace HTTP personalizado:</span><span class="sxs-lookup"><span data-stu-id="280d6-134">The following configuration code from the sample shows setting the `TransferMode` property to streaming on the `basicHttpBinding` and a custom HTTP binding:</span></span>  
  
```xml  
<!-- An example basicHttpBinding using streaming. -->  
<basicHttpBinding>  
  <binding name="HttpStreaming" maxReceivedMessageSize="67108864"  
           transferMode="Streamed"/>  
</basicHttpBinding>  
<!-- An example customBinding using HTTP and streaming.-->  
<customBinding>  
  <binding name="Soap12">  
    <textMessageEncoding messageVersion="Soap12WSAddressing10" />  
    <httpTransport transferMode="Streamed"  
                   maxReceivedMessageSize="67108864"/>  
  </binding>  
</customBinding>  
```  
  
 <span data-ttu-id="280d6-135">Además de establecer `transferMode` en `Streamed`, el código de configuración anterior establece `maxReceivedMessageSize` en 64 MB.</span><span class="sxs-lookup"><span data-stu-id="280d6-135">In addition to setting the `transferMode` to `Streamed`, the previous configuration code sets the `maxReceivedMessageSize` to 64MB.</span></span> <span data-ttu-id="280d6-136">Como un mecanismo de la defensa, `maxReceivedMessageSize` establece un límite en el tamaño máximo permitido de los mensajes que se reciben.</span><span class="sxs-lookup"><span data-stu-id="280d6-136">As a defense mechanism, `maxReceivedMessageSize` places a cap on the maximum allowable size of messages on receive.</span></span> <span data-ttu-id="280d6-137">El `maxReceivedMessageSize` predeterminado es de 64 KB, que normalmente es demasiado pequeño para los escenarios de transmisión por secuencias.</span><span class="sxs-lookup"><span data-stu-id="280d6-137">The default `maxReceivedMessageSize` is 64 KB, which is usually too low for streaming scenarios.</span></span>  
  
## <a name="processing-data-as-it-is-streamed"></a><span data-ttu-id="280d6-138">Procesamiento de datos cuando se transmiten por secuencias</span><span class="sxs-lookup"><span data-stu-id="280d6-138">Processing Data As It Is Streamed</span></span>  

 <span data-ttu-id="280d6-139">Las operaciones `GetStream`, `UploadStream` y `EchoStream` tratan sobre enviar datos directamente desde un archivo o sobre guardar los datos recibidos directamente en un archivo.</span><span class="sxs-lookup"><span data-stu-id="280d6-139">The operations `GetStream`, `UploadStream` and `EchoStream` all deal with sending data directly from a file or saving received data directly to a file.</span></span> <span data-ttu-id="280d6-140">Sin embargo, en algunos casos, hay un requisito para enviar o recibir grandes cantidades de datos y realizar el procesamiento en fragmentos de datos cuando se envían o se reciben.</span><span class="sxs-lookup"><span data-stu-id="280d6-140">However in some cases, there is a requirement to send or receive large amounts of data and perform some processing on chunks of the data as it is being sent or received.</span></span> <span data-ttu-id="280d6-141">Una manera de resolver tales escenarios es escribir una secuencia personalizada (una clase que deriva de <xref:System.IO.Stream>) que procesa los datos cuando se leen o se escriben.</span><span class="sxs-lookup"><span data-stu-id="280d6-141">One way to address such scenarios is to write a custom stream (a class that derives from <xref:System.IO.Stream>) that processes data as it is read or written.</span></span> <span data-ttu-id="280d6-142">La operación `GetReversedStream` y la clase `ReverseStream` son un ejemplo de esto.</span><span class="sxs-lookup"><span data-stu-id="280d6-142">The `GetReversedStream` operation and `ReverseStream` class are an example of this.</span></span>  
  
 <span data-ttu-id="280d6-143">`GetReversedStream` crea y devuelve una nueva instancia de `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="280d6-143">`GetReversedStream` creates and returns a new instance of `ReverseStream`.</span></span> <span data-ttu-id="280d6-144">El procesamiento real se produce cuando el sistema lee desde ese objeto `ReverseStream`.</span><span class="sxs-lookup"><span data-stu-id="280d6-144">The actual processing happens as the system reads from that `ReverseStream` object.</span></span> <span data-ttu-id="280d6-145">La implementación `ReverseStream.Read` lee un fragmento de bytes del archivo subyacente, los invierte y después devuelve los bytes invertidos.</span><span class="sxs-lookup"><span data-stu-id="280d6-145">The `ReverseStream.Read` implementation reads a chunk of bytes from the underlying file, reverses them, then returns the reversed bytes.</span></span> <span data-ttu-id="280d6-146">Esto no invierte el contenido del archivo completo, sino un fragmento de bytes cada vez.</span><span class="sxs-lookup"><span data-stu-id="280d6-146">This does not reverse the entire file content; it reverses one chunk of bytes at a time.</span></span> <span data-ttu-id="280d6-147">Se trata de un ejemplo para mostrar cómo puede realizar el procesamiento de la secuencia cuando el contenido se lee o escribe desde la secuencia y hacia ella.</span><span class="sxs-lookup"><span data-stu-id="280d6-147">This is an example to show how you can perform stream processing as the content is being read or written from and to the stream.</span></span>  
  
```csharp
class ReverseStream : Stream  
{  
  
    FileStream inStream;  
    internal ReverseStream(string filePath)  
    {  
        //Opens the file and places a StreamReader around it.  
        inStream = File.OpenRead(filePath);  
    }  
  
    // Other methods removed for brevity.  
  
    public override int Read(byte[] buffer, int offset, int count)  
    {  
        int countRead=inStream.Read(buffer, offset,count);  
        ReverseBuffer(buffer, offset, countRead);  
        return countRead;  
    }  
  
    public override void Close()  
    {  
        inStream.Close();  
        base.Close();  
    }  
    protected override void Dispose(bool disposing)  
    {  
        inStream.Dispose();  
        base.Dispose(disposing);  
    }  
    void ReverseBuffer(byte[] buffer, int offset, int count)  
    {  
        int i, j;  
        for (i = offset, j = offset + count - 1; i < j; i++, j--)  
        {  
            byte currenti = buffer[i];  
            buffer[i] = buffer[j];  
            buffer[j] = currenti;  
        }  
  
    }  
}  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="280d6-148">Ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="280d6-148">Running the Sample</span></span>  

 <span data-ttu-id="280d6-149">Para ejecutar el ejemplo, primero compile el servicio y el cliente siguiendo las directrices al final de este documento.</span><span class="sxs-lookup"><span data-stu-id="280d6-149">To run the sample, first build both the service and the client by following the directions at the end of this document.</span></span> <span data-ttu-id="280d6-150">A continuación, inicie el servicio y el cliente en dos ventanas de la consola diferentes.</span><span class="sxs-lookup"><span data-stu-id="280d6-150">Then start the service and the client in two different console windows.</span></span> <span data-ttu-id="280d6-151">Cuando el cliente se inicia, espera a que presione ENTRAR cuando el servicio está listo.</span><span class="sxs-lookup"><span data-stu-id="280d6-151">When the client starts, it waits for you to press ENTER when the service is ready.</span></span> <span data-ttu-id="280d6-152">Después el cliente llama a los métodos `GetStream()`, `UploadStream()` y `GetReversedStream()` primero sobre HTTP y después sobre TCP.</span><span class="sxs-lookup"><span data-stu-id="280d6-152">The client then calls the methods `GetStream()`, `UploadStream()` and `GetReversedStream()` first over HTTP and then over TCP.</span></span> <span data-ttu-id="280d6-153">A continuación, se muestra un resultado del ejemplo desde el servicio seguido de uno desde el cliente:</span><span class="sxs-lookup"><span data-stu-id="280d6-153">Here is an example output from the service followed by example output from the client:</span></span>  
  
 <span data-ttu-id="280d6-154">Resultado del servicio:</span><span class="sxs-lookup"><span data-stu-id="280d6-154">Service Output:</span></span>  
  
```console  
The streaming service is ready.  
Press <ENTER> to terminate service.  
  
Saving to file D:\...\uploadedfile  
......................  
File D:\...\uploadedfile saved  
Saving to file D:\...\uploadedfile  
...............  
File D:\...\uploadedfile saved  
```  
  
 <span data-ttu-id="280d6-155">Resultado del cliente:</span><span class="sxs-lookup"><span data-stu-id="280d6-155">Client Output:</span></span>  
  
```console  
Press <ENTER> when service is ready  
------ Using HTTP ------
Calling GetStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
......................  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
------ Using Custom HTTP ------  
Calling GetStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
Calling UploadStream()  
Calling GetReversedStream()  
Saving to file D:\...\clientfile  
...............  
Wrote 33405 bytes to stream  
  
File D:\...\clientfile saved  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="280d6-156">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="280d6-156">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="280d6-157">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="280d6-157">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="280d6-158">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="280d6-158">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="280d6-159">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="280d6-159">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="280d6-160">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="280d6-160">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="280d6-161">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="280d6-161">The samples may already be installed on your machine.</span></span> <span data-ttu-id="280d6-162">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="280d6-162">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="280d6-163">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="280d6-163">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="280d6-164">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="280d6-164">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
