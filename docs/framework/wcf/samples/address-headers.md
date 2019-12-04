---
title: Encabezados de dirección
ms.date: 03/30/2017
ms.assetid: b0c94d4a-3bde-4b4d-bb6d-9f12bc3a6940
ms.openlocfilehash: 3bc8512fb2492a7249c81fc33a3c7b83904f1ccd
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715227"
---
# <a name="address-headers"></a><span data-ttu-id="bfdda-102">Encabezados de dirección</span><span class="sxs-lookup"><span data-stu-id="bfdda-102">Address Headers</span></span>

<span data-ttu-id="bfdda-103">En el ejemplo de encabezados de dirección se muestra cómo los clientes pueden pasar parámetros de referencia a un servicio mediante Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="bfdda-103">The Address Headers sample demonstrates how clients can pass reference parameters to a service using Windows Communication Foundation (WCF).</span></span>

> [!NOTE]
> <span data-ttu-id="bfdda-104">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="bfdda-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="bfdda-105">La especificación del direccionamiento del WS define la noción de una referencia del punto de conexión como una manera de direccionar un punto de conexión de servicio Web determinado.</span><span class="sxs-lookup"><span data-stu-id="bfdda-105">The WS-Addressing specification defines the notion of an endpoint reference as a way to address a particular Web service endpoint.</span></span> <span data-ttu-id="bfdda-106">En WCF, las referencias de punto de conexión se modelan mediante el `EndpointAddress` clase-`EndpointAddress` es el tipo del campo de dirección de la clase `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="bfdda-106">In WCF, endpoint references are modeled using the `EndpointAddress` class - `EndpointAddress` is the type of the Address field of the `ServiceEndpoint` class.</span></span>

<span data-ttu-id="bfdda-107">La parte del modelo de referencia de punto de conexión es que cada referencia puede llevar algunos parámetros de referencia que agregan información de identificación excepcional.</span><span class="sxs-lookup"><span data-stu-id="bfdda-107">Part of the endpoint reference model is that each reference can carry some reference parameters that add extra identifying information.</span></span> <span data-ttu-id="bfdda-108">En WCF, estos parámetros de referencia se modelan como instancias de `AddressHeader` clase.</span><span class="sxs-lookup"><span data-stu-id="bfdda-108">In WCF, these reference parameters are modeled as instances of `AddressHeader` class.</span></span>

<span data-ttu-id="bfdda-109">En este ejemplo, el cliente agrega un parámetro de referencia a `EndpointAddress` del punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="bfdda-109">In this sample, the client adds a reference parameter to the `EndpointAddress` of the client endpoint.</span></span> <span data-ttu-id="bfdda-110">El servicio busca este parámetro de referencia y utiliza su valor en la lógica de su operación del servicio "Hola".</span><span class="sxs-lookup"><span data-stu-id="bfdda-110">The service looks for this reference parameter and uses its value in the logic of its "Hello" service operation.</span></span>

## <a name="client"></a><span data-ttu-id="bfdda-111">Client</span><span class="sxs-lookup"><span data-stu-id="bfdda-111">Client</span></span>

<span data-ttu-id="bfdda-112">Para que el cliente envíe un parámetro de referencia, debe agregar un `AddressHeader` a `EndpointAddress` de `ServiceEndpoint`.</span><span class="sxs-lookup"><span data-stu-id="bfdda-112">For the client to send a reference parameter, it must add an `AddressHeader` to the `EndpointAddress` of the `ServiceEndpoint`.</span></span> <span data-ttu-id="bfdda-113">Dado que la clase `EndpointAddress` es inmutable, la modificación de una dirección del punto de conexión se debe hacer utilizando la clase `EndpointAddressBuilder`.</span><span class="sxs-lookup"><span data-stu-id="bfdda-113">Because the `EndpointAddress` class is immutable, modification of an endpoint address must be done using the `EndpointAddressBuilder` class.</span></span> <span data-ttu-id="bfdda-114">El código siguiente inicializa el cliente para enviar un parámetro de referencia como parte de su mensaje.</span><span class="sxs-lookup"><span data-stu-id="bfdda-114">The following code initializes the client to send a reference parameter as part of its message.</span></span>

```csharp
HelloClient client = new HelloClient();
EndpointAddressBuilder builder =
    new EndpointAddressBuilder(client.Endpoint.Address);
AddressHeader header =
    AddressHeader.CreateAddressHeader(IDName, IDNamespace, "John");
builder.Headers.Add(header);
client.Endpoint.Address = builder.ToEndpointAddress();
```

<span data-ttu-id="bfdda-115">El código crea un `EndpointAddressBuilder` utilizando el `EndpointAddress` original como un valor inicial.</span><span class="sxs-lookup"><span data-stu-id="bfdda-115">The code creates an `EndpointAddressBuilder` using the original `EndpointAddress` as an initial value.</span></span> <span data-ttu-id="bfdda-116">A continuación, agrega un encabezado de dirección recién creado; la llamada a `CreateAddressHeader` crea un encabezado con un nombre, espacio de nombres y valor determinados.</span><span class="sxs-lookup"><span data-stu-id="bfdda-116">It then adds a newly created address header; the call to `CreateAddressHeader` creates a header with a particular name, namespace, and value.</span></span> <span data-ttu-id="bfdda-117">Aquí el valor es "John."</span><span class="sxs-lookup"><span data-stu-id="bfdda-117">Here the value is "John".</span></span> <span data-ttu-id="bfdda-118">Una vez agregado al generador el encabezado, el método `ToEndpointAddress()` convierte el generador (mutable) en una dirección del punto de conexión (inmutable), la cual está asignada al campo de dirección del punto de conexión del cliente.</span><span class="sxs-lookup"><span data-stu-id="bfdda-118">Once the header is added to the builder, the `ToEndpointAddress()` method converts the (mutable) builder back into an (immutable) endpoint address, which is assigned back to the client endpoint's Address field.</span></span>

<span data-ttu-id="bfdda-119">Ahora cuando el cliente llama a `Console.WriteLine(client.Hello());`, el servicio puede obtener el valor de este parámetro de dirección, como se ha visto en el resultado del cliente.</span><span class="sxs-lookup"><span data-stu-id="bfdda-119">Now when the client calls `Console.WriteLine(client.Hello());`, the service is able to get the value of this address parameter, as seen in the resulting output of the client.</span></span>

`Hello, John`

## <a name="server"></a><span data-ttu-id="bfdda-120">Server</span><span class="sxs-lookup"><span data-stu-id="bfdda-120">Server</span></span>

<span data-ttu-id="bfdda-121">La implementación de la operación del servicio`Hello()` utiliza el `OperationContext` actual para inspeccionar los valores de los encabezados en el mensaje entrante.</span><span class="sxs-lookup"><span data-stu-id="bfdda-121">The implementation of the service operation `Hello()` uses the current `OperationContext` to inspect the values of the headers on the incoming message.</span></span>

```csharp
string id = null;
// look at headers on incoming message
for (int i = 0;
     i < OperationContext.Current.IncomingMessageHeaders.Count;
     ++i)
{
    MessageHeaderInfo h = OperationContext.Current.IncomingMessageHeaders[i];
    // for any reference parameters with the correct name & namespace
    if (h.IsReferenceParameter &&
        h.Name == IDName &&
        h.Namespace == IDNamespace)
    {
        // read the value of that header
        XmlReader xr = OperationContext.Current.IncomingMessageHeaders.GetReaderAtHeader(i);
        id = xr.ReadElementContentAsString();
    }
}
return "Hello, " + id;
```

<span data-ttu-id="bfdda-122">El código produce iteraciones sobre todos los encabezados en el mensaje entrante, buscando encabezados que son parámetros de referencia con el nombre determinado y.</span><span class="sxs-lookup"><span data-stu-id="bfdda-122">The code iterates over all the headers on the incoming message, looking for headers that are reference parameters with the particular name and.</span></span> <span data-ttu-id="bfdda-123">Cuando se encuentra el parámetro, lee el valor del parámetro y lo almacena en la variante de "id.".</span><span class="sxs-lookup"><span data-stu-id="bfdda-123">When the parameter is found, it reads the value of the parameter and stores it in the "id" variable.</span></span>

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bfdda-124">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bfdda-124">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="bfdda-125">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bfdda-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="bfdda-126">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bfdda-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

3. <span data-ttu-id="bfdda-127">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bfdda-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfdda-128">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bfdda-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bfdda-129">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bfdda-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="bfdda-130">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bfdda-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfdda-131">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bfdda-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\AddressHeaders`
