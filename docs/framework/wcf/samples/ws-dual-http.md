---
title: WS Http dual
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 4acf2491c242099f6c8b6c9c01dc18e9c99c9934
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589739"
---
# <a name="ws-dual-http"></a><span data-ttu-id="64ce4-102">WS Http dual</span><span class="sxs-lookup"><span data-stu-id="64ce4-102">WS Dual Http</span></span>

<span data-ttu-id="64ce4-103">El ejemplo Http dual muestra cómo configurar el enlace `WSDualHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="64ce4-103">The Dual Http sample demonstrates how to configure the `WSDualHttpBinding` binding.</span></span> <span data-ttu-id="64ce4-104">Este ejemplo está compuesto de un programa de consola de cliente (.exe) y una biblioteca de servicios (.dll) hospedados por Internet Information Services (IIS).</span><span class="sxs-lookup"><span data-stu-id="64ce4-104">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="64ce4-105">El servicio implementa un contrato dúplex.</span><span class="sxs-lookup"><span data-stu-id="64ce4-105">The service implements a duplex contract.</span></span> <span data-ttu-id="64ce4-106">La interfaz `ICalculatorDuplex`, que expone las operaciones matemáticas (sumar, restar, multiplicar y dividir), define el contrato.</span><span class="sxs-lookup"><span data-stu-id="64ce4-106">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="64ce4-107">En este ejemplo, la interfaz `ICalculatorDuplex` permite al cliente realizar las operaciones matemáticas, calculando un resultado en ejecución sobre la sesión.</span><span class="sxs-lookup"><span data-stu-id="64ce4-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over the session.</span></span> <span data-ttu-id="64ce4-108">Independientemente, el servicio devuelve los resultados en la interfaz `ICalculatorDuplexCallback`.</span><span class="sxs-lookup"><span data-stu-id="64ce4-108">Independently, the service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="64ce4-109">Un contrato dúplex requiere una sesión, porque se debe establecer un contexto para poner en correlación el conjunto de mensajes que se envían entre el cliente y el servicio.</span><span class="sxs-lookup"><span data-stu-id="64ce4-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between client and service.</span></span> <span data-ttu-id="64ce4-110">El enlace `WSDualHttpBinding` admite la comunicación dúplex.</span><span class="sxs-lookup"><span data-stu-id="64ce4-110">The `WSDualHttpBinding` binding supports duplex communication.</span></span>

> [!NOTE]
> <span data-ttu-id="64ce4-111">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="64ce4-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="64ce4-112">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="64ce4-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="64ce4-113">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="64ce4-113">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="64ce4-114">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="64ce4-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="64ce4-115">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="64ce4-115">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

<span data-ttu-id="64ce4-116">Para configurar un punto de conexión de servicio con `WSDualHttpBinding`, especifique el enlace en la configuración del punto de conexión según se muestra.</span><span class="sxs-lookup"><span data-stu-id="64ce4-116">To configure a service endpoint with the `WSDualHttpBinding`, specify the binding in the endpoint configuration as shown.</span></span>

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

<span data-ttu-id="64ce4-117">En el cliente, debe configurar una dirección que el servidor pueda utilizar para conectarse al cliente, como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="64ce4-117">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

<span data-ttu-id="64ce4-118">Al ejecutar el ejemplo, las solicitudes y respuestas de la operación se muestran en la ventana de la consola del cliente.</span><span class="sxs-lookup"><span data-stu-id="64ce4-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="64ce4-119">Presione ENTRAR en la ventana de cliente para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="64ce4-119">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="64ce4-120">Al ejecutar el ejemplo, se ven los mensajes devueltos al cliente en la interfaz de devolución de llamada enviada del servicio.</span><span class="sxs-lookup"><span data-stu-id="64ce4-120">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="64ce4-121">Se muestra cada resultado intermedio, seguido por la ecuación completa en la realización de todas las operaciones.</span><span class="sxs-lookup"><span data-stu-id="64ce4-121">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="64ce4-122">Presione Entrar para cerrar el cliente.</span><span class="sxs-lookup"><span data-stu-id="64ce4-122">Press ENTER to shut down the client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="64ce4-123">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="64ce4-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="64ce4-124">Instale ASP.NET 4,0 con el siguiente comando.</span><span class="sxs-lookup"><span data-stu-id="64ce4-124">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="64ce4-125">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64ce4-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="64ce4-126">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64ce4-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="64ce4-127">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="64ce4-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="64ce4-128">Al ejecutar el cliente en una configuración entre equipos, asegúrese de reemplazar localhost en el `address` atributo del elemento [ \<endpoint> \<client> de](../../configure-apps/file-schema/wcf/endpoint-of-client.md) y el `clientBaseAddress` atributo del [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) elemento del [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) elemento con el nombre del equipo adecuado, como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="64ce4-128">When running the client in a cross-machine configuration, be sure to replace localhost in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element of the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown:</span></span>

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```
