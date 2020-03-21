---
title: Proveedor WMI
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: 04fdbb7efcae6fdbb78f467352e6106ac5218799
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183200"
---
# <a name="wmi-provider"></a><span data-ttu-id="3af73-102">Proveedor WMI</span><span class="sxs-lookup"><span data-stu-id="3af73-102">WMI Provider</span></span>
<span data-ttu-id="3af73-103">En este ejemplo se muestra cómo recopilar datos de servicios de Windows Communication Foundation (WCF) en tiempo de ejecución mediante el proveedor de Instrumental de administración de Windows (WMI) integrado en WCF.</span><span class="sxs-lookup"><span data-stu-id="3af73-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="3af73-104">Asimismo, este ejemplo muestra cómo agregar un objeto WMI definido por el usuario a un servicio.</span><span class="sxs-lookup"><span data-stu-id="3af73-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="3af73-105">El ejemplo activa el proveedor WMI para [la introducción](../../../../docs/framework/wcf/samples/getting-started-sample.md) y `ICalculator` muestra cómo recopilar datos del servicio en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3af73-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="3af73-106">WMI es la implementación de Microsoft del estándar Web-Based Enterprise Management (WBEM).</span><span class="sxs-lookup"><span data-stu-id="3af73-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="3af73-107">Para obtener más información sobre el SDK de WMI, vea Instrumental de administración de [Windows](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="3af73-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="3af73-108">WBEM es un estándar de la industria para saber cómo exponen las aplicaciones la instrumentación de administración a las herramientas de administración externas.</span><span class="sxs-lookup"><span data-stu-id="3af73-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="3af73-109">WCF implementa un proveedor WMI, un componente que expone la instrumentación en tiempo de ejecución a través de una interfaz compatible con WBEM.</span><span class="sxs-lookup"><span data-stu-id="3af73-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="3af73-110">Las herramientas de administración pueden conectarse a los servicios a través de la interfaz en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3af73-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="3af73-111">WCF expone atributos de servicios como direcciones, enlaces, comportamientos y agentes de escucha.</span><span class="sxs-lookup"><span data-stu-id="3af73-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="3af73-112">El proveedor de WMI integrado se activa en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3af73-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="3af73-113">Esto se hace `wmiProviderEnabled` a través del atributo del [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) de diagnóstico en la [ \<sección system.serviceModel>,](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) como se muestra en la siguiente configuración de ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3af73-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="3af73-114">Esta entrada de configuración expone una interfaz WMI.</span><span class="sxs-lookup"><span data-stu-id="3af73-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="3af73-115">Ahora, las aplicaciones de administración pueden establecer la conexión a través de esta interfaz y obtener acceso a la instrumentación de administración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3af73-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="3af73-116">Objeto WMI personalizado</span><span class="sxs-lookup"><span data-stu-id="3af73-116">Custom WMI Object</span></span>  
 <span data-ttu-id="3af73-117">Agregar objetos WMI a un servicio permite revelar la información definida por el usuario junto con la información de proveedor WMI integrada.</span><span class="sxs-lookup"><span data-stu-id="3af73-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="3af73-118">Esto se logra publicando el esquema del servicio en WMI mediante la aplicación Installutil.exe.</span><span class="sxs-lookup"><span data-stu-id="3af73-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="3af73-119">Las instrucciones para conseguirlo, además de más información, se pueden encontrar en las instrucciones de configuración al final del tema.</span><span class="sxs-lookup"><span data-stu-id="3af73-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="3af73-120">Acceso a la información de WMI</span><span class="sxs-lookup"><span data-stu-id="3af73-120">Accessing WMI Information</span></span>  

<span data-ttu-id="3af73-121">Puede obtenerse acceso a los datos WMI de maneras muy distintas.</span><span class="sxs-lookup"><span data-stu-id="3af73-121">WMI data can be accessed in many different ways.</span></span> <span data-ttu-id="3af73-122">Microsoft proporciona API de WMI para scripts, aplicaciones de Visual Basic, aplicaciones C++ y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3af73-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework.</span></span> <span data-ttu-id="3af73-123">Para obtener más información, consulte Uso de [WMI](/windows/desktop/wmisdk/using-wmi).</span><span class="sxs-lookup"><span data-stu-id="3af73-123">For more information, see [Using WMI](/windows/desktop/wmisdk/using-wmi).</span></span>
  
 <span data-ttu-id="3af73-124">Este ejemplo utiliza dos scripts Java: uno para enumerar los servicios que se ejecutan en el equipo junto con algunas de sus propiedades y otro para ver los datos de WMI definidos por el usuario.</span><span class="sxs-lookup"><span data-stu-id="3af73-124">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="3af73-125">El script abre una conexión con el proveedor WMI, analiza los datos y muestra los datos recopilados.</span><span class="sxs-lookup"><span data-stu-id="3af73-125">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="3af73-126">Inicie el ejemplo para crear una instancia en ejecución de un servicio WCF.</span><span class="sxs-lookup"><span data-stu-id="3af73-126">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="3af73-127">Mientras el servicio se está ejecutando, ejecute cada script de Java usando el comando siguiente en el símbolo del sistema:</span><span class="sxs-lookup"><span data-stu-id="3af73-127">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="3af73-128">El script obtiene acceso al instrumental contenido en el servicio y genera la salida siguiente:</span><span class="sxs-lookup"><span data-stu-id="3af73-128">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```console  
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
  
 <span data-ttu-id="3af73-129">Después, ejecute el segundo script de Java para mostrar los datos de WMI definidos por el usuario:</span><span class="sxs-lookup"><span data-stu-id="3af73-129">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="3af73-130">El script tiene acceso al instrumental definido por el usuario contenido en los servicios y genera el resultado siguiente:</span><span class="sxs-lookup"><span data-stu-id="3af73-130">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="3af73-131">El resultado muestra que hay un único servicio que se ejecuta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3af73-131">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="3af73-132">El servicio expone un extremo que implementa el contrato `ICalculator`.</span><span class="sxs-lookup"><span data-stu-id="3af73-132">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="3af73-133">Los valores del comportamiento y el enlace que el punto de conexión implementa se muestran como la suma de elementos individuales de la pila de mensajería.</span><span class="sxs-lookup"><span data-stu-id="3af73-133">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="3af73-134">WMI no se limita a exponer la instrumentación de administración de la infraestructura WCF.</span><span class="sxs-lookup"><span data-stu-id="3af73-134">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="3af73-135">La aplicación puede exponer sus propios elementos de datos específicos del dominio a través del mismo mecanismo.</span><span class="sxs-lookup"><span data-stu-id="3af73-135">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="3af73-136">WMI es un mecanismo unificado para la inspección y control de un servicio Web.</span><span class="sxs-lookup"><span data-stu-id="3af73-136">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="3af73-137">Configurar, compilar y ejecutar el ejemplo</span><span class="sxs-lookup"><span data-stu-id="3af73-137">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="3af73-138">Asegúrese de que ha realizado el procedimiento de instalación única [para los ejemplos](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="3af73-138">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="3af73-139">Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="3af73-139">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="3af73-140">Publique el esquema de los servicios en WMI ejecutando InstallUtil.exe (las ubicaciones predeterminadas para Installutil.exe son "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") en el archivo service.dll del directorio de hospedaje.</span><span class="sxs-lookup"><span data-stu-id="3af73-140">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="3af73-141">Este paso solo debe ejecutarse cuando se hayan realizado cambios en el archivo service.dll.</span><span class="sxs-lookup"><span data-stu-id="3af73-141">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="3af73-142">Para ejecutar el ejemplo en una configuración de un equipo o entre equipos, siga las instrucciones de Ejecución de [los ejemplos](../../../../docs/framework/wcf/samples/running-the-samples.md)de Windows Communication Foundation .</span><span class="sxs-lookup"><span data-stu-id="3af73-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="3af73-143">Si ha instalado WCF después de instalar ASP.NET, es posible que deba ejecutar "%WINDIR%" Microsoft.Net-Framework-v3.0-Windows Communication Foundation-servicemodelreg.exe " -r -x para conceder a la cuenta ASPNET permiso para publicar objetos WMI.</span><span class="sxs-lookup"><span data-stu-id="3af73-143">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="3af73-144">Vea los datos del ejemplo que aparece mediante WMI con los comandos: `cscript EnumerateServices.js` o `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="3af73-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="3af73-145">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="3af73-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="3af73-146">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="3af73-146">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="3af73-147">Si este directorio no existe, vaya a Ejemplos de [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los ejemplos y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="3af73-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="3af73-148">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="3af73-148">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="3af73-149">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3af73-149">See also</span></span>

- <span data-ttu-id="3af73-150">[Ejemplos de supervisión de AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="3af73-150">[AppFabric Monitoring Samples](https://docs.microsoft.com/previous-versions/appfabric/ff383407(v=azure.10))</span></span>
