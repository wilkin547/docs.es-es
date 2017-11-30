---
title: Probar internamente
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Self hosted service
- Self Host Sample [Windows Communication Foundation]
ms.assetid: 05e68661-1ddf-4abf-a899-9bb1b8272a5b
caps.latest.revision: "38"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: dc1a25bcf6f840f2ad5939d812b23c56c7966d93
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="self-host"></a><span data-ttu-id="0c40b-102">Probar internamente</span><span class="sxs-lookup"><span data-stu-id="0c40b-102">Self-Host</span></span>
<span data-ttu-id="0c40b-103">Este ejemplo muestra cómo implementar un servicio autohospedado en una aplicación de la consola.</span><span class="sxs-lookup"><span data-stu-id="0c40b-103">This sample demonstrates how to implement a self-hosted service in a console application.</span></span> <span data-ttu-id="0c40b-104">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="0c40b-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="0c40b-105">Se ha cambiado el nombre al archivo de configuración de servicio de Web.config a App.config y se ha modificado para configurar una dirección base, que el host utiliza.</span><span class="sxs-lookup"><span data-stu-id="0c40b-105">The service configuration file has been renamed from Web.config to App.config and modified to configure a base address, which the host uses.</span></span> <span data-ttu-id="0c40b-106">El código fuente del servicio se ha modificado para implementar una función `Main` estática que crea y abre un host de servicio que proporciona la dirección base configurada.</span><span class="sxs-lookup"><span data-stu-id="0c40b-106">The service source code has been modified to implement a static `Main` function that creates and opens a service host that provides the configured base address.</span></span> <span data-ttu-id="0c40b-107">La implementación del servicio se ha modificado para escribir la salida en la consola para cada operación.</span><span class="sxs-lookup"><span data-stu-id="0c40b-107">The service implementation has been modified to write output to the console for each operation.</span></span> <span data-ttu-id="0c40b-108">No se ha modificado el cliente, salvo para configurar la dirección del extremo correcta del servicio.</span><span class="sxs-lookup"><span data-stu-id="0c40b-108">The client has been unmodified, except for configuring the correct endpoint address of the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0c40b-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="0c40b-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0c40b-110">El ejemplo implementa una función principal estática para crear <xref:System.ServiceModel.ServiceHost> para el tipo `CalculatorService` determinado, como se muestra en el código de ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="0c40b-110">The sample implements a static main function to create a <xref:System.ServiceModel.ServiceHost> for the given `CalculatorService` type, as shown in the following sample code.</span></span>  
  
```  
// Host the service within this EXE console application.  
public static void Main()  
{  
    // Create a ServiceHost for the CalculatorService type.  
    using (ServiceHost serviceHost =   
           new ServiceHost(typeof(CalculatorService)))  
    {  
        // Open the ServiceHost to create listeners   
        // and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
    }  
}  
```  
  
 <span data-ttu-id="0c40b-111">Cuando un servicio se hospeda en Internet Information Services (IIS) o el Servicio de activación de procesos de Windows (WAS), el entorno de hospedaje proporciona la dirección base del servicio.</span><span class="sxs-lookup"><span data-stu-id="0c40b-111">When a service is hosted in Internet Information Services (IIS) or Windows Process Activation Service (WAS), the base address of the service is provided by the hosting environment.</span></span> <span data-ttu-id="0c40b-112">En el caso de que sea autohospedado, deberá especificar la dirección base.</span><span class="sxs-lookup"><span data-stu-id="0c40b-112">In the self-hosted case, you must specify the base address yourself.</span></span> <span data-ttu-id="0c40b-113">Esto se hace mediante el `add` elemento, el elemento secundario de [ \<baseAddresses >](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), elemento secundario de [ \<host >](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), elemento secundario de [ \<servicio > ](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="0c40b-113">This is done using the `add` element, child of [\<baseAddresses>](../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md), child of [\<host>](../../../../docs/framework/configure-apps/file-schema/wcf/host.md), child of [\<service>](../../../../docs/framework/configure-apps/file-schema/wcf/service.md) as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service   
    name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
    </baseAddresses>  
  </host>  
  ...  
</service>  
```  
  
 <span data-ttu-id="0c40b-114">Al ejecutar el ejemplo, las solicitudes y las respuestas de operación se muestran tanto en la ventanas de la consola del cliente como del servicio.</span><span class="sxs-lookup"><span data-stu-id="0c40b-114">When you run the sample, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="0c40b-115">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="0c40b-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0c40b-116">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="0c40b-116">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="0c40b-117">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c40b-117">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="0c40b-118">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c40b-118">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="0c40b-119">Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0c40b-119">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c40b-120">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="0c40b-120">The samples may already be installed on your computer.</span></span> <span data-ttu-id="0c40b-121">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="0c40b-121">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0c40b-122">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0c40b-122">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0c40b-123">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="0c40b-123">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\SelfHost`  
  
## <a name="see-also"></a><span data-ttu-id="0c40b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c40b-124">See Also</span></span>  
 [<span data-ttu-id="0c40b-125">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="0c40b-125">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
