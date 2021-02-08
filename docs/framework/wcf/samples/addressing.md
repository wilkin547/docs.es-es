---
description: 'Más información acerca de: direccionamiento'
title: Direccionamiento
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 40c13515f0a53e7e8e4dbf10708cebe0b2886a6f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99779184"
---
# <a name="addressing"></a><span data-ttu-id="f04de-103">Direccionamiento</span><span class="sxs-lookup"><span data-stu-id="f04de-103">Addressing</span></span>

<span data-ttu-id="f04de-104">El ejemplo de direccionamiento muestra varios aspectos y características de direcciones del extremo.</span><span class="sxs-lookup"><span data-stu-id="f04de-104">The Addressing sample demonstrates various aspects and features of endpoint addresses.</span></span> <span data-ttu-id="f04de-105">El ejemplo se basa en el [Introducción](getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="f04de-105">The sample is based on the [Getting Started](getting-started-sample.md).</span></span> <span data-ttu-id="f04de-106">En este ejemplo, el servicio es hospedado por sí mismo.</span><span class="sxs-lookup"><span data-stu-id="f04de-106">In this sample the service is self-hosted.</span></span> <span data-ttu-id="f04de-107">El cliente y el servicio son aplicaciones de consola.</span><span class="sxs-lookup"><span data-stu-id="f04de-107">Both the service and the client are console applications.</span></span> <span data-ttu-id="f04de-108">El servicio define varios puntos de conexión mediante una combinación de direcciones del punto de conexión absolutas y relativas.</span><span class="sxs-lookup"><span data-stu-id="f04de-108">The service defines multiple endpoints using a combination of relative and absolute endpoint addresses.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f04de-109">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="f04de-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="f04de-110">El archivo de configuración de servicio especifica una dirección base y cuatro puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f04de-110">The service configuration file specifies a base address and four endpoints.</span></span> <span data-ttu-id="f04de-111">La dirección base se especifica utilizando el elemento agregar, bajo el servicio/host/baseAddresses como se muestra en la configuración del ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f04de-111">The base address is specified using the add element, under service/host/baseAddresses as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 <span data-ttu-id="f04de-112">La primera definición de punto de conexión mostrada en el siguiente ejemplo de configuración especifica una dirección relativa, lo cual significa que la dirección del punto de conexión es una combinación de la dirección base y la dirección relativa siguiendo las reglas de composición de identificadores uniformes de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="f04de-112">The first endpoint definition shown in the following sample configuration specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of URI composition.</span></span>  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="f04de-113">En este caso, la dirección relativa está vacía (""), por lo que la dirección del punto de conexión es igual a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="f04de-113">In this case, the relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="f04de-114">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service` .</span><span class="sxs-lookup"><span data-stu-id="f04de-114">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>
  
 <span data-ttu-id="f04de-115">La segunda definición de extremo también especifica una dirección relativa, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f04de-115">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span>  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="f04de-116">La dirección relativa, "test", se anexa a la dirección base.</span><span class="sxs-lookup"><span data-stu-id="f04de-116">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="f04de-117">La dirección del punto de conexión real es `http://localhost:8000/servicemodelsamples/service/test` .</span><span class="sxs-lookup"><span data-stu-id="f04de-117">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>
  
 <span data-ttu-id="f04de-118">La tercera definición de extremo especifica una dirección absoluta, como se muestra en el siguiente ejemplo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f04de-118">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="f04de-119">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="f04de-119">The base address plays no role in the address.</span></span> <span data-ttu-id="f04de-120">La dirección del punto de conexión real es `http://localhost:8001/hello/servicemodelsamples` .</span><span class="sxs-lookup"><span data-stu-id="f04de-120">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>
  
 <span data-ttu-id="f04de-121">La cuarta dirección del extremo especifica una dirección absoluta y un TCP de transporte diferente.</span><span class="sxs-lookup"><span data-stu-id="f04de-121">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="f04de-122">La dirección base no desempeña ningún papel en la dirección.</span><span class="sxs-lookup"><span data-stu-id="f04de-122">The base address plays no role in the address.</span></span> <span data-ttu-id="f04de-123">La dirección del punto de conexión real es `net.tcp://localhost:9000/servicemodelsamples/service` .</span><span class="sxs-lookup"><span data-stu-id="f04de-123">The actual endpoint address is `net.tcp://localhost:9000/servicemodelsamples/service`.</span></span>
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="f04de-124">El cliente tiene acceso solo a uno de los cuatro puntos de conexión de servicio, pero los cuatro se definen en su archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="f04de-124">The client accesses just one of the four service endpoints, but all four are defined in its configuration file.</span></span> <span data-ttu-id="f04de-125">El cliente selecciona un punto de conexión cuando crea el objeto `CalculatorProxy`.</span><span class="sxs-lookup"><span data-stu-id="f04de-125">The client selects an endpoint when it creates the `CalculatorProxy` object.</span></span> <span data-ttu-id="f04de-126">Cambiando el nombre de configuración de `CalculatorEndpoint1` a través de `CalculatorEndpoint4`, puede ejercer cada uno de los extremos.</span><span class="sxs-lookup"><span data-stu-id="f04de-126">By changing the configuration name from `CalculatorEndpoint1` through `CalculatorEndpoint4`, you can exercise each of the endpoints.</span></span>  
  
 <span data-ttu-id="f04de-127">Al ejecutar el ejemplo, el servicio enumera la dirección, enlazando el nombre y el nombre del contrato para cada uno de sus puntos de conexión.</span><span class="sxs-lookup"><span data-stu-id="f04de-127">When you run the sample, the service enumerates the address, binding name and contract name for each of its endpoints.</span></span> <span data-ttu-id="f04de-128">El punto de conexión de intercambio (MEX) de metadatos simplemente es otro punto de conexión de la perspectiva del ServiceHost que se presenta en la lista.</span><span class="sxs-lookup"><span data-stu-id="f04de-128">The metadata exchange (MEX) endpoint is just another endpoint from the ServiceHost's perspective so it shows up in the list.</span></span>  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="f04de-129">Al ejecutar el cliente, las solicitudes de la operación y las respuestas se muestran en las ventanas de la consola del cliente y del servicio.</span><span class="sxs-lookup"><span data-stu-id="f04de-129">When you run the client, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="f04de-130">Presione Entrar en cada ventana de la consola para cerrar el servicio y el cliente.</span><span class="sxs-lookup"><span data-stu-id="f04de-130">Press ENTER in each console window to shut down the service and client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f04de-131">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="f04de-131">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="f04de-132">Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f04de-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="f04de-133">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f04de-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="f04de-134">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f04de-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="f04de-135">Si usa Svcutil.exe para regenerar la configuración de este ejemplo, asegúrese de que modifica el nombre del extremo en la configuración del cliente para que coincida con el código de cliente.</span><span class="sxs-lookup"><span data-stu-id="f04de-135">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="f04de-136">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="f04de-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f04de-137">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="f04de-137">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="f04de-138">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="f04de-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f04de-139">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="f04de-139">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
