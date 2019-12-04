---
title: NetNamedPipeBinding
ms.date: 03/30/2017
helpviewer_keywords:
- Net Profile Named Pipe
ms.assetid: e78e845f-c325-46e2-927d-81616f97f7d5
ms.openlocfilehash: 5904a5b61c0cc472c40eb2b4967815d5e6add195
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2019
ms.locfileid: "74714671"
---
# <a name="netnamedpipebinding"></a><span data-ttu-id="b9d75-102">NetNamedPipeBinding</span><span class="sxs-lookup"><span data-stu-id="b9d75-102">NetNamedPipeBinding</span></span>
<span data-ttu-id="b9d75-103">El ejemplo muestra el enlace `netNamedPipeBinding`, que proporciona la comunicación entre procesos del mismo equipo.</span><span class="sxs-lookup"><span data-stu-id="b9d75-103">This sample demonstrates the `netNamedPipeBinding` binding, which provides cross-process communication on the same machine.</span></span> <span data-ttu-id="b9d75-104">Las canalizaciones con nombre no funcionan entre equipos.</span><span class="sxs-lookup"><span data-stu-id="b9d75-104">Named pipes do not work across machines.</span></span> <span data-ttu-id="b9d75-105">Este ejemplo se basa en el servicio de calculadora de [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) .</span><span class="sxs-lookup"><span data-stu-id="b9d75-105">This sample is based on The [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) calculator service.</span></span>  
  
 <span data-ttu-id="b9d75-106">En este ejemplo, el servicio es hospedado por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="b9d75-106">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="b9d75-107">El cliente y el servicio son aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="b9d75-107">Both the client and the service are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9d75-108">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="b9d75-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b9d75-109">El enlace se especifica en los archivos de configuración para el cliente y servicio.</span><span class="sxs-lookup"><span data-stu-id="b9d75-109">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="b9d75-110">El tipo de enlace se especifica en el atributo `binding` del [punto de conexión de\<](../../configure-apps/file-schema/wcf/endpoint-element.md) o [\<extremo > de \<elemento > cliente](../../configure-apps/file-schema/wcf/endpoint-of-client.md) , tal y como se muestra en la configuración del ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9d75-110">The binding type is specified in the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) or [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element, as shown in the following sample configuration:</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="b9d75-111">El ejemplo anterior muestra cómo configurar un extremo para utilizar el enlace `netNamedPipeBinding` con la configuración predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b9d75-111">The previous sample shows how to configure an endpoint to use the `netNamedPipeBinding` binding with the default settings.</span></span> <span data-ttu-id="b9d75-112">Si desea configurar el enlace `netNamedPipeBinding` y cambiar algunos de sus valores, debe definir una configuración de enlace.</span><span class="sxs-lookup"><span data-stu-id="b9d75-112">If you want to configure the `netNamedPipeBinding` binding and change some of its settings, you must define a binding configuration.</span></span> <span data-ttu-id="b9d75-113">El extremo debe hacer referencia a la configuración de enlace por el nombre con un atributo `bindingConfiguration`.</span><span class="sxs-lookup"><span data-stu-id="b9d75-113">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span>  
  
```xml  
<endpoint address="net.pipe://localhost/ServiceModelSamples/service"  
          binding="netNamedPipeBinding"  
          bindingConfiguration="Binding1"   
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="b9d75-114">En este ejemplo la configuración de enlace se denomina `Binding1`, y responde a la siguiente definición:</span><span class="sxs-lookup"><span data-stu-id="b9d75-114">In this sample, the binding configuration is named `Binding1` and has the following definition:</span></span>  
  
```xml  
<bindings>  
  <!--   
        Following is the expanded configuration section for a NetNamedPipeBinding.  
        Each property is configured with the default value.  
     -->  
  <netNamedPipeBinding>  
    <binding name="Binding1"   
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"   
             receiveTimeout="00:10:00"   
             sendTimeout="00:01:00"  
             transactionFlow="false"   
             transferMode="Buffered"   
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"   
             maxBufferPoolSize="524288"  
             maxBufferSize="65536"   
             maxConnections="10"   
             maxReceivedMessageSize="65536">  
      <security mode="Transport">  
        <transport protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netNamedPipeBinding>  
</bindings>  
```  
  
 <span data-ttu-id="b9d75-115">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="b9d75-115">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b9d75-116">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="b9d75-116">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b9d75-117">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="b9d75-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b9d75-118">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b9d75-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b9d75-119">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b9d75-119">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b9d75-120">Para ejecutar el ejemplo en una configuración de un solo equipo, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b9d75-120">To run the sample in a single machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b9d75-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="b9d75-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9d75-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="b9d75-122">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="b9d75-123">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos de Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b9d75-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9d75-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="b9d75-124">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\NamedPipe`  
