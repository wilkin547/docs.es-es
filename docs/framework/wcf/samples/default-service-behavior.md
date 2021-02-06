---
description: 'Más información sobre: comportamiento predeterminado del servicio'
title: Comportamiento de servicio predeterminado
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
ms.openlocfilehash: a0b83180c9ab758cb7a8db7f92a8bf0c081e4489
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631988"
---
# <a name="default-service-behavior"></a><span data-ttu-id="bd1d2-103">Comportamiento de servicio predeterminado</span><span class="sxs-lookup"><span data-stu-id="bd1d2-103">Default Service Behavior</span></span>

<span data-ttu-id="bd1d2-104">Este ejemplo muestra cómo se pueden configurar los valores del comportamiento de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-104">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="bd1d2-105">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-105">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="bd1d2-106">Este ejemplo define explícitamente los comportamientos del servicio y de la operación mediante los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-106">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="bd1d2-107">Puede configurar los comportamientos en archivos de configuración o imperativamente en código (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="bd1d2-107">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="bd1d2-108">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bd1d2-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="bd1d2-110">La clase de servicio especifica comportamientos con <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-110">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="bd1d2-111">Todos los valores especificados son valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-111">All values specified are the defaults.</span></span>  
  
```csharp
[ServiceBehavior(  
    AutomaticSessionShutdown=true,  
    ConcurrencyMode=ConcurrencyMode.Single,  
    InstanceContextMode=InstanceContextMode.PerSession,  
    IncludeExceptionDetailInFaults=false,  
    UseSynchronizationContext=true,  
    ValidateMustUnderstand=true)]  
public class CalculatorService : ICalculator  
{  
    [OperationBehavior(  
        TransactionAutoComplete=true,  
        TransactionScopeRequired=false,  
        Impersonation=ImpersonationOption.NotAllowed)]  
    public double Add(double n1, double n2)  
    {  
        System.Threading.Thread.Sleep(1600);  
        return n1 + n2;  
    }  
    ...  
}  
```  
  
 <span data-ttu-id="bd1d2-112">Los comportamientos del servicio se especifican con el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-112">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="bd1d2-113">La tabla siguiente describe algunos de estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-113">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="bd1d2-114">Comportamiento de servicio</span><span class="sxs-lookup"><span data-stu-id="bd1d2-114">Service behavior</span></span>|<span data-ttu-id="bd1d2-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd1d2-115">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="bd1d2-116">Se cierra automáticamente una sesión cuando lo solicita el cliente.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-116">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="bd1d2-117">Especifica el modo de simultaneidad para cada instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-117">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="bd1d2-118">Especifica el modo de contexto de instancia.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-118">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="bd1d2-119">Determina si utilizar el contexto de sincronización proporcionado, si se ha establecido uno.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-119">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="bd1d2-120">Utilice esto cuando desee controlar si usar un `WindowsFormsSynchronizationContext` en aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-120">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="bd1d2-121">Determina si las excepciones de ejecución no controladas generales se convertirán en `Fault<string>` y se enviará como un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-121">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="bd1d2-122">Especifica el nivel de aislamiento de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-122">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="bd1d2-123">Determina si los encabezados del mensaje inesperados producen una condición de error.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-123">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="bd1d2-124">Los comportamientos de la operación se especifican utilizando el atributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-124">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="bd1d2-125">La tabla siguiente describe algunos de estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-125">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="bd1d2-126">Comportamiento de la operación</span><span class="sxs-lookup"><span data-stu-id="bd1d2-126">Operation Behavior</span></span>|<span data-ttu-id="bd1d2-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="bd1d2-127">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="bd1d2-128">Determina si la realización de la operación del servicio confirma la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-128">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="bd1d2-129">Determina si la operación del servicio da de alta en una transacción fluida del cliente.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-129">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="bd1d2-130">Determina si la operación de servicio suplanta la identidad del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-130">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="bd1d2-131">Determina si las instancias del servicio se reciclan en el inicio o final de la llamada de operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-131">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="bd1d2-132">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-132">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="bd1d2-133">El retraso entre las llamadas es el resultado de las llamadas a `System.Threading.Thread.Sleep()` realizadas en las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-133">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="bd1d2-134">El resto de los ejemplos de comportamiento explica con más detalle estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-134">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="bd1d2-135">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-135">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd1d2-136">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="bd1d2-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="bd1d2-137">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bd1d2-137">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="bd1d2-138">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bd1d2-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="bd1d2-139">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bd1d2-139">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="bd1d2-140">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-140">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bd1d2-141">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-141">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bd1d2-142">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-142">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd1d2-143">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="bd1d2-143">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
