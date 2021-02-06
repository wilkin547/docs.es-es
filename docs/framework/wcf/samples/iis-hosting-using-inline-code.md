---
description: 'Más información acerca de: hospedaje de IIS mediante código en línea'
title: Hospedaje de IIS utilizando código en línea
ms.date: 03/30/2017
helpviewer_keywords:
- Web hosted service
- IIS Hosting Using Inline Code Sample [Windows Communication Foundation]
ms.assetid: 56fe3687-a34b-4661-8e30-b33770f413fa
ms.openlocfilehash: 58c2e119ad49f56d015290747ab247bd45ff4d23
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631871"
---
# <a name="iis-hosting-using-inline-code"></a><span data-ttu-id="02acc-103">Hospedaje de IIS utilizando código en línea</span><span class="sxs-lookup"><span data-stu-id="02acc-103">IIS Hosting Using Inline Code</span></span>

<span data-ttu-id="02acc-104">Este ejemplo muestra cómo implementar un servicio hospedado por Internet Information Services (IIS), donde el código de servicio está contenido en línea en un archivo .svc y se compila a petición.</span><span class="sxs-lookup"><span data-stu-id="02acc-104">This sample demonstrates how to implement a service hosted by Internet Information Services (IIS), where the service code is contained in-line in a .svc file and is compiled on demand.</span></span> <span data-ttu-id="02acc-105">El código de servicio también se puede implementar directamente en los archivos de código de origen situado en el directorio \App_Code de la aplicación o compilado en un ensamblado implementado en \bin.</span><span class="sxs-lookup"><span data-stu-id="02acc-105">Service code can also be implemented directly in source code files located in the application's \App_Code directory, or compiled into assembly deployed in \bin.</span></span> <span data-ttu-id="02acc-106">Este ejemplo no muestra estas técnicas.</span><span class="sxs-lookup"><span data-stu-id="02acc-106">This sample does not demonstrate these techniques.</span></span>

> [!NOTE]
> <span data-ttu-id="02acc-107">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="02acc-107">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="02acc-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="02acc-108">The samples may already be installed on your computer.</span></span> <span data-ttu-id="02acc-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="02acc-109">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="02acc-110">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="02acc-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="02acc-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="02acc-111">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WebHost\InlineCode`

<span data-ttu-id="02acc-112">El ejemplo muestra un servicio típico que implementa un contrato que define un modelo de comunicación solicitud-respuesta.</span><span class="sxs-lookup"><span data-stu-id="02acc-112">The sample demonstrates a typical service that implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="02acc-113">El servicio se hospeda en IIS y el código de servicio se contiene completamente en el archivo Service.svc.</span><span class="sxs-lookup"><span data-stu-id="02acc-113">The service is hosted in IIS and the service code is entirely contained in the Service.svc file.</span></span> <span data-ttu-id="02acc-114">El primer mensaje enviado al servicio permite que éste se active en el host y se compile a petición.</span><span class="sxs-lookup"><span data-stu-id="02acc-114">The service is host-activated and compiled on-demand by the first message sent to the service.</span></span> <span data-ttu-id="02acc-115">No es necesario realizar una compilación previa.</span><span class="sxs-lookup"><span data-stu-id="02acc-115">There is no pre-compilation necessary.</span></span> <span data-ttu-id="02acc-116">El servicio implementa un contrato `ICalculator` tal y como se define en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="02acc-116">The service implements an `ICalculator` contract as defined in the following code:</span></span>

```csharp
// Define a service contract.
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]
    public interface ICalculator
{
    [OperationContract]
    double Add(double n1, double n2);
    [OperationContract]
    double Subtract(double n1, double n2);
    [OperationContract]
    double Multiply(double n1, double n2);
    [OperationContract]
    double Divide(double n1, double n2);
}
```

<span data-ttu-id="02acc-117">La implementación del servicio calcula y devuelve el resultado adecuado.</span><span class="sxs-lookup"><span data-stu-id="02acc-117">The service implementation calculates and returns the appropriate result.</span></span>

`<%@ServiceHost language=c# Debug="true" Service="Microsoft.ServiceModel.Samples.CalculatorService" %>`

```csharp
// Service class that implements the service contract.
public class CalculatorService : ICalculator
{
    public double Add(double n1, double n2)
    {
        return n1 + n2;
    }
    public double Subtract(double n1, double n2)
    {
        return n1 - n2;
    }
    public double Multiply(double n1, double n2)
    {
        return n1 * n2;
    }
    public double Divide(double n1, double n2)
    {
        return n1 / n2;
    }
}
```

<span data-ttu-id="02acc-118">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="02acc-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="02acc-119">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="02acc-119">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="02acc-120">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="02acc-120">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="02acc-121">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02acc-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="02acc-122">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02acc-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="02acc-123">Una vez compilada la solución, ejecute setup.bat para configurar la aplicación ServiceModelSamples en IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="02acc-123">After the solution has been built, run setup.bat to set up the ServiceModelSamples Application in IIS 7.0.</span></span> <span data-ttu-id="02acc-124">El directorio ServiceModelSamples debería aparecer ahora como una aplicación de IIS 7,0.</span><span class="sxs-lookup"><span data-stu-id="02acc-124">The ServiceModelSamples directory should now appear as an IIS 7.0 Application.</span></span>

4. <span data-ttu-id="02acc-125">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="02acc-125">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span> <span data-ttu-id="02acc-126">Para obtener un ejemplo sobre cómo crear una aplicación cliente que pueda llamar a este servicio, consulte [Cómo: crear un cliente](../how-to-create-a-wcf-client.md).</span><span class="sxs-lookup"><span data-stu-id="02acc-126">For an example on how to create a client application that can call this service, see [How to: Create a Client](../how-to-create-a-wcf-client.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="02acc-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="02acc-127">See also</span></span>

- <span data-ttu-id="02acc-128">[Ejemplos de hospedaje y persistencia de AppFabric](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="02acc-128">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
