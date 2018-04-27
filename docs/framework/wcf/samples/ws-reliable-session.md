---
title: Sesión de confianza de WS
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
caps.latest.revision: 30
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8d7b28968a77f03a622c67acdb58e239593199a2
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="ws-reliable-session"></a><span data-ttu-id="8f8c6-102">Sesión de confianza de WS</span><span class="sxs-lookup"><span data-stu-id="8f8c6-102">WS Reliable Session</span></span>
<span data-ttu-id="8f8c6-103">Este ejemplo muestra el uso de la sesión de confianza. </span><span class="sxs-lookup"><span data-stu-id="8f8c6-103">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="8f8c6-104">Las sesiones de confianza proporcionan compatibilidad para la mensajería y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-104">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="8f8c6-105">La mensajería de confianza reintenta la comunicación en caso de error y permite especificar garantías de entrega, como la llegada en orden de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-105">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="8f8c6-106">Las sesiones mantienen el estado de los clientes entre llamadas.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-106">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="8f8c6-107">El ejemplo implementa las sesiones para mantener el estado del cliente y especifica las convicciones de la entrega en orden.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-107">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8f8c6-108">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="8f8c6-109">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="8f8c6-110">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8f8c6-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="8f8c6-111">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="8f8c6-112">En este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-112">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="8f8c6-113">Las características de sesión fiables están habilitadas y configuradas en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-113">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="8f8c6-114">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-114">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8f8c6-115">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-115">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="8f8c6-116">El ejemplo utiliza el archivo `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-116">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="8f8c6-117">El enlace se especifica en los archivos de configuración para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-117">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="8f8c6-118">El tipo de enlace se especifica en el atributo `binding` del elemento del extremo tal y como se explica en el ejemplo siguiente de configuración.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-118">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="8f8c6-119">El extremo contiene un atributo `bindingConfiguration` que hace referencia a una configuración de enlace denominada "Binding1".</span><span class="sxs-lookup"><span data-stu-id="8f8c6-119">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="8f8c6-120">La configuración de enlace permite que las sesiones confiables estableciendo la `enabled` atributo de la [ \<reliableSession >](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) a `true`.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-120">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../../../docs/framework/configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="8f8c6-121">Las convicciones de la entrega para las sesiones ordenadas se controlan estableciendo el atributo ordenado como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-121">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="8f8c6-122">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-122">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="8f8c6-123">La clase de implementación de servicio implementa <xref:System.ServiceModel.InstanceContextMode.PerSession> que crea instancias para mantener una instancia de clase independiente para cada cliente, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-123">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="8f8c6-124">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="8f8c6-125">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-125">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="8f8c6-126">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="8f8c6-126">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="8f8c6-127">Instale [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mediante el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="8f8c6-127">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="8f8c6-128">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8f8c6-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="8f8c6-129">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8f8c6-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="8f8c6-130">Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="8f8c6-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f8c6-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f8c6-131">See Also</span></span>
