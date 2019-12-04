---
title: Generador de canales
ms.date: 03/30/2017
ms.assetid: 09b53aa1-b13c-476c-a461-e82fcacd2a8b
ms.openlocfilehash: eac315cf88b2ecc7471f194ef6c3be902b3ccbaa
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716047"
---
# <a name="channel-factory"></a><span data-ttu-id="02435-102">Generador de canales</span><span class="sxs-lookup"><span data-stu-id="02435-102">Channel Factory</span></span>

<span data-ttu-id="02435-103">Este ejemplo muestra cómo una aplicación cliente puede crear un canal con la clase <xref:System.ServiceModel.ChannelFactory> en lugar de un cliente generado.</span><span class="sxs-lookup"><span data-stu-id="02435-103">This sample demonstrates how a client application can create a channel with the <xref:System.ServiceModel.ChannelFactory> class instead of a generated client.</span></span> <span data-ttu-id="02435-104">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="02435-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>

> [!NOTE]
> <span data-ttu-id="02435-105">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="02435-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="02435-106">Este ejemplo utiliza la clase <xref:System.ServiceModel.ChannelFactory%601> para crear un canal a un extremo de servicio.</span><span class="sxs-lookup"><span data-stu-id="02435-106">This sample uses the <xref:System.ServiceModel.ChannelFactory%601> class to create a channel to a service endpoint.</span></span> <span data-ttu-id="02435-107">Normalmente, para crear un canal a un punto de conexión de servicio, se genera un tipo de cliente con la [herramienta de utilidad de metadatos de ServiceModel (SvcUtil. exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) y se crea una instancia del tipo generado.</span><span class="sxs-lookup"><span data-stu-id="02435-107">Typically, to create a channel to a service endpoint you generate a client type with the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) and create an instance of the generated type.</span></span> <span data-ttu-id="02435-108">También puede crear un canal utilizando la clase <xref:System.ServiceModel.ChannelFactory%601>, tal y como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="02435-108">You can also create a channel by using the <xref:System.ServiceModel.ChannelFactory%601> class, as demonstrated in this sample.</span></span> <span data-ttu-id="02435-109">El servicio creado por el siguiente código de ejemplo es idéntico al servicio en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="02435-109">The service created by the following sample code is identical to the service in the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>

```csharp
EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
WSHttpBinding binding = new WSHttpBinding();
ChannelFactory<ICalculator> factory = new
                    ChannelFactory<ICalculator>(binding, address);
ICalculator channel = factory.CreateChannel();
```

> [!IMPORTANT]
> <span data-ttu-id="02435-110">Si está ejecutando este ejemplo en un escenario con varios equipos, debe reemplazar el "host local" en el código anterior con el nombre completo del equipo que está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="02435-110">If you are running this sample in a cross-machine scenario, you must replace "localhost" in the preceding code with the fully-qualified name of the machine that is running the service.</span></span> <span data-ttu-id="02435-111">Este ejemplo no utiliza la configuración para establecer la dirección del punto de conexión, por lo que se debe hacer en el código.</span><span class="sxs-lookup"><span data-stu-id="02435-111">This sample does not use configuration to set the endpoint address, so this must be done in code.</span></span>

<span data-ttu-id="02435-112">Una vez creado el canal, se pueden invocar operaciones de servicio de la misma manera que con un cliente generado.</span><span class="sxs-lookup"><span data-stu-id="02435-112">Once the channel is created, service operations can be invoked just as with a generated client.</span></span>

```csharp
// Call the Add service operation.
double value1 = 100.00D;
double value2 = 15.99D;
double result = channel.Add(value1, value2);
Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);
```

<span data-ttu-id="02435-113">Para cerrar el canal, se debe convertir primero a una interfaz <xref:System.ServiceModel.IClientChannel>.</span><span class="sxs-lookup"><span data-stu-id="02435-113">To close the channel, it must first be cast to an <xref:System.ServiceModel.IClientChannel> interface.</span></span> <span data-ttu-id="02435-114">Esto es porque cuando se genera el canal se declara en la aplicación cliente utilizando la interfaz `ICalculator`, que cuenta con métodos como `Add` y `Subtract` pero no `Close`.</span><span class="sxs-lookup"><span data-stu-id="02435-114">This is because the channel as generated is declared in the client application using the `ICalculator` interface, which has methods like `Add` and `Subtract` but not `Close`.</span></span> <span data-ttu-id="02435-115">El método `Close` se origina en la interfaz <xref:System.ServiceModel.ICommunicationObject>.</span><span class="sxs-lookup"><span data-stu-id="02435-115">The `Close` method originates on the <xref:System.ServiceModel.ICommunicationObject> interface.</span></span>

```csharp
// Close the channel.
 ((IClientChannel)client).Close();
```

<span data-ttu-id="02435-116">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="02435-116">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="02435-117">Presione ENTRAR en la ventana de cliente para cerrar la aplicación del cliente.</span><span class="sxs-lookup"><span data-stu-id="02435-117">Press ENTER in the client window to shut down the client application.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="02435-118">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="02435-118">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="02435-119">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02435-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="02435-120">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02435-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span> <span data-ttu-id="02435-121">Observe que este ejemplo no permite la publicación de metadatos.</span><span class="sxs-lookup"><span data-stu-id="02435-121">Note that this sample does not enable metadata publishing.</span></span> <span data-ttu-id="02435-122">Debe habilitarla primero para este ejemplo con objeto de regenerar el tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="02435-122">You must first enable metadata publishing for this sample to regenerate the client type.</span></span>

3. <span data-ttu-id="02435-123">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02435-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>

### <a name="to-run-the-sample-cross-machine"></a><span data-ttu-id="02435-124">Para ejecutar el ejemplo en varios equipos</span><span class="sxs-lookup"><span data-stu-id="02435-124">To run the sample cross machine</span></span>

1. <span data-ttu-id="02435-125">Reemplace el "host local" en el código siguiente con el nombre completo del equipo que está ejecutando el servicio.</span><span class="sxs-lookup"><span data-stu-id="02435-125">Replace "localhost" in the following code with the fully-qualified name of the machine that is running the service.</span></span>

    ```csharp
    EndpointAddress address = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");
    ```

> [!IMPORTANT]
> <span data-ttu-id="02435-126">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="02435-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="02435-127">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="02435-127">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="02435-128">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="02435-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02435-129">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="02435-129">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\ChannelFactory`
