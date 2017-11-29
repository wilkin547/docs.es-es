---
title: "Encabezados de dirección"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 19a7291ce13221e85b49c6ef97c6b375b8b71014
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="address-headers"></a><span data-ttu-id="8923a-102">Encabezados de dirección</span><span class="sxs-lookup"><span data-stu-id="8923a-102">Address Headers</span></span>
<span data-ttu-id="8923a-103">El ejemplo de encabezados de dirección muestra cómo los clientes pueden pasar los parámetros de referencia a un servicio utilizando [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8923a-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8923a-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8923a-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8923a-105">La especificación del direccionamiento del WS define la noción de una referencia del extremo como una manera de direccionar un extremo de servicio Web determinado.</span><span class="sxs-lookup"><span data-stu-id="8923a-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="8923a-106">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], las referencias del extremo se modelan utilizando la clase `EndpointAddress`- `EndpointAddress` es el tipo del campo de dirección de la clase `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="8923a-106">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>  
  
 <span data-ttu-id="8923a-107">La parte del modelo de referencia de extremo es que cada referencia puede llevar algunos parámetros de referencia que agregan información de identificación excepcional.</span><span class="sxs-lookup"><span data-stu-id="8923a-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="8923a-108">En [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], estos parámetros de referencia se modelan como instancias de la clase `AddressHeader`.</span><span class="sxs-lookup"><span data-stu-id="8923a-108">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], these reference parameters are modeled as instances of `AddressHeader` class.</span></span>  
  
 <span data-ttu-id="8923a-109">En este ejemplo, el cliente agrega un parámetro de referencia a `EndpointAddress` del extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="8923a-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="8923a-110">El servicio busca este parámetro de referencia y utiliza su valor en la lógica de su operación del servicio "Hola".</span><span class="sxs-lookup"><span data-stu-id="8923a-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>  
  
## <a name="client"></a><span data-ttu-id="8923a-111">Cliente</span><span class="sxs-lookup"><span data-stu-id="8923a-111">Client</span></span>  
 <span data-ttu-id="8923a-112">Para que el cliente envíe un parámetro de referencia, debe agregar un `AddressHeader` a `EndpointAddress` de `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="8923a-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="8923a-113">Dado que la clase `EndpointAddress` es inmutable, la modificación de una dirección del extremo se debe hacer utilizando la clase `EndpointAddressBuilder`.</span><span class="sxs-lookup"><span data-stu-id="8923a-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="8923a-114">El código siguiente inicializa el cliente para enviar un parámetro de referencia como parte de su mensaje.</span><span class="sxs-lookup"><span data-stu-id="8923a-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>  
  
```  
HelloClient client = new HelloClient();  
EndpointAddressBuilder builder =   
    new EndpointAddressBuilder(client.Endpoint.Address);  
AddressHeader header =   
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");  
builder.Headers.Add(header);  
client.Endpoint.Address = builder.ToEndpointAddress();  
```  
  
 <span data-ttu-id="8923a-115">El código crea un `EndpointAddressBuilder` utilizando el `EndpointAddress` original como un valor inicial.</span><span class="sxs-lookup"><span data-stu-id="8923a-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="8923a-116">Agrega a continuación un encabezado de dirección creado recientemente; la llamada a `CreateAddressHeadercreates` un encabezado con un nombre determinado, espacio de nombres y valor.</span><span class="sxs-lookup"><span data-stu-id="8923a-116">It then adds a newly created address header; the call to `CreateAddressHeadercreates` a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="8923a-117">Aquí el valor es "John."</span><span class="sxs-lookup"><span data-stu-id="8923a-117">Here the value is "John".</span></span> <span data-ttu-id="8923a-118">Una vez agregado al generador el encabezado, el método `ToEndpointAddress()` convierte el generador (mutable) en una dirección del extremo (inmutable), la cual está asignada al campo de dirección del extremo del cliente.</span><span class="sxs-lookup"><span data-stu-id="8923a-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>  
  
 <span data-ttu-id="8923a-119">Ahora cuando el cliente llama a `Console.WriteLine(client.Hello());`, el servicio puede obtener el valor de este parámetro de dirección, como se ha visto en el resultado del cliente.</span><span class="sxs-lookup"><span data-stu-id="8923a-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>  
  
 `Hello, John`  
  
## <a name="server"></a><span data-ttu-id="8923a-120">Servidor</span><span class="sxs-lookup"><span data-stu-id="8923a-120">Server</span></span>  
 <span data-ttu-id="8923a-121">La implementación de la operación del servicio`Hello()` utiliza el `OperationContext` actual para inspeccionar los valores de los encabezados en el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="8923a-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>  
  
```  
string id = null;  
// look at headers on incoming message  
for (int i = 0;   
     i < OperationContext.Current.IncomingMessageHeaders.Count;   
     ++i)  
{  
    MessageHeaderInfo h =   
        OperationContext.Current.IncomingMessageHeaders[i];  
    // for any reference parameters with the correct name & namespace  
    if (h.IsReferenceParameter &&   
        h.Name == IDName &&   
        h.Namespace == IDNamespace)  
    {  
        // read the value of that header  
        XmlReader xr =   
OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);  
        id = xr.ReadElementContentAsString();  
    }  
}  
return "Hello, " + id;  
```  
  
 <span data-ttu-id="8923a-122">El código produce iteraciones sobre todos los encabezados en el mensaje entrante, buscando encabezados que son parámetros de referencia con el nombre determinado y.</span><span class="sxs-lookup"><span data-stu-id="8923a-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="8923a-123">Cuando se encuentra el parámetro, lee el valor del parámetro y lo almacena en la variante de "id.".</span><span class="sxs-lookup"><span data-stu-id="8923a-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8923a-124">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8923a-124">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8923a-125">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8923a-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="8923a-126">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8923a-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="8923a-127">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8923a-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8923a-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8923a-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8923a-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8923a-129">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8923a-130">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8923a-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8923a-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8923a-131">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`  
  
## <a name="see-also"></a><span data-ttu-id="8923a-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="8923a-132">See Also</span></span>
