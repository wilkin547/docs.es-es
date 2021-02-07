---
description: 'Más información acerca de: WS Reliable Session'
title: Sesión de confianza de WS
ms.date: 03/30/2017
helpviewer_keywords:
- Reliable session
ms.assetid: 86e914f2-060b-432b-bd17-333695317745
ms.openlocfilehash: a8ccdefd3ef585e3ae164246d69e5cc004390728
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99714955"
---
# <a name="ws-reliable-session"></a><span data-ttu-id="d9a7d-103">Sesión de confianza de WS</span><span class="sxs-lookup"><span data-stu-id="d9a7d-103">WS Reliable Session</span></span>

<span data-ttu-id="d9a7d-104">Este ejemplo muestra el uso de la sesión de confianza. </span><span class="sxs-lookup"><span data-stu-id="d9a7d-104">This sample demonstrates the use of reliable sessions.</span></span> <span data-ttu-id="d9a7d-105">Las sesiones de confianza proporcionan compatibilidad para la mensajería y las sesiones de confianza.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-105">Reliable sessions provide support for reliable messaging and sessions.</span></span> <span data-ttu-id="d9a7d-106">La mensajería de confianza reintenta la comunicación en caso de error y permite especificar garantías de entrega, como la llegada en orden de los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-106">Reliable messaging retries communication on failure and allows delivery assurances to be specified, such as in-order arrival of messages.</span></span> <span data-ttu-id="d9a7d-107">Las sesiones mantienen el estado de los clientes entre llamadas.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-107">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="d9a7d-108">El ejemplo implementa las sesiones para mantener el estado del cliente y especifica las convicciones de la entrega en orden.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-108">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d9a7d-109">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d9a7d-110">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-110">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d9a7d-111">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d9a7d-112">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-112">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsReliableSession`  
  
 <span data-ttu-id="d9a7d-113">Este ejemplo se basa en el [Introducción](getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-113">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="d9a7d-114">Las características de sesión fiables están habilitadas y configuradas en los archivos de configuración de la aplicación para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-114">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>  
  
 <span data-ttu-id="d9a7d-115">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-115">In this sample, the service is hosted in Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d9a7d-116">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-116">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="d9a7d-117">El ejemplo utiliza el archivo `wsHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-117">The sample uses the `wsHttpBinding`.</span></span> <span data-ttu-id="d9a7d-118">El enlace se especifica en los archivos de configuración para el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-118">The binding is specified in the configuration files for both the client and service.</span></span> <span data-ttu-id="d9a7d-119">El tipo de enlace se especifica en el atributo `binding` del elemento del punto de conexión tal y como se explica en el ejemplo siguiente de configuración.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-119">The binding type is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="wsHttpBinding"  
          bindingConfiguration="Binding1"
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="d9a7d-120">El punto de conexión contiene un atributo `bindingConfiguration` que hace referencia a una configuración de enlace denominada "Binding1".</span><span class="sxs-lookup"><span data-stu-id="d9a7d-120">The endpoint contains a `bindingConfiguration` attribute that references a binding configuration named "Binding1."</span></span> <span data-ttu-id="d9a7d-121">La configuración de enlace habilita las sesiones confiables estableciendo el `enabled` atributo de [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) en `true` .</span><span class="sxs-lookup"><span data-stu-id="d9a7d-121">The binding configuration enables reliable sessions by setting the `enabled` attribute of the [\<reliableSession>](../../configure-apps/file-schema/wcf/reliablesession.md) to `true`.</span></span> <span data-ttu-id="d9a7d-122">Las convicciones de la entrega para las sesiones ordenadas se controlan estableciendo el atributo ordenado como `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-122">Delivery assurances for ordered sessions are controlled by setting the ordered attribute to `true` or `false`.</span></span> <span data-ttu-id="d9a7d-123">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-123">The default is `true`.</span></span>  
  
```xml  
<bindings>  
    <wsHttpBinding>  
        <binding name="Binding1">  
            <reliableSession enabled="true" />  
        </binding>  
    </wsHttpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="d9a7d-124">La clase de implementación de servicio implementa <xref:System.ServiceModel.InstanceContextMode.PerSession> que crea instancias para mantener una instancia de clase independiente para cada cliente, como se muestra en el código muestra siguiente.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-124">The service implementation class implements <xref:System.ServiceModel.InstanceContextMode.PerSession> instancing to maintain a separate class instance for each client, as shown in the following sample code.</span></span>  

```csharp
[ServiceBehavior(InstanceContextMode=InstanceContextMode.PerSession)] public class CalculatorService : ICalculator  
{  
    ...  
}  
```
  
 <span data-ttu-id="d9a7d-125">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="d9a7d-126">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-126">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d9a7d-127">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="d9a7d-127">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d9a7d-128">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="d9a7d-128">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="d9a7d-129">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d9a7d-129">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="d9a7d-130">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d9a7d-130">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="d9a7d-131">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d9a7d-131">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
