---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: ce21d9d099d893015ea828bdc3b136ab83f6d8e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183432"
---
# <a name="operationcontextscope"></a><span data-ttu-id="1e2d1-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="1e2d1-102">OperationContextScope</span></span>
<span data-ttu-id="1e2d1-103">El OperationContextScope ejemplo muestra cómo enviar información adicional en una llamada de Windows Communication Foundation (WCF) mediante encabezados.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="1e2d1-104">En este ejemplo, tanto el servidor como el cliente son aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1e2d1-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="1e2d1-106">El ejemplo muestra cómo un cliente puede enviar información adicional como <xref:System.ServiceModel.Channels.MessageHeader> mediante <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="1e2d1-107">Se crea un objeto <xref:System.ServiceModel.OperationContextScope> se crea generando un ámbito en un canal.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="1e2d1-108">Los encabezados que se deben traducir al servicio remoto se pueden agregar a la colección <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="1e2d1-109">Los encabezados agregados a esta colección se pueden recuperar en el servicio teniendo acceso a <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="1e2d1-110">Sus llamadas se realizan en varios canales y, a continuación, los encabezados agregados al cliente solo se aplican al canal utilizado para crear <xref:System.ServiceModel.OperationContextScope>.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="1e2d1-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="1e2d1-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="1e2d1-112">Éste es el servicio de ejemplo que recibe un mensaje del cliente e intenta buscar el encabezado en la colección <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="1e2d1-113">El cliente pasa el GUID que envió al encabezado y el servicio recupera el encabezado personalizado y, si está presente, lo compara con el GUID pasado como argumento por el cliente.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
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
  
## <a name="messageheaderclient"></a><span data-ttu-id="1e2d1-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="1e2d1-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="1e2d1-115">Esta es la implementación de cliente que usa el proxy generado por [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) para comunicarse con el servicio remoto.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="1e2d1-116">Crea primero dos objetos proxy de `MessageHeaderReaderClient`.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="1e2d1-117">El cliente crea a continuación un OperationContextScope y genera el ámbito en `client1`.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="1e2d1-118">Agrega un <xref:System.ServiceModel.Channels.MessageHeader> a <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> e invoca una llamada en ambos clientes.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="1e2d1-119">Se asegura de que el `client1` encabezado `client2` se envía solo encendido `RetrieveHeader` y no comprobando el valor devuelto de la llamada.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
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
  
 <span data-ttu-id="1e2d1-120">Este ejemplo se autohospeda.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-120">This sample is self-hosted.</span></span> <span data-ttu-id="1e2d1-121">Se proporciona el siguiente resultado del ejemplo procedente de su ejecución:</span><span class="sxs-lookup"><span data-stu-id="1e2d1-121">The following sample output from running the sample is provided:</span></span>  
  
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
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="1e2d1-122">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="1e2d1-122">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="1e2d1-123">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="1e2d1-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="1e2d1-124">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="1e2d1-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="1e2d1-125">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="1e2d1-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1e2d1-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="1e2d1-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-127">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="1e2d1-128">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="1e2d1-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="1e2d1-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="1e2d1-129">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
