---
title: Limitación de peticiones
ms.date: 03/30/2017
helpviewer_keywords:
- service behaviors, throttling sample
- Throttling Sample [Windows Communication Foundation]
ms.assetid: 40bb3582-8ae9-4410-96f0-6c515bfaf47c
ms.openlocfilehash: 14d16a644aa89d5da9ec1adcbdef48367ddc1205
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74715692"
---
# <a name="throttling"></a><span data-ttu-id="4c036-102">Limitación de peticiones</span><span class="sxs-lookup"><span data-stu-id="4c036-102">Throttling</span></span>
<span data-ttu-id="4c036-103">El ejemplo de limitación de peticiones muestra el uso de la limitación de controles.</span><span class="sxs-lookup"><span data-stu-id="4c036-103">The Throttling sample demonstrates the use of throttling controls.</span></span> <span data-ttu-id="4c036-104">Los controles de limitación de peticiones establecen límites en el número de llamadas simultáneas, instancias o sesiones para evitar el consumo excesivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="4c036-104">Throttling controls place limits on the number of concurrent calls, instances, or sessions to prevent over-consumption of resources.</span></span> <span data-ttu-id="4c036-105">El comportamiento de la limitación de peticiones se especifica en los valores del archivo de configuración del servicio.</span><span class="sxs-lookup"><span data-stu-id="4c036-105">Throttling behavior is specified in service configuration file settings.</span></span> <span data-ttu-id="4c036-106">Este ejemplo se basa en el [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) que implementa un servicio de calculadora.</span><span class="sxs-lookup"><span data-stu-id="4c036-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
 <span data-ttu-id="4c036-107">En este ejemplo, el cliente es una aplicación de consola (.exe) y los Servicios de Internet Information Server (IIS) hospedan el servicio.</span><span class="sxs-lookup"><span data-stu-id="4c036-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4c036-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="4c036-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="4c036-109">El archivo de configuración de servicio especifica los controles de limitación en un [\<serviceThrottling >](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), tal y como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="4c036-109">The service configuration file specifies throttling controls in a [\<serviceThrottling>](../../../../docs/framework/configure-apps/file-schema/wcf/servicethrottling.md), as shown in the following sample configuration.</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <serviceDebug includeExceptionDetailInFaults="False" />  
      <serviceMetadata httpGetEnabled="True"/>  
      <!-- Specify throttling behavior -->  
    <serviceThrottling maxConcurrentCalls="2"  
                       maxConcurrentInstances="10"/>  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="4c036-110">Tal y como se ha configurado, el servicio limita las llamadas máximas simultáneas a 2 y el número máximo de instancias simultáneas a 10.</span><span class="sxs-lookup"><span data-stu-id="4c036-110">As configured, the service limits the maximum concurrent calls to 2, and the maximum number of concurrent instances to 10.</span></span>  
  
 <span data-ttu-id="4c036-111">Para mostrar la limitación de peticiones, definimos un período de suspensión en los métodos de servicio de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="4c036-111">In order to demonstrate throttling we define a sleep time on the service methods as follows:</span></span>  
  
```csharp
public double Add(double n1, double n2)  
{  
    System.Threading.Thread.Sleep(2000);  
    return n1 + n2;  
}  
```  
  
 <span data-ttu-id="4c036-112">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="4c036-112">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4c036-113">Se ejecutan a la vez los métodos Sumar y Restar y los métodos Multiplicar y Dividir también se ejecutan a la vez siempre que no se puedan ejecutar más de dos métodos a la vez, con lo que se produciría la limitación de peticiones.</span><span class="sxs-lookup"><span data-stu-id="4c036-113">The Add and Subtract methods are executed concurrently and the Multiply and Divide methods are executed concurrently proving that not more than 2 methods can be executed concurrently thus demonstrating throttling.</span></span>  
  
```console  
Press <ENTER> to terminate client.  
Add(100,15.99)  
Subtract(145,76.54)  
Multiply(9,81.25)  
Divide(22,7)  
  
Add Result: 115.99  
Subtract Result: 68.46  
Multiply Result: 731.25  
Divide Result: 3.14285714285714  
  
Press any key to continue . . .  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c036-114">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c036-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="4c036-115">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c036-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="4c036-116">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c036-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="4c036-117">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c036-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="4c036-118">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4c036-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4c036-119">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4c036-119">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="4c036-120">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c036-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c036-121">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4c036-121">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Throttling`  
