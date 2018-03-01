---
title: Contadores de rendimiento de WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be4ffac8444f6365dacb2b20db6abbb6792c2239
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="69261-102">Contadores de rendimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="69261-102">WCF Performance Counters</span></span>
[!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<span data-ttu-id="69261-103"> incluye un conjunto grande de contadores de rendimiento para ayudarle a calibrar el rendimiento de su aplicación.</span><span class="sxs-lookup"><span data-stu-id="69261-103"> includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="69261-104">Habilitación de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="69261-104">Enabling Performance Counters</span></span>  
 <span data-ttu-id="69261-105">Puede habilitar contadores de rendimiento para un servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] a través del archivo de configuración app.config del servicio [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], como se indica a continuación:</span><span class="sxs-lookup"><span data-stu-id="69261-105">You can enable performance counters for a [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service through the app.config configuration file of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="69261-106">Puede establecer el atributo `performanceCounters` para habilitar un tipo específico de contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-106">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="69261-107">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="69261-107">Valid values are</span></span>  
  
-   <span data-ttu-id="69261-108">All: todos los contadores de categoría (ServiceModelService, ServiceModelEndpoint y ServiceModelOperation) están habilitados.</span><span class="sxs-lookup"><span data-stu-id="69261-108">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
-   <span data-ttu-id="69261-109">ServiceOnly: solo se habilitan los contadores de categoría ServiceModelService.</span><span class="sxs-lookup"><span data-stu-id="69261-109">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="69261-110">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="69261-110">This is the default value.</span></span>  
  
-   <span data-ttu-id="69261-111">Off: los contadores de rendimiento ServiceModel\* están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="69261-111">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="69261-112">Si desea habilitar los contadores de rendimiento para todas las aplicaciones de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], incluya los parámetros de configuración en el archivo Machine.config.</span><span class="sxs-lookup"><span data-stu-id="69261-112">If you want to enable performance counters for all [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="69261-113">Vea la **aumentar el tamaño de memoria para los contadores de rendimiento** sección para obtener más información acerca de cómo configurar memoria suficiente para que los contadores de rendimiento en su equipo.</span><span class="sxs-lookup"><span data-stu-id="69261-113">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="69261-114">Si utiliza puntos de extensibilidad de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], como invocadores de operación personalizados, también debe emitir sus propios contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-114">If you use [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="69261-115">Esto se debe a que, si implementa un punto de extensibilidad, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] quizá no pueda emitir los datos de contador de rendimiento estándar en la ruta de acceso predeterminada.</span><span class="sxs-lookup"><span data-stu-id="69261-115">This is because if you implement an extensibility point, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="69261-116">Si no implementa la compatibilidad con el contador de rendimiento manual, puede que no vea los datos de contador de rendimiento que espera.</span><span class="sxs-lookup"><span data-stu-id="69261-116">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="69261-117">Además, puede habilitar los contadores de rendimiento en el código de la siguiente forma,</span><span class="sxs-lookup"><span data-stu-id="69261-117">You can also enable performance counters in your code as follows,</span></span>  
  
```  
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="69261-118">Ver los datos de rendimiento</span><span class="sxs-lookup"><span data-stu-id="69261-118">Viewing Performance Data</span></span>  
 <span data-ttu-id="69261-119">Para ver los datos capturados por los contadores de rendimiento, utilice el monitor de rendimiento (Perfmon.exe) incluido en Windows.</span><span class="sxs-lookup"><span data-stu-id="69261-119">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="69261-120">Puede iniciar esta herramienta, vaya a **iniciar**y haga clic en **ejecutar** y escriba `perfmon.exe` en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="69261-120">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69261-121">Se pueden lanzar instancias del contador de rendimiento antes de que el distribuidor del punto de conexión haya procesado los últimos mensajes.</span><span class="sxs-lookup"><span data-stu-id="69261-121">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="69261-122">Esto puede dar lugar a que no se capturen los datos de rendimiento de algunos mensajes.</span><span class="sxs-lookup"><span data-stu-id="69261-122">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="69261-123">Aumento del tamaño de la memoria para los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="69261-123">Increasing Memory Size for Performance Counters</span></span>  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]<span data-ttu-id="69261-124"> utiliza la memoria compartida independiente para sus categorías de contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-124"> uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="69261-125">De forma predeterminada, la memoria compartida independiente se establece en un cuarto del tamaño de la memoria global del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-125">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="69261-126">La memoria global del contador de rendimiento predeterminada es 524.288 bytes.</span><span class="sxs-lookup"><span data-stu-id="69261-126">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="69261-127">Por lo tanto, las tres categorías de contador de rendimiento [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] tienen un tamaño predeterminado de aproximadamente 128KB cada una.</span><span class="sxs-lookup"><span data-stu-id="69261-127">Therefore, the three [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="69261-128">Dependiendo de las características del tiempo de ejecución de las aplicaciones [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] de un equipo, es posible agotar la memoria del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-128">Depending upon the runtime characteristics of the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="69261-129">Cuando esto ocurre, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] escribe un error en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69261-129">When this happens, [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] writes an error to the application event log.</span></span> <span data-ttu-id="69261-130">El contenido del error indica que no se cargó un contador de rendimiento, y la entrada contiene la excepción "System.InvalidOperationException: Memoria insuficiente para la vista personaliza del archivo de contadores".</span><span class="sxs-lookup"><span data-stu-id="69261-130">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="69261-131">Si se habilita la traza en el nivel de error, también se sigue la traza del error.</span><span class="sxs-lookup"><span data-stu-id="69261-131">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="69261-132">Si se agota la memoria del contador de rendimiento y continúan ejecutándose las aplicaciones [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] con los contadores de rendimiento habilitados, podría degradarse el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-132">If performance counter memory is exhausted, continuing to run your [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="69261-133">Si es administrador de la máquina, configúrela y asigne memoria suficiente para admitir el número máximo de contadores de rendimiento que puedan existir en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="69261-133">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="69261-134">Puede cambiar la cantidad de memoria del contador de rendimiento para las categorías de [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] del registro.</span><span class="sxs-lookup"><span data-stu-id="69261-134">You can change the amount of performance counter memory for [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] categories in the registry.</span></span> <span data-ttu-id="69261-135">Para cambiarla, es necesario agregar un nuevo valor DWORD, denominado `FileMappingSize`, a las tres ubicaciones siguientes y establecerlo en el valor en bytes deseado.</span><span class="sxs-lookup"><span data-stu-id="69261-135">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="69261-136">Reinicie su equipo para que estos cambios se hagan efectivos.</span><span class="sxs-lookup"><span data-stu-id="69261-136">Reboot your machine so that these changes are taken into effect.</span></span>  
  
-   <span data-ttu-id="69261-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="69261-137">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="69261-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="69261-138">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
-   <span data-ttu-id="69261-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="69261-139">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="69261-140">Cuando se elimina un número importante de objetos (por ejemplo, ServiceHost) pero se espera recopilar los elementos no usados, el contador de rendimiento `PrivateBytes` registra un número excepcionalmente alto.</span><span class="sxs-lookup"><span data-stu-id="69261-140">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="69261-141">Para solucionar este problema, puede agregar sus propios contadores específicos de la aplicación, o utilizar el atributo `performanceCounters` para habilitar solo los contadores del nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="69261-141">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="69261-142">Tipos de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="69261-142">Types of Performance Counters</span></span>  
 <span data-ttu-id="69261-143">Los contadores de rendimiento abarcan tres niveles diferentes: servicio, extremo y operación.</span><span class="sxs-lookup"><span data-stu-id="69261-143">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="69261-144">Puede utilizar WMI para recuperar el nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-144">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="69261-145">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="69261-145">For example,</span></span>  
  
-   <span data-ttu-id="69261-146">Nombre de instancia del contador de servicio puede obtenerse a través de WMI [servicio](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) "CounterInstanceName" propiedad de la instancia.</span><span class="sxs-lookup"><span data-stu-id="69261-146">Service counter instance name can be obtained through WMI [Service](../../../../../docs/framework/wcf/diagnostics/wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="69261-147">Nombre de instancia del contador de punto de conexión puede obtenerse a través de WMI [extremo](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) "CounterInstanceName" propiedad de la instancia.</span><span class="sxs-lookup"><span data-stu-id="69261-147">Endpoint counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
-   <span data-ttu-id="69261-148">Nombre de instancia de contador de operación puede obtenerse a través de WMI [extremo](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) "GetOperationCounterInstanceName" al método de instancia.</span><span class="sxs-lookup"><span data-stu-id="69261-148">Operation counter instance name can be obtained through WMI [Endpoint](../../../../../docs/framework/wcf/diagnostics/wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="69261-149">Para obtener más información acerca de WMI, consulte [utilizando Windows Management Instrumentation para diagnósticos](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="69261-149">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../../../../../docs/framework/wcf/diagnostics/wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="69261-150">Contadores de rendimiento del servicio</span><span class="sxs-lookup"><span data-stu-id="69261-150">Service performance counters</span></span>  
 <span data-ttu-id="69261-151">Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="69261-151">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="69261-152">Pueden encontrarse en el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo con el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-152">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="69261-153">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="69261-153">The instances are named using the following pattern:</span></span>  
  
```  
ServiceName@ServiceBaseAddress  
```  
  
 <span data-ttu-id="69261-154">Se agrega un contador a un ámbito del servicio desde el contador de una colección de extremos.</span><span class="sxs-lookup"><span data-stu-id="69261-154">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="69261-155">Los contadores de rendimiento de la creación de una instancia de servicio aumentan cuando se crea un nuevo InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="69261-155">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="69261-156">Tenga en cuenta que también se crea un nuevo InstanceContext cuando recibe un mensaje de no activación (con un servicio existente), o cuando se conecta a la instancia de una sesión, finaliza la sesión y, a continuación, se vuelve a conectar desde otra sesión.</span><span class="sxs-lookup"><span data-stu-id="69261-156">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="69261-157">Contadores de rendimiento del extremo</span><span class="sxs-lookup"><span data-stu-id="69261-157">Endpoint performance counters</span></span>  
 <span data-ttu-id="69261-158">Los contadores de rendimiento del extremo permiten examinar datos que reflejan la aceptación de los mensajes por un extremo.</span><span class="sxs-lookup"><span data-stu-id="69261-158">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="69261-159">Pueden encontrarse en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al visualizarlo mediante el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-159">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="69261-160">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="69261-160">The instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName)@(endpoint listener address)  
```  
  
 <span data-ttu-id="69261-161">Los datos son similares a los recopilados para las operaciones individuales, pero solo se agregan a lo largo del extremo.</span><span class="sxs-lookup"><span data-stu-id="69261-161">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="69261-162">Un contador en un ámbito de extremo se agrega desde los contadores de una colección de operaciones.</span><span class="sxs-lookup"><span data-stu-id="69261-162">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69261-163">Si dos extremos poseen nombres y direcciones de contrato idénticos, se asignan a la misma instancia del contador.</span><span class="sxs-lookup"><span data-stu-id="69261-163">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="69261-164">Contadores de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="69261-164">Operation performance counters</span></span>  
 <span data-ttu-id="69261-165">Los contadores de rendimiento de la operación se encuentran en el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="69261-165">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="69261-166">Cada operación posee una instancia individual.</span><span class="sxs-lookup"><span data-stu-id="69261-166">Each operation has an individual instance.</span></span> <span data-ttu-id="69261-167">Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato.</span><span class="sxs-lookup"><span data-stu-id="69261-167">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="69261-168">Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="69261-168">The object instances are named using the following pattern:</span></span>  
  
```  
(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)  
```  
  
 <span data-ttu-id="69261-169">Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.</span><span class="sxs-lookup"><span data-stu-id="69261-169">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="69261-170">Cuando los contadores son visibles en varios ámbitos, los datos recopilados de un ámbito superior se agregan a los datos de los ámbitos inferiores.</span><span class="sxs-lookup"><span data-stu-id="69261-170">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="69261-171">Por ejemplo, `Calls` a un extremo representa la suma de todas las llamadas de la operación en el extremo; `Calls` a un servicio representa la suma de todas las llamadas a todos los extremos del servicio.</span><span class="sxs-lookup"><span data-stu-id="69261-171">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="69261-172">Si existen nombres de la operación duplicados en un contrato, solo se obtiene una instancia de contador para ambas operaciones.</span><span class="sxs-lookup"><span data-stu-id="69261-172">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="69261-173">Programación de los contadores de rendimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="69261-173">Programming the WCF Performance Counters</span></span>  
 <span data-ttu-id="69261-174">Se instalan varios archivos en la carpeta de instalación de SDK de modo que pueda obtenerse acceso a los contadores de rendimiento [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] mediante programación.</span><span class="sxs-lookup"><span data-stu-id="69261-174">Several files are installed in the SDK install folder so that you can access the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] performance counters programmatically.</span></span> <span data-ttu-id="69261-175">Estos archivos se enumeran como se indica a continuación.</span><span class="sxs-lookup"><span data-stu-id="69261-175">These files are listed as follows.</span></span>  
  
-   <span data-ttu-id="69261-176">_ServiceModelEndpointPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="69261-176">_ServiceModelEndpointPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="69261-177">_ServiceModelOperationPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="69261-177">_ServiceModelOperationPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="69261-178">_ServiceModelServicePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="69261-178">_ServiceModelServicePerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="69261-179">_SMSvcHostPerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="69261-179">_SMSvcHostPerfCounters.vrg</span></span>  
  
-   <span data-ttu-id="69261-180">_TransactionBridgePerfCounters.vrg</span><span class="sxs-lookup"><span data-stu-id="69261-180">_TransactionBridgePerfCounters.vrg</span></span>  
  
 <span data-ttu-id="69261-181">Para obtener más información sobre cómo obtener acceso a los contadores mediante programación, vea [arquitectura de programación del contador de rendimiento](http://go.microsoft.com/fwlink/?LinkId=95179).</span><span class="sxs-lookup"><span data-stu-id="69261-181">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](http://go.microsoft.com/fwlink/?LinkId=95179).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69261-182">Vea también</span><span class="sxs-lookup"><span data-stu-id="69261-182">See Also</span></span>  
 [<span data-ttu-id="69261-183">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="69261-183">Administration and Diagnostics</span></span>](../../../../../docs/framework/wcf/diagnostics/index.md)
