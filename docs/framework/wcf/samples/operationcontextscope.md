---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 581f75ece1a601b3baf590c1923a17a353de1ff1
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714621"
---
# <a name="operationcontextscope"></a><span data-ttu-id="7fa1f-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="7fa1f-102">OperationContextScope</span></span>
<span data-ttu-id="7fa1f-103">En el ejemplo OperationContextScope se muestra cómo enviar información adicional sobre una llamada a Windows Communication Foundation (WCF) mediante encabezados.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="7fa1f-104">En este ejemplo, tanto el servidor como el cliente son aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7fa1f-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7fa1f-106">El ejemplo muestra cómo un cliente puede enviar información adicional como <xref:System.ServiceModel.Channels.MessageHeader> mediante <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="7fa1f-107">Se crea un objeto <xref:System.ServiceModel.OperationContextScope> se crea generando un ámbito en un canal.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="7fa1f-108">Los encabezados que se deben traducir al servicio remoto se pueden agregar a la colección <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="7fa1f-109">Los encabezados agregados a esta colección se pueden recuperar en el servicio teniendo acceso a <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="7fa1f-110">Sus llamadas se realizan en varios canales y, a continuación, los encabezados agregados al cliente solo se aplican al canal utilizado para crear <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="7fa1f-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="7fa1f-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="7fa1f-112">Éste es el servicio de ejemplo que recibe un mensaje del cliente e intenta buscar el encabezado en la colección <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="7fa1f-113">El cliente pasa el GUID que envió al encabezado y el servicio recupera el encabezado personalizado y, si está presente, lo compara con el GUID pasado como argumento por el cliente.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```csharp
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="7fa1f-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="7fa1f-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="7fa1f-115">Esta es la implementación del cliente que usa el proxy generado por la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para comunicarse con el servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="7fa1f-116">Crea primero dos objetos proxy de `MessageHeaderReaderClient`.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="7fa1f-117">El cliente crea a continuación un OperationContextScope y genera el ámbito en `client1`.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="7fa1f-118">Agrega un <xref:System.ServiceModel.Channels.MessageHeader> a <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> e invoca una llamada en ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="7fa1f-119">Garantiza que el encabezado se envíe solo en `client1` y no en `client2` comprobando el valor devuelto de la llamada a `RetrieveHeader`.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```csharp
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetrieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="7fa1f-120">Este ejemplo se autohospeda.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-120">This sample is self-hosted.</span></span> <span data-ttu-id="7fa1f-121">Se proporciona el siguiente resultado del ejemplo procedente de su ejecución:</span><span class="sxs-lookup"><span data-stu-id="7fa1f-121">The following sample output from running the sample is provided:</span></span>  
  
```console  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7fa1f-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="7fa1f-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7fa1f-123">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7fa1f-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7fa1f-124">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7fa1f-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7fa1f-125">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7fa1f-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7fa1f-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7fa1f-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-127">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="7fa1f-128">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7fa1f-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7fa1f-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="7fa1f-129">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
