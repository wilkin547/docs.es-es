---
description: 'Más información sobre: simultaneidad'
title: Simultaneidad
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, concurency sample
- Concurrency Sample [Windows Communication Foundation]
ms.assetid: f8dbdfb3-6858-4f95-abe3-3a1db7878926
ms.openlocfilehash: 2fbb6f9fc5ee2807ed0ca0592c364f048d5d8b14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99778547"
---
# <a name="concurrency"></a><span data-ttu-id="318cc-103">Simultaneidad</span><span class="sxs-lookup"><span data-stu-id="318cc-103">Concurrency</span></span>

<span data-ttu-id="318cc-104">El ejemplo de la Simultaneidad muestra cómo utilizar <xref:System.ServiceModel.ServiceBehaviorAttribute> con la enumeración <xref:System.ServiceModel.ConcurrencyMode>, que controla si una instancia de un servicio procesa secuencialmente o simultáneamente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="318cc-104">The Concurrency sample demonstrates using the <xref:System.ServiceModel.ServiceBehaviorAttribute> with the <xref:System.ServiceModel.ConcurrencyMode> enumeration, which controls whether an instance of a service processes messages sequentially or concurrently.</span></span> <span data-ttu-id="318cc-105">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="318cc-105">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="318cc-106">Este ejemplo define un nuevo contrato, `ICalculatorConcurrency`, que hereda de `ICalculator`, proporcionando dos operaciones adicionales para inspeccionar el estado de la simultaneidad del servicio.</span><span class="sxs-lookup"><span data-stu-id="318cc-106">This sample defines a new contract, `ICalculatorConcurrency`, which inherits from `ICalculator`, providing two additional operations for inspecting the state of the service concurrency.</span></span> <span data-ttu-id="318cc-107">Modificando el valor de simultaneidad, puede observar el cambio en el comportamiento ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="318cc-107">By altering the concurrency setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="318cc-108">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="318cc-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="318cc-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="318cc-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="318cc-110">Hay tres modos de simultaneidad disponibles:</span><span class="sxs-lookup"><span data-stu-id="318cc-110">There are three concurrency modes available:</span></span>  
  
- <span data-ttu-id="318cc-111">`Single`: Cada instancia del servicio procesa a la vez un mensaje.</span><span class="sxs-lookup"><span data-stu-id="318cc-111">`Single`: Each service instance processes one message at a time.</span></span> <span data-ttu-id="318cc-112">Éste es el modo de simultaneidad predeterminado.</span><span class="sxs-lookup"><span data-stu-id="318cc-112">This is the default concurrency mode.</span></span>  
  
- <span data-ttu-id="318cc-113">`Multiple`: Cada instancia del servicio procesa simultáneamente varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="318cc-113">`Multiple`: Each service instance processes multiple messages concurrently.</span></span> <span data-ttu-id="318cc-114">La implementación del servicio debe ser segura para los subprocesos para utilizar este modo de simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="318cc-114">The service implementation must be thread-safe to use this concurrency mode.</span></span>  
  
- <span data-ttu-id="318cc-115">`Reentrant`: cada instancia de servicio procesa a la vez un mensaje, pero acepta llamadas reentrantes.</span><span class="sxs-lookup"><span data-stu-id="318cc-115">`Reentrant`: Each service instance processes one message at a time, but accepts reentrant calls.</span></span> <span data-ttu-id="318cc-116">El servicio solo acepta estas llamadas cuando está llamando a. Reentrante se muestra en el ejemplo [ConcurrencyMode. reentrante](concurrencymode-reentrant.md) .</span><span class="sxs-lookup"><span data-stu-id="318cc-116">The service only accepts these calls when it is calling out. Reentrant is demonstrated in the [ConcurrencyMode.Reentrant](concurrencymode-reentrant.md) sample.</span></span>  
  
 <span data-ttu-id="318cc-117">El uso de simultaneidad se relaciona con el modo de creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="318cc-117">The use of concurrency is related to the instancing mode.</span></span> <span data-ttu-id="318cc-118">Para crear instancias<xref:System.ServiceModel.InstanceContextMode.PerCall>, la simultaneidad no es pertinente, porque una nueva instancia del servicio procesa cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="318cc-118">In <xref:System.ServiceModel.InstanceContextMode.PerCall> instancing, concurrency is not relevant, because each message is processed by a new service instance.</span></span> <span data-ttu-id="318cc-119">Para crear instancias<xref:System.ServiceModel.InstanceContextMode.Single>, o<xref:System.ServiceModel.ConcurrencyMode.Single> o la simultaneidad <xref:System.ServiceModel.ConcurrencyMode.Multiple> es pertinente, dependiendo de si la instancia única procesa secuencialmente o simultáneamente los mensajes.</span><span class="sxs-lookup"><span data-stu-id="318cc-119">In <xref:System.ServiceModel.InstanceContextMode.Single> instancing, either <xref:System.ServiceModel.ConcurrencyMode.Single> or <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency is relevant, depending on whether the single instance processes messages sequentially or concurrently.</span></span> <span data-ttu-id="318cc-120">Para crear instancias<xref:System.ServiceModel.InstanceContextMode.PerSession>, cualquiera de los modos de la simultaneidad puede ser pertinente.</span><span class="sxs-lookup"><span data-stu-id="318cc-120">In <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing, any of the concurrency modes may be relevant.</span></span>  
  
 <span data-ttu-id="318cc-121">La clase de servicio especifica el comportamiento de la simultaneidad con el atributo `[ServiceBehavior(ConcurrencyMode=<setting>)]` como se muestra en el ejemplo de código que sigue.</span><span class="sxs-lookup"><span data-stu-id="318cc-121">The service class specifies concurrency behavior with the `[ServiceBehavior(ConcurrencyMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="318cc-122">Cambiando las líneas marcadas con comentarios, se puede experimentar con `Single` y con los modos de simultaneidad `Multiple`.</span><span class="sxs-lookup"><span data-stu-id="318cc-122">By changing which lines are commented out, you can experiment with the `Single` and `Multiple` concurrency modes.</span></span> <span data-ttu-id="318cc-123">Recuerde recompilar el servicio después de cambiar el modo de la simultaneidad.</span><span class="sxs-lookup"><span data-stu-id="318cc-123">Remember to rebuild the service after changing the concurrency mode.</span></span>  
  
```csharp
// Single allows a single message to be processed sequentially by each service instance.  
//[ServiceBehavior(ConcurrencyMode = ConcurrencyMode.Single, InstanceContextMode = InstanceContextMode.Single)]  
  
// Multiple allows concurrent processing of multiple messages by a service instance.  
// The service implementation should be thread-safe. This can be used to increase throughput.  
[ServiceBehavior(ConcurrencyMode=ConcurrencyMode.Multiple, InstanceContextMode = InstanceContextMode.Single)]  
  
// Uses Thread.Sleep to vary the execution time of each operation.  
public class CalculatorService : ICalculatorConcurrency  
{  
    int operationCount;  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(180);  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(100);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(150);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        operationCount++;  
        System.Threading.Thread.Sleep(120);  
        return n1 / n2;  
    }  
  
    public string GetConcurrencyMode()  
    {
        // Return the ConcurrencyMode of the service.  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.ConcurrencyMode.ToString();  
    }  
  
    public int GetOperationCount()  
    {
        // Return the number of operations.  
        return operationCount;  
    }  
}  
```  
  
 <span data-ttu-id="318cc-124">El ejemplo utiliza la simultaneidad <xref:System.ServiceModel.ConcurrencyMode.Multiple> con <xref:System.ServiceModel.InstanceContextMode.Single> que crea instancias de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="318cc-124">The sample uses <xref:System.ServiceModel.ConcurrencyMode.Multiple> concurrency with <xref:System.ServiceModel.InstanceContextMode.Single> instancing by default.</span></span> <span data-ttu-id="318cc-125">El código de cliente se ha modificado para utilizar un proxy asincrónico.</span><span class="sxs-lookup"><span data-stu-id="318cc-125">The client code has been modified to use an asynchronous proxy.</span></span> <span data-ttu-id="318cc-126">Esto permite al cliente realizar varias llamadas al servicio sin esperar por una respuesta entre cada llamada.</span><span class="sxs-lookup"><span data-stu-id="318cc-126">This allows the client to make multiple calls to the service without waiting for a response between each call.</span></span> <span data-ttu-id="318cc-127">Puede observar la diferencia en el comportamiento del modo de simultaneidad de servicio.</span><span class="sxs-lookup"><span data-stu-id="318cc-127">You can observe the difference in behavior of the service concurrency mode.</span></span>  
  
 <span data-ttu-id="318cc-128">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="318cc-128">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="318cc-129">Se muestra el modo de la simultaneidad en el que el servicio se está ejecutando, se llama a cada operación y, a continuación, se muestra el recuento de la operación.</span><span class="sxs-lookup"><span data-stu-id="318cc-129">The concurrency mode that the service is running under is displayed, each operation is called, and then the operation count is displayed.</span></span> <span data-ttu-id="318cc-130">Observe que cuando el modo de la simultaneidad es `Multiple`, los resultados se devuelven en un orden diferente a como se llamaron, porque el servicio procesa simultáneamente varios mensajes.</span><span class="sxs-lookup"><span data-stu-id="318cc-130">Notice that when the concurrency mode is `Multiple`, the results are returned in a different order than how they were called, because the service processes multiple messages concurrently.</span></span> <span data-ttu-id="318cc-131">Cambiando el modo de simultaneidad a `Single`, los resultados se devuelven en el orden en que se denominaron, porque el servicio procesa secuencialmente cada mensaje.</span><span class="sxs-lookup"><span data-stu-id="318cc-131">By changing the concurrency mode to `Single`, the results are returned in the order they were called, because the service processes each message sequentially.</span></span> <span data-ttu-id="318cc-132">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="318cc-132">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="318cc-133">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="318cc-133">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="318cc-134">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="318cc-134">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="318cc-135">Si usa Svcutil.exe para generar el cliente proxy, asegúrese de que incluye la `/async` opción.</span><span class="sxs-lookup"><span data-stu-id="318cc-135">If you use Svcutil.exe to generate the proxy client, ensure that you include the `/async` option.</span></span>  
  
3. <span data-ttu-id="318cc-136">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="318cc-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="318cc-137">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="318cc-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="318cc-138">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="318cc-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="318cc-139">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="318cc-139">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="318cc-140">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="318cc-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="318cc-141">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="318cc-141">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Concurrency`  
