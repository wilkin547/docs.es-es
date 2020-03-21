---
title: Comportamiento de servicio predeterminado
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, defaults
- Default Service Behavior Sample [Windows Communication Foundation]
ms.assetid: 442d4f71-c64e-4c62-816a-a66c38e7d3ec
ms.openlocfilehash: 798231cbfddf17dd63a61f3e2a07a6490289e56f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183751"
---
# <a name="default-service-behavior"></a><span data-ttu-id="54019-102">Comportamiento de servicio predeterminado</span><span class="sxs-lookup"><span data-stu-id="54019-102">Default Service Behavior</span></span>
<span data-ttu-id="54019-103">Este ejemplo muestra cómo se pueden configurar los valores del comportamiento de servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-103">This sample demonstrates how service behavior settings can be configured.</span></span> <span data-ttu-id="54019-104">El ejemplo se basa en la [introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="54019-105">Este ejemplo define explícitamente los comportamientos del servicio y de la operación mediante los atributos <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54019-105">This sample explicitly defines service behaviors and operation behaviors using the <xref:System.ServiceModel.ServiceBehaviorAttribute> and <xref:System.ServiceModel.OperationBehaviorAttribute> attributes.</span></span> <span data-ttu-id="54019-106">Puede configurar los comportamientos en archivos de configuración o imperativamente en código (como se muestra en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="54019-106">You can configure behaviors in configuration files or imperatively in code (as this sample demonstrates).</span></span>  
  
 <span data-ttu-id="54019-107">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54019-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="54019-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="54019-109">La clase de servicio especifica comportamientos con <xref:System.ServiceModel.ServiceBehaviorAttribute> y <xref:System.ServiceModel.OperationBehaviorAttribute>, tal y como se muestra en el ejemplo de código siguiente.</span><span class="sxs-lookup"><span data-stu-id="54019-109">The service class specifies behaviors with the <xref:System.ServiceModel.ServiceBehaviorAttribute> and the <xref:System.ServiceModel.OperationBehaviorAttribute> as shown in the following code sample.</span></span> <span data-ttu-id="54019-110">Todos los valores especificados son valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="54019-110">All values specified are the defaults.</span></span>  
  
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
  
 <span data-ttu-id="54019-111">Los comportamientos del servicio se especifican con el atributo <xref:System.ServiceModel.ServiceBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54019-111">Service behaviors are specified with the <xref:System.ServiceModel.ServiceBehaviorAttribute> attribute.</span></span> <span data-ttu-id="54019-112">La tabla siguiente describe algunos de estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="54019-112">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="54019-113">Comportamiento de servicio</span><span class="sxs-lookup"><span data-stu-id="54019-113">Service behavior</span></span>|<span data-ttu-id="54019-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="54019-114">Description</span></span>|  
|----------------------|-----------------|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.AutomaticSessionShutdown%2A>|<span data-ttu-id="54019-115">Se cierra automáticamente una sesión cuando lo solicita el cliente.</span><span class="sxs-lookup"><span data-stu-id="54019-115">Automatically shuts down a session at the client's request.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ConcurrencyMode%2A>|<span data-ttu-id="54019-116">Especifica el modo de simultaneidad para cada instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-116">Specifies the concurrency mode for each service instance.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.InstanceContextMode%2A>|<span data-ttu-id="54019-117">Especifica el modo de contexto de instancia.</span><span class="sxs-lookup"><span data-stu-id="54019-117">Specifies the instance context mode.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.UseSynchronizationContext%2A>|<span data-ttu-id="54019-118">Determina si utilizar el contexto de sincronización proporcionado, si se ha establecido uno.</span><span class="sxs-lookup"><span data-stu-id="54019-118">Determines whether to use the provided synchronization context, if one is set.</span></span> <span data-ttu-id="54019-119">Utilice esto cuando desee controlar si usar un `WindowsFormsSynchronizationContext` en aplicaciones de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="54019-119">Use this when you want to control whether to use a `WindowsFormsSynchronizationContext` in Windows Forms applications.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.IncludeExceptionDetailInFaults%2A>|<span data-ttu-id="54019-120">Determina si las excepciones de ejecución no controladas generales se convertirán en `Fault<string>` y se enviará como un mensaje de error.</span><span class="sxs-lookup"><span data-stu-id="54019-120">Determines whether general unhandled execution exceptions are to be converted into a `Fault<string>` and sent as a fault message.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.TransactionIsolationLevel%2A>|<span data-ttu-id="54019-121">Especifica el nivel de aislamiento de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="54019-121">Specifies the isolation level for transactions.</span></span>|  
|<xref:System.ServiceModel.ServiceBehaviorAttribute.ValidateMustUnderstand%2A>|<span data-ttu-id="54019-122">Determina si los encabezados del mensaje inesperados producen una condición de error.</span><span class="sxs-lookup"><span data-stu-id="54019-122">Determines whether unexpected message headers cause an error condition.</span></span>|  
  
 <span data-ttu-id="54019-123">Los comportamientos de la operación se especifican utilizando el atributo <xref:System.ServiceModel.OperationBehaviorAttribute>.</span><span class="sxs-lookup"><span data-stu-id="54019-123">Operation behaviors are specified by using the <xref:System.ServiceModel.OperationBehaviorAttribute> attribute.</span></span> <span data-ttu-id="54019-124">La tabla siguiente describe algunos de estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="54019-124">The following table describes some of these behaviors.</span></span>  
  
|<span data-ttu-id="54019-125">Comportamiento de la operación</span><span class="sxs-lookup"><span data-stu-id="54019-125">Operation Behavior</span></span>|<span data-ttu-id="54019-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="54019-126">Description</span></span>|  
|------------------------|-----------------|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionAutoComplete%2A>|<span data-ttu-id="54019-127">Determina si la realización de la operación del servicio confirma la transacción actual.</span><span class="sxs-lookup"><span data-stu-id="54019-127">Determines whether service operation completion commits the current transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.TransactionScopeRequired%2A>|<span data-ttu-id="54019-128">Determina si la operación del servicio da de alta en una transacción fluida del cliente.</span><span class="sxs-lookup"><span data-stu-id="54019-128">Determines whether the service operation enlists in a client-flowed transaction.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.Impersonation%2A>|<span data-ttu-id="54019-129">Determina si la operación de servicio suplanta la identidad del autor de la llamada.</span><span class="sxs-lookup"><span data-stu-id="54019-129">Determines whether the service operation impersonates the caller's identity.</span></span>|  
|<xref:System.ServiceModel.OperationBehaviorAttribute.ReleaseInstanceMode%2A>|<span data-ttu-id="54019-130">Determina si las instancias del servicio se reciclan en el inicio o final de la llamada de operación de servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-130">Determines whether service instances are recycled at the start or end of the service operation call.</span></span>|  
  
 <span data-ttu-id="54019-131">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="54019-131">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="54019-132">El retraso entre las llamadas es el resultado de las llamadas a `System.Threading.Thread.Sleep()` realizadas en las operaciones del servicio.</span><span class="sxs-lookup"><span data-stu-id="54019-132">The delay between the calls is the result of the calls to `System.Threading.Thread.Sleep()` made in the service operations.</span></span> <span data-ttu-id="54019-133">El resto de los ejemplos de comportamiento explica con más detalle estos comportamientos.</span><span class="sxs-lookup"><span data-stu-id="54019-133">The rest of the behavior samples explain these behaviors in more detail.</span></span> <span data-ttu-id="54019-134">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="54019-134">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="54019-135">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="54019-135">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="54019-136">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="54019-136">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="54019-137">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="54019-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="54019-138">Para ejecutar el ejemplo en una configuración de uno o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="54019-138">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="54019-139">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="54019-139">The samples may already be installed on your machine.</span></span> <span data-ttu-id="54019-140">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="54019-140">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="54019-141">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="54019-141">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="54019-142">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="54019-142">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Default`  
