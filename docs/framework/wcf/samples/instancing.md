---
description: 'Más información acerca de: creación de instancias'
title: Instancing
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, instancing sample
- Instancing Sample [Windows Communication Foundation]
ms.assetid: c290fa54-f6ae-45a1-9186-d9504ebc6ee6
ms.openlocfilehash: 88cff6912e3285370a456d5d8575c995ff15ef57
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726460"
---
# <a name="instancing"></a><span data-ttu-id="2f641-103">Instancing</span><span class="sxs-lookup"><span data-stu-id="2f641-103">Instancing</span></span>

<span data-ttu-id="2f641-104">El ejemplo de la creación de instancias muestra el valor de comportamiento de creación de instancias, que controla cómo las instancias de una clase de servicio se crean en respuesta a las solicitudes de cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-104">The Instancing sample demonstrates the instancing behavior setting, which controls how instances of a service class are created in response to client requests.</span></span> <span data-ttu-id="2f641-105">El ejemplo se basa en el [Introducción](getting-started-sample.md), que implementa el `ICalculator` contrato de servicio.</span><span class="sxs-lookup"><span data-stu-id="2f641-105">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="2f641-106">Este ejemplo define un nuevo contrato, `ICalculatorInstance`, que se hereda de `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="2f641-106">This sample defines a new contract, `ICalculatorInstance`, which inherits from `ICalculator`.</span></span> <span data-ttu-id="2f641-107">El contrato especificado por `ICalculatorInstance` proporciona tres operaciones adicionales para inspeccionar el estado de la instancia del servicio.</span><span class="sxs-lookup"><span data-stu-id="2f641-107">The contract specified by `ICalculatorInstance` provides three additional operations for inspecting the state of the service instance.</span></span> <span data-ttu-id="2f641-108">Modificando el valor de la creación de instancias, puede observar el cambio en el comportamiento ejecutando el cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-108">By altering the instancing setting, you can observe the change in behavior by running the client.</span></span>  
  
 <span data-ttu-id="2f641-109">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="2f641-109">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2f641-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="2f641-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="2f641-111">Los siguientes modos de creación de instancias están disponibles:</span><span class="sxs-lookup"><span data-stu-id="2f641-111">The following instancing modes are available:</span></span>  
  
- <span data-ttu-id="2f641-112"><xref:System.ServiceModel.InstanceContextMode.PerCall>: Se crea un Nuevo servicio para cada solicitud de cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-112"><xref:System.ServiceModel.InstanceContextMode.PerCall>: A new service instance is created for each client request.</span></span>  
  
- <span data-ttu-id="2f641-113"><xref:System.ServiceModel.InstanceContextMode.PerSession>: Se crea una nueva instancia para cada nueva sesión del cliente y se mantiene durante el tiempo que dure esa sesión (esto requiere un enlace que admita una sesión).</span><span class="sxs-lookup"><span data-stu-id="2f641-113"><xref:System.ServiceModel.InstanceContextMode.PerSession>: A new instance is created for each new client session, and maintained for the lifetime of that session (requires a binding that supports session).</span></span>  
  
- <span data-ttu-id="2f641-114"><xref:System.ServiceModel.InstanceContextMode.Single>: Una única instancia de la clase del servicio administra todas las solicitudes de cliente durante la vida de la aplicación</span><span class="sxs-lookup"><span data-stu-id="2f641-114"><xref:System.ServiceModel.InstanceContextMode.Single>: A single instance of the service class handles all client requests for the lifetime of the application.</span></span>  
  
 <span data-ttu-id="2f641-115">La clase de servicio especifica el comportamiento de la creación de instancias con el atributo `[ServiceBehavior(InstanceContextMode=<setting>)]` como se muestra en el ejemplo de código que sigue.</span><span class="sxs-lookup"><span data-stu-id="2f641-115">The service class specifies instancing behavior with the `[ServiceBehavior(InstanceContextMode=<setting>)]` attribute as shown in the code sample that follows.</span></span> <span data-ttu-id="2f641-116">Cambiando las líneas que se marcan con comentarios, se puede observar el comportamiento de cada uno de los modos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="2f641-116">By changing which lines are commented out, you can observe the behavior of each of the instance modes.</span></span> <span data-ttu-id="2f641-117">Recuerde recompilar el servicio después de cambiar el modo de la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="2f641-117">Remember to rebuild the service after changing the instancing mode.</span></span> <span data-ttu-id="2f641-118">No hay ninguna configuración relacionada con la creación de instancias para especificar en el cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-118">There are no instancing-related settings to specify on the client.</span></span>  
  
```csharp
// Enable one of the following instance modes to compare instancing behaviors.  
 [ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)]  
  
// PerCall creates a new instance for each operation.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.PerCall)]  
  
// Singleton creates a single instance for application lifetime.  
//[ServiceBehavior(InstanceContextMode = InstanceContextMode.Single)]  
public class CalculatorService : ICalculatorInstance  
{  
    static Object syncObject = new object();  
    static int instanceCount;  
    int instanceId;  
    int operationCount;  
  
    public CalculatorService()  
    {  
        lock (syncObject)  
        {  
            instanceCount++;  
            instanceId = instanceCount;  
        }  
    }  
  
    public double Add(double n1, double n2)  
    {  
        operationCount++;  
        return n1 + n2;  
    }  
  
    public double Subtract(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 - n2;  
    }  
  
    public double Multiply(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 * n2;  
    }  
  
    public double Divide(double n1, double n2)  
    {  
        Interlocked.Increment(ref operationCount);  
        return n1 / n2;  
    }  
  
    public string GetInstanceContextMode()  
    {   // Return the InstanceContextMode of the service  
        ServiceHost host = (ServiceHost)OperationContext.Current.Host;  
        ServiceBehaviorAttribute behavior = host.Description.Behaviors.Find<ServiceBehaviorAttribute>();  
        return behavior.InstanceContextMode.ToString();  
    }  
  
    public int GetInstanceId()  
    {   // Return the id for this instance  
        return instanceId;  
    }  
  
    public int GetOperationCount()  
    {   // Return the number of ICalculator operations performed
        // on this instance  
        lock (syncObject)  
        {  
            return operationCount;  
        }  
    }  
}  
  
static void Main()  
{  
    // Create a client.  
    CalculatorInstanceClient client = new CalculatorInstanceClient();  
    string instanceMode = client.GetInstanceContextMode();  
    Console.WriteLine("InstanceContextMode: {0}", instanceMode);  
    DoCalculations(client);  
  
    // Create a second client.  
    CalculatorInstanceClient client2 = new CalculatorInstanceClient();  
  
    DoCalculations(client2);  
  
    Console.WriteLine();  
    Console.WriteLine("Press <ENTER> to terminate client.");  
    Console.ReadLine();  
}  
```  
  
 <span data-ttu-id="2f641-119">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="2f641-120">Se muestra el modo de la instancia en el cual el servicio se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="2f641-120">The instance mode the service is running under is displayed.</span></span> <span data-ttu-id="2f641-121">Tras cada operación, se muestran el Id. de la instancia y el recuento de la operación, para reflejar el comportamiento del modo de la creación de instancias.</span><span class="sxs-lookup"><span data-stu-id="2f641-121">After each operation, the instance ID and operation count are displayed to reflect the behavior of the instancing mode.</span></span> <span data-ttu-id="2f641-122">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="2f641-122">Press ENTER in the client window to shut down the client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="2f641-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="2f641-123">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="2f641-124">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2f641-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="2f641-125">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2f641-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="2f641-126">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="2f641-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="2f641-127">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="2f641-127">The samples may already be installed on your machine.</span></span> <span data-ttu-id="2f641-128">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="2f641-128">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="2f641-129">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="2f641-129">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="2f641-130">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="2f641-130">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Instancing`  
