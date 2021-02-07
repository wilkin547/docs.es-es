---
description: 'Más información sobre: Stream'
title: STREAM
ms.date: 03/30/2017
ms.assetid: 58a3db81-20ab-4627-bf31-39d30b70b4fe
ms.openlocfilehash: ea0759f9eca2a974f77e8a6b059160b9a45bd94e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99668856"
---
# <a name="stream"></a>STREAM

El ejemplo de la secuencia muestra el uso de la comunicación de modos de transferencias por secuencia. El servicio expone varias operaciones que envían y reciben secuencias. Este ejemplo se autohospeda. Tanto el cliente como el servicio son los programas de la consola.  
  
> [!NOTE]
> El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Windows Communication Foundation (WCF) puede comunicarse en dos modos de transferencia: almacenado en búfer o en streaming. En el modo de transferencia almacenado en búfer (predeterminado), se debe entregar completamente un mensaje para que un receptor pueda leerlo. En el modo de transferencia de transmisión por secuencias, el receptor puede empezar a procesar el mensaje antes de se entregue completamente. El modo de transmisión por secuencias es útil cuando la información que se pasa es larga y puede procesarse en serie. El modo de transmisión por secuencias también es útil cuando el mensaje es demasiado grande para que se almacene en búfer completamente.  
  
## <a name="streaming-and-service-contracts"></a>Transmisión por secuencias y contratos de servicio  

 La transmisión por secuencias es algo a tener en cuenta cuando se diseña un contrato de servicio. Si una operación recibe o devuelve grandes cantidades de datos, debería considerar transmitir por secuencias estos datos para evitar la utilización de mucha memoria debido al almacenamiento en búfer de mensajes de entrada o de salida. Para transmitir los en secuencias, el parámetro que contiene los datos deben ser los únicos parámetros del mensaje. Por ejemplo, si el mensaje de entrada es el que se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de entrada. De igual forma, si el mensaje de salida se va a transmitir por secuencia, la operación debe tener exactamente un parámetro de salida o un valor devuelto. En cualquier caso, el tipo de valor de parámetro o devuelvo debe ser `Stream`, `Message` o `IXmlSerializable`. A continuación se muestra el contrato de servicio utilizado en este ejemplo de transmisión por secuencias.  
  
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
  
 La operación `GetStream` recibe algunos datos de entrada como una cadena, que está almacenada en búfer, y devuelve `Stream`, que se transmite por secuencia. A la inversa, `UploadStream` admite una `Stream` (transmitida por secuencias) y devuelve un `bool` (almacenado en búfer). `EchoStream` toma y devuelve `Stream` y es un ejemplo de una operación cuyos mensajes de entrada y salida se transmiten por secuencias. Finalmente, `GetReversedStream` no toma ninguna entrada y devuelve un `Stream` (transmitido por secuencia).  
  
## <a name="enabling-streamed-transfers"></a>Habilitación de transferencias por secuencias  

 Definir los contratos de operación tal y como se han descrito anteriormente proporciona una transmisión por secuencias en el nivel de modelo de programación. Si se detiene allí, el transporte todavía almacena en búfer el contenido completo del mensaje. Para habilitar la transmisión por secuencias de transporte, seleccione un modo de transferencia en el elemento de enlace del transporte. El elemento de enlace tiene una propiedad `TransferMode` que puede establecerse en `Buffered`, `Streamed`, `StreamedRequest`o `StreamedResponse`. Establecer el modo de transferencia en `Streamed` habilita la comunicación de transmisión por secuencias en ambas direcciones. Establecer el modo de transferencia en `StreamedRequest` o `StreamedResponse` habilita la comunicación de transmisión por secuencias en la solicitud o la respuesta, respectivamente.  
  
 `basicHttpBinding` expone la propiedad `TransferMode` en el enlace tal y como hace `NetTcpBinding` y `NetNamedPipeBinding`. Para otros transportes, debe crear un enlace personalizado para establecer el modo de transferencia.  
  
 El código de configuración siguiente del ejemplo muestra cómo establecer la propiedad `TransferMode` en la transmisión por secuencias en `basicHttpBinding` y un enlace HTTP personalizado:  
  
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
  
 Además de establecer `transferMode` en `Streamed`, el código de configuración anterior establece `maxReceivedMessageSize` en 64 MB. Como un mecanismo de la defensa, `maxReceivedMessageSize` establece un límite en el tamaño máximo permitido de los mensajes que se reciben. El `maxReceivedMessageSize` predeterminado es de 64 KB, que normalmente es demasiado pequeño para los escenarios de transmisión por secuencias.  
  
## <a name="processing-data-as-it-is-streamed"></a>Procesamiento de datos cuando se transmiten por secuencias  

 Las operaciones `GetStream`, `UploadStream` y `EchoStream` tratan sobre enviar datos directamente desde un archivo o sobre guardar los datos recibidos directamente en un archivo. Sin embargo, en algunos casos, hay un requisito para enviar o recibir grandes cantidades de datos y realizar el procesamiento en fragmentos de datos cuando se envían o se reciben. Una manera de resolver tales escenarios es escribir una secuencia personalizada (una clase que deriva de <xref:System.IO.Stream>) que procesa los datos cuando se leen o se escriben. La operación `GetReversedStream` y la clase `ReverseStream` son un ejemplo de esto.  
  
 `GetReversedStream` crea y devuelve una nueva instancia de `ReverseStream`. El procesamiento real se produce cuando el sistema lee desde ese objeto `ReverseStream`. La implementación `ReverseStream.Read` lee un fragmento de bytes del archivo subyacente, los invierte y después devuelve los bytes invertidos. Esto no invierte el contenido del archivo completo, sino un fragmento de bytes cada vez. Se trata de un ejemplo para mostrar cómo puede realizar el procesamiento de la secuencia cuando el contenido se lee o escribe desde la secuencia y hacia ella.  
  
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
  
## <a name="running-the-sample"></a>Ejecutar el ejemplo  

 Para ejecutar el ejemplo, primero compile el servicio y el cliente siguiendo las directrices al final de este documento. A continuación, inicie el servicio y el cliente en dos ventanas de la consola diferentes. Cuando el cliente se inicia, espera a que presione ENTRAR cuando el servicio está listo. Después el cliente llama a los métodos `GetStream()`, `UploadStream()` y `GetReversedStream()` primero sobre HTTP y después sobre TCP. A continuación, se muestra un resultado del ejemplo desde el servicio seguido de uno desde el cliente:  
  
 Resultado del servicio:  
  
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
  
 Resultado del cliente:  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!NOTE]
> Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\Stream`  
