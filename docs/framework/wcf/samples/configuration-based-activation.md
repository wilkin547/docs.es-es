---
title: Activación basada en la configuración
ms.date: 03/30/2017
ms.assetid: 21bb762e-c43e-4b0c-887b-5e434d665838
ms.openlocfilehash: 3ac4edd2a51e4ed8a5c0b7e73d7d1afa31334c33
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="configuration-based-activation"></a><span data-ttu-id="05fab-102">Activación basada en la configuración</span><span class="sxs-lookup"><span data-stu-id="05fab-102">Configuration-Based Activation</span></span>
<span data-ttu-id="05fab-103">Este ejemplo muestra cómo activar los servicios de Windows Communication Foundation (WCF) sin necesidad de un archivo .svc.</span><span class="sxs-lookup"><span data-stu-id="05fab-103">This sample demonstrates how to activate Windows Communication Foundation (WCF) services without requiring a .svc file.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="05fab-104">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="05fab-104">The samples may already be installed on your computer.</span></span> <span data-ttu-id="05fab-105">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="05fab-105">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="05fab-106">Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="05fab-106">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="05fab-107">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="05fab-107">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\ConfigBasedActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="05fab-108">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="05fab-108">Sample Details</span></span>  
 <span data-ttu-id="05fab-109">En este ejemplo, el cliente es el cliente de prueba WCF y el servicio se hospeda en IIS.</span><span class="sxs-lookup"><span data-stu-id="05fab-109">In this sample, the client is the WCF test client and the service is hosted in IIS.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05fab-110">El procedimiento de instalación y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.</span><span class="sxs-lookup"><span data-stu-id="05fab-110">The setup and build instructions for this sample are located at the end of this topic.</span></span>  
  
### <a name="activation-of-services-without-requiring-a-svc-file"></a><span data-ttu-id="05fab-111">Activación de servicios sin necesidad de un archivo .svc</span><span class="sxs-lookup"><span data-stu-id="05fab-111">Activation of services without requiring a .svc file</span></span>  
 <span data-ttu-id="05fab-112">En [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], se necesitaba un archivo .svc para activar un servicio.</span><span class="sxs-lookup"><span data-stu-id="05fab-112">In [!INCLUDE[netfx35_short](../../../../includes/netfx35-short-md.md)], a .svc file was required for activating a service.</span></span> <span data-ttu-id="05fab-113">Esto ocasionaba sobrecarga de administración adicional, porque era necesario implementar y mantener un archivo adicional junto con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05fab-113">This caused additional management overhead, because an additional file was required to be deployed and maintained along with the application.</span></span> <span data-ttu-id="05fab-114">Con la versión de [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], los componentes de activación se pueden configurar utilizando el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05fab-114">With the release of [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)], the activation components can be configured using the application configuration file.</span></span>  
  
 [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)]<span data-ttu-id="05fab-115"> incluye un nuevo elemento de configuración (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), en <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> del archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05fab-115"> introduces a new configuration element (<xref:System.ServiceModel.Configuration.ServiceActivationElement>), in the <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> of the application configuration file.</span></span> <span data-ttu-id="05fab-116">La colección de <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> acepta una colección de servicios para activar, como se muestra en el siguiente ejemplo de código.</span><span class="sxs-lookup"><span data-stu-id="05fab-116">The <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection> collection accepts a collection of services to activate, as shown in the following code example.</span></span>  
  
```xml  
<serviceActivations>  
   <add relativeAddress="Calculator.svc" service="Microsoft.ServiceModel.Samples.CalculatorService" />  
  
<serviceActivations>  
```  
  
 <span data-ttu-id="05fab-117">Es preciso tener en cuenta una observación: la configuración parece muy similar a la configuración de archivos .svc.</span><span class="sxs-lookup"><span data-stu-id="05fab-117">The observation to make is the configuration looks very similar to the configuration of .svc files.</span></span> <span data-ttu-id="05fab-118">Se incluye un atributo adicional, `relativeAddress`, que proporciona la dirección del servicio.</span><span class="sxs-lookup"><span data-stu-id="05fab-118">An additional attribute that is introduced is the `relativeAddress` that provides the address of the service.</span></span> <span data-ttu-id="05fab-119">La dirección relativa también es la ruta de acceso virtual del servicio.</span><span class="sxs-lookup"><span data-stu-id="05fab-119">The relative address is also the virtual path for the service.</span></span> <span data-ttu-id="05fab-120">El host recupera el archivo Web.config del archivo de la ubicación `virtualPath`, si está presente; de lo contrario, el host busca de forma recursiva en su carpeta primaria.</span><span class="sxs-lookup"><span data-stu-id="05fab-120">The host retrieves the Web.config file of the file from the `virtualPath` location, if present; otherwise the host searches its parent folder recursively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="05fab-121">En este ejemplo se requiere que funcione el hospedaje en IIS.</span><span class="sxs-lookup"><span data-stu-id="05fab-121">This sample requires hosting in IIS to function.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="05fab-122">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="05fab-122">To use this sample</span></span>  
  
1.  <span data-ttu-id="05fab-123">Mediante [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], abra el archivo Service.csproj.</span><span class="sxs-lookup"><span data-stu-id="05fab-123">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the Service.csproj file.</span></span>  
  
2.  <span data-ttu-id="05fab-124">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="05fab-124">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
3.  <span data-ttu-id="05fab-125">Pruebe el servicio ejecutando WCFTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="05fab-125">Test the service by running WCFTestClient.exe.</span></span>  
  
4.  <span data-ttu-id="05fab-126">Mediante [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navegue a la carpeta %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE.</span><span class="sxs-lookup"><span data-stu-id="05fab-126">Using [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], navigate to the %SystemDrive%\Program Files\Microsoft Visual Studio 10.0\Common7\IDE folder.</span></span>  
  
5.  <span data-ttu-id="05fab-127">Ejecute WcfTestClient.exe.</span><span class="sxs-lookup"><span data-stu-id="05fab-127">Run WcfTestClient.exe.</span></span>  
  
6.  <span data-ttu-id="05fab-128">Establezca la dirección MEX del servicio.</span><span class="sxs-lookup"><span data-stu-id="05fab-128">Set the MEX address of the service.</span></span>  
  
7.  <span data-ttu-id="05fab-129">Presione CTRL+MAYÚS+A para establecer la dirección de servicio.</span><span class="sxs-lookup"><span data-stu-id="05fab-129">Press CTRL+SHIFT+A to set the service address.</span></span>  
  
8.  <span data-ttu-id="05fab-130">Establecer la dirección http://localhost/ServiceModelSamples/Calculator.svc.</span><span class="sxs-lookup"><span data-stu-id="05fab-130">Set the address to http://localhost/ServiceModelSamples/Calculator.svc.</span></span>  
  
9. <span data-ttu-id="05fab-131">Realice la operación `Add`.</span><span class="sxs-lookup"><span data-stu-id="05fab-131">Perform the `Add` operation.</span></span> <span data-ttu-id="05fab-132">Establezca el valor del parámetro `n1` en 10 y el valor del parámetro `n2` en 15.</span><span class="sxs-lookup"><span data-stu-id="05fab-132">Set value on the `n1` parameter to 10 and set value on the `n2` parameter to 15.</span></span>  
  
10. <span data-ttu-id="05fab-133">Presione **invocar**.</span><span class="sxs-lookup"><span data-stu-id="05fab-133">Press **Invoke**.</span></span>  
  
     <span data-ttu-id="05fab-134">El resultado esperado es 25.</span><span class="sxs-lookup"><span data-stu-id="05fab-134">The expected result is 25.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="05fab-135">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="05fab-135">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="05fab-136">Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05fab-136">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="05fab-137">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05fab-137">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="05fab-138">Una vez compilada la solución, ejecute Setup.bat para configurar la aplicación ServiceModelSamples en IIS.</span><span class="sxs-lookup"><span data-stu-id="05fab-138">After the solution has been built, run Setup.bat to set up the ServiceModelSamples Application in IIS.</span></span> <span data-ttu-id="05fab-139">El directorio ServiceModelSamples debería aparecer ahora como una aplicación IIS.</span><span class="sxs-lookup"><span data-stu-id="05fab-139">The ServiceModelSamples directory should now appear as an IIS Application.</span></span>  
  
4.  <span data-ttu-id="05fab-140">Para ejecutar el ejemplo en una configuración de equipo único o varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="05fab-140">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05fab-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="05fab-141">See Also</span></span>  
 [<span data-ttu-id="05fab-142">Ejemplos de persistencia y el hospedaje de AppFabric</span><span class="sxs-lookup"><span data-stu-id="05fab-142">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
