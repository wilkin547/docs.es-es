---
title: Proveedor WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: 7947d9a1bedfe7a2a550a7b4d52b3cf5a8f40126
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/06/2018
ms.locfileid: "48839403"
---
# <a name="wmi-provider"></a><span data-ttu-id="4c70a-102">Proveedor WMI</span><span class="sxs-lookup"><span data-stu-id="4c70a-102">WMI Provider</span></span>
<span data-ttu-id="4c70a-103">Este ejemplo muestra cómo recopilar datos de servicios de Windows Communication Foundation (WCF) en tiempo de ejecución mediante el proveedor de Instrumental de administración de Windows (WMI) que está integrado en WCF.</span><span class="sxs-lookup"><span data-stu-id="4c70a-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="4c70a-104">Asimismo, este ejemplo muestra cómo agregar un objeto WMI definido por el usuario a un servicio.</span><span class="sxs-lookup"><span data-stu-id="4c70a-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="4c70a-105">El ejemplo activa el proveedor WMI para la [Introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) y muestra cómo recopilar datos de la `ICalculator` servicio en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c70a-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="4c70a-106">WMI es la implementación de Microsoft del estándar Web-Based Enterprise Management (WBEM).</span><span class="sxs-lookup"><span data-stu-id="4c70a-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="4c70a-107">Para obtener más información sobre el SDK de WMI, consulte [Instrumental de administración de Windows](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="4c70a-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="4c70a-108">WBEM es un estándar de la industria para saber cómo exponen las aplicaciones la instrumentación de administración a las herramientas de administración externas.</span><span class="sxs-lookup"><span data-stu-id="4c70a-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="4c70a-109">WCF implementa un proveedor WMI, un componente que expone la instrumentación en tiempo de ejecución a través de una interfaz compatible con WBEM.</span><span class="sxs-lookup"><span data-stu-id="4c70a-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="4c70a-110">Las herramientas de administración pueden conectarse a los servicios a través de la interfaz en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4c70a-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="4c70a-111">WCF expone atributos de servicios como direcciones, enlaces, comportamientos y agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="4c70a-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="4c70a-112">El proveedor de WMI integrado se activa en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c70a-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="4c70a-113">Esto se realiza mediante el `wmiProviderEnabled` atributo de la [ \<diagnósticos >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) en el [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) sección, como se muestra en el ejemplo siguiente configuración:</span><span class="sxs-lookup"><span data-stu-id="4c70a-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="4c70a-114">Esta entrada de configuración expone una interfaz WMI.</span><span class="sxs-lookup"><span data-stu-id="4c70a-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="4c70a-115">Ahora, las aplicaciones de administración pueden establecer la conexión a través de esta interfaz y obtener acceso a la instrumentación de administración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4c70a-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="4c70a-116">Objeto WMI personalizado</span><span class="sxs-lookup"><span data-stu-id="4c70a-116">Custom WMI Object</span></span>  
 <span data-ttu-id="4c70a-117">Agregar objetos WMI a un servicio permite revelar la información definida por el usuario junto con la información de proveedor WMI integrada.</span><span class="sxs-lookup"><span data-stu-id="4c70a-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="4c70a-118">Esto se logra publicando el esquema del servicio en WMI mediante la aplicación Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="4c70a-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="4c70a-119">Las instrucciones para conseguirlo, además de más información, se pueden encontrar en las instrucciones de configuración al final del tema.</span><span class="sxs-lookup"><span data-stu-id="4c70a-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="4c70a-120">Acceso a la información de WMI</span><span class="sxs-lookup"><span data-stu-id="4c70a-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="4c70a-121">Se puede tener acceso a los datos de WMI de maneras muy distintas.</span><span class="sxs-lookup"><span data-stu-id="4c70a-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="4c70a-122">Microsoft proporciona las API de WMI para scripts, aplicaciones de Visual Basic, las aplicaciones de C++ y el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span><span class="sxs-lookup"><span data-stu-id="4c70a-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span></span>  
  
 <span data-ttu-id="4c70a-123">Este ejemplo utiliza dos scripts Java: uno para enumerar los servicios que se ejecutan en el equipo junto con algunas de sus propiedades y otro para ver los datos de WMI definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="4c70a-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="4c70a-124">El script abre una conexión con el proveedor WMI, analiza los datos y muestra los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="4c70a-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="4c70a-125">Iniciar el ejemplo para crear una instancia en ejecución de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="4c70a-125">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="4c70a-126">Mientras el servicio se está ejecutando, ejecute cada script de Java usando el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="4c70a-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="4c70a-127">El script obtiene acceso al instrumental contenido en el servicio y genera la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c70a-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="4c70a-128">Después, ejecute el segundo script de Java para mostrar los datos de WMI definidos por el usuario:</span><span class="sxs-lookup"><span data-stu-id="4c70a-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="4c70a-129">El script tiene acceso al instrumental definido por el usuario contenido en los servicios y genera el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="4c70a-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="4c70a-130">El resultado muestra que hay un único servicio que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="4c70a-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="4c70a-131">El servicio expone un extremo que implementa el contrato `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="4c70a-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="4c70a-132">Los valores del comportamiento y enlace que el punto de conexión implementa se muestran como la suma de elementos individuales de la pila de mensajería.</span><span class="sxs-lookup"><span data-stu-id="4c70a-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="4c70a-133">WMI no se limita a exponer el Instrumental de administración de la infraestructura de WCF.</span><span class="sxs-lookup"><span data-stu-id="4c70a-133">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="4c70a-134">La aplicación puede exponer sus propios elementos de datos específicos del dominio a través del mismo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="4c70a-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="4c70a-135">WMI es un mecanismo unificado para la inspección y control de un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="4c70a-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="4c70a-136">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="4c70a-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="4c70a-137">Asegúrese de que ha realizado la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c70a-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="4c70a-138">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c70a-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="4c70a-139">Publique el esquema de los servicios en WMI ejecutando InstallUtil.exe (las ubicaciones predeterminadas para Installutil.exe son "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") en el archivo service.dll del directorio de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="4c70a-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="4c70a-140">Este paso solo debe ejecutarse cuando se hayan realizado cambios en el archivo service.dll.</span><span class="sxs-lookup"><span data-stu-id="4c70a-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4.  <span data-ttu-id="4c70a-141">Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="4c70a-141">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4c70a-142">Si ha instalado WCF después de instalar ASP.NET, es posible que deba ejecutar "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe "- r - x para proporcionar a la cuenta de ASPNET permiso para publicar objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="4c70a-142">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5.  <span data-ttu-id="4c70a-143">Vea los datos del ejemplo que aparece mediante WMI con los comandos: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="4c70a-143">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4c70a-144">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4c70a-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="4c70a-145">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4c70a-145">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4c70a-146">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4c70a-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4c70a-147">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4c70a-147">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="4c70a-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c70a-148">See Also</span></span>  
 [<span data-ttu-id="4c70a-149">Ejemplos de supervisión de AppFabric</span><span class="sxs-lookup"><span data-stu-id="4c70a-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
