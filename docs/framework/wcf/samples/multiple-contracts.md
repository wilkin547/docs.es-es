---
title: Contratos múltiples
ms.date: 03/30/2017
ms.assetid: 2bef319b-fe9c-4d49-ac6c-dfb23eb35099
ms.openlocfilehash: acced4bfc79571c78e868b31b0a4db6cfbdea76a
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59295567"
---
# <a name="multiple-contracts"></a><span data-ttu-id="dadd4-102">Contratos múltiples</span><span class="sxs-lookup"><span data-stu-id="dadd4-102">Multiple Contracts</span></span>
<span data-ttu-id="dadd4-103">El ejemplo de contratos múltiples muestra cómo implementar más de un contrato en un servicio y cómo configurar los puntos de conexión para comunicarse con cada uno de los contratos implementados.</span><span class="sxs-lookup"><span data-stu-id="dadd4-103">The Multiple Contracts sample demonstrates how to implement more than one contract on a service and how to configure endpoints for communicating with each of the implemented contracts.</span></span> <span data-ttu-id="dadd4-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="dadd4-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="dadd4-105">El servicio se ha modificado para definir dos contratos: `ICalculator` y `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="dadd4-105">The service has been modified to define two contracts, the `ICalculator` contract and the `ICalculatorSession` contract.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dadd4-106">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="dadd4-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="dadd4-107">La clase de servicio implementa los contratos `ICalculator` e `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="dadd4-107">The service class implements both the `ICalculator` and `ICalculatorSession` contracts.</span></span> <span data-ttu-id="dadd4-108">Dado que uno de los contratos requiere una sesión, el servicio utiliza el modo de instancia <xref:System.ServiceModel.InstanceContextMode.PerSession> para mantener el estado en toda la duración de la sesión.</span><span class="sxs-lookup"><span data-stu-id="dadd4-108">Because one of the contracts requires a session, the service uses the <xref:System.ServiceModel.InstanceContextMode.PerSession> instance mode to maintain the state over the lifetime of the session.</span></span>  
  
 <span data-ttu-id="dadd4-109">La configuración de servicio se ha modificado para definir dos extremos para exponer cada contrato.</span><span class="sxs-lookup"><span data-stu-id="dadd4-109">The service configuration has been modified to define two endpoints to expose each contract.</span></span> <span data-ttu-id="dadd4-110">El extremo `ICalculator` se expone en la dirección base utilizando `basicHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="dadd4-110">The `ICalculator` endpoint is exposed at the base address using a `basicHttpBinding`.</span></span> <span data-ttu-id="dadd4-111">El extremo `ICalculatorSession` se expone en la dirección base/sesión utilizando `wsHttpBinding` con el atributo `bindingConfiguration` establecido en `BindingWithSession`, tal y como se muestra en la configuración de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="dadd4-111">The `ICalculatorSession` endpoint is exposed at the baseaddress/session using a `wsHttpBinding` with the `bindingConfiguration` attribute set to `BindingWithSession`, as shown in the following sample configuration.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <!-- ICalculator endpoint is exposed using BasicBinding at the base  
       address provided by host:   
       http://localhost/servicemodelsamples/service.svc  -->  
  <endpoint address=""  
            binding="basicHttpBinding"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" />  
  <!-- ICalculatorSession endpoint is exposed using BindingWithSession  
       at {baseaddress}/session:  
       http://localhost/servicemodelsamples/service.svc/session -->  
  <endpoint address="session"  
            binding="wsHttpBinding"  
            bindingConfiguration="BindingWithSession"   
           contract="Microsoft.ServiceModel.Samples.ICalculatorSession" />  
  ...  
</service>  
```  
  
 <span data-ttu-id="dadd4-112">El código de cliente generado incluye ahora una clase de cliente para el contrato original `ICalculator` y el nuevo contrato `ICalculatorSession`.</span><span class="sxs-lookup"><span data-stu-id="dadd4-112">The generated client code now includes a client class for both the original `ICalculator` contract and the new `ICalculatorSession` contract.</span></span> <span data-ttu-id="dadd4-113">Se han modificado la configuración de cliente y el código para comunicarse con cada contrato en el extremo de servicio adecuado.</span><span class="sxs-lookup"><span data-stu-id="dadd4-113">The client configuration and code have been modified to communicate with each contract at the appropriate service endpoint.</span></span>  
  
 <span data-ttu-id="dadd4-114">El cliente es una aplicación de consola de Windows (.exe).</span><span class="sxs-lookup"><span data-stu-id="dadd4-114">The client is a console windows application (.exe).</span></span> <span data-ttu-id="dadd4-115">El servicio está hospedado por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="dadd4-115">The service is hosted by Internet Information Services (IIS).</span></span>  
  
 <span data-ttu-id="dadd4-116">La ventana de la consola del cliente muestra las operaciones enviadas a cada uno de los puntos de conexión, primero el punto de conexión básico, seguido por el punto de conexión seguro.</span><span class="sxs-lookup"><span data-stu-id="dadd4-116">The client console window displays the operations sent to each of the endpoints, first the basic endpoint, followed by the secure endpoint.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dadd4-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="dadd4-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="dadd4-118">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadd4-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dadd4-119">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadd4-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="dadd4-120">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dadd4-120">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dadd4-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="dadd4-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="dadd4-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="dadd4-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dadd4-123">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="dadd4-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dadd4-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="dadd4-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\MultipleContracts`  
