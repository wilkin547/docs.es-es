---
description: 'Más información acerca de: contadores de rendimiento de WCF'
title: Contadores de rendimiento de WCF
ms.date: 03/30/2017
helpviewer_keywords:
- performance counters [WCF]
ms.assetid: f559b2bd-ed83-4988-97a1-e88f06646609
ms.openlocfilehash: c6572ece289fb550dd4974a8f8e957f7d3ef51b5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99655349"
---
# <a name="wcf-performance-counters"></a><span data-ttu-id="0cfd8-103">Contadores de rendimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="0cfd8-103">WCF Performance Counters</span></span>

<span data-ttu-id="0cfd8-104">Windows Communication Foundation (WCF) incluye un gran conjunto de contadores de rendimiento para ayudarle a medir el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-104">Windows Communication Foundation (WCF) includes a large set of performance counters to help you gauge your application's performance.</span></span>  
  
## <a name="enabling-performance-counters"></a><span data-ttu-id="0cfd8-105">Habilitación de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0cfd8-105">Enabling Performance Counters</span></span>  

 <span data-ttu-id="0cfd8-106">Puede habilitar los contadores de rendimiento para un servicio WCF a través del archivo de configuración app.config del servicio WCF de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-106">You can enable performance counters for a WCF service through the app.config configuration file of the WCF service as follows:</span></span>  
  
```xml  
<configuration>  
    <system.serviceModel>  
        <diagnostics performanceCounters="All" />  
    </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="0cfd8-107">Puede establecer el atributo `performanceCounters` para habilitar un tipo específico de contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-107">The `performanceCounters` attribute can be set to enable a specific type of performance counters.</span></span> <span data-ttu-id="0cfd8-108">Los valores válidos son</span><span class="sxs-lookup"><span data-stu-id="0cfd8-108">Valid values are</span></span>  
  
- <span data-ttu-id="0cfd8-109">All: todos los contadores de categoría (ServiceModelService, ServiceModelEndpoint y ServiceModelOperation) están habilitados.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-109">All: All category counters (ServiceModelService, ServiceModelEndpoint and ServiceModelOperation) are enabled.</span></span>  
  
- <span data-ttu-id="0cfd8-110">ServiceOnly: solo se habilitan los contadores de categoría ServiceModelService.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-110">ServiceOnly: Only ServiceModelService category counters are enabled.</span></span> <span data-ttu-id="0cfd8-111">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-111">This is the default value.</span></span>  
  
- <span data-ttu-id="0cfd8-112">Off: los contadores de rendimiento ServiceModel\* están deshabilitados.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-112">Off: ServiceModel\* performance counters are disabled.</span></span>  
  
 <span data-ttu-id="0cfd8-113">Si desea habilitar los contadores de rendimiento para todas las aplicaciones WCF, puede colocar los valores de configuración en el archivo de Machine.config.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-113">If you want to enable performance counters for all WCF applications, you can place the configuration settings in the Machine.config file.</span></span>  <span data-ttu-id="0cfd8-114">Consulte la sección **aumento del tamaño de la memoria para los contadores de rendimiento** más adelante para obtener más información sobre cómo configurar la memoria suficiente para los contadores de rendimiento de su equipo.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-114">Please see the **Increasing Memory Size for Performance Counters** section below for more information on configuring sufficient memory for performance counters on your machine.</span></span>  
  
 <span data-ttu-id="0cfd8-115">Si usa puntos de extensibilidad de WCF como invocadores de operación personalizados, también debe emitir sus propios contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-115">If you use WCF extensibility points such as custom operation invokers, you should also emit your own performance counters.</span></span> <span data-ttu-id="0cfd8-116">Esto se debe a que, si implementa un punto de extensibilidad, WCF ya no puede emitir los datos de contador de rendimiento estándar en la ruta de acceso predeterminada.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-116">This is because if you implement an extensibility point, WCF may no longer emit the standard performance counter data in the default path.</span></span> <span data-ttu-id="0cfd8-117">Si no implementa la compatibilidad con el contador de rendimiento manual, puede que no vea los datos de contador de rendimiento que espera.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-117">If you do not implement manual performance counter support, you may not see the performance counter data you expect.</span></span>  
  
 <span data-ttu-id="0cfd8-118">Además, puede habilitar los contadores de rendimiento en el código de la siguiente forma,</span><span class="sxs-lookup"><span data-stu-id="0cfd8-118">You can also enable performance counters in your code as follows,</span></span>  
  
```csharp
using System.Configuration;  
using System.ServiceModel.Configuration;  
using System.ServiceModel.Diagnostics;  
Configuration config = ConfigurationManager.OpenExeConfiguration(  
    ConfigurationUserLevel.None);  
ServiceModelSectionGroup sg = ServiceModelSectionGroup.GetSectionGroup(config);  
sg.Diagnostic.PerformanceCounters = PerformanceCounterScope.All;  
config.Save();  
```  
  
## <a name="viewing-performance-data"></a><span data-ttu-id="0cfd8-119">Visualización de datos de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0cfd8-119">Viewing Performance Data</span></span>  

 <span data-ttu-id="0cfd8-120">Para ver los datos capturados por los contadores de rendimiento, utilice el monitor de rendimiento (Perfmon.exe) incluido en Windows.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-120">To view data captured by the performance counters, you can use the Performance Monitor (Perfmon.exe) that comes with Windows.</span></span> <span data-ttu-id="0cfd8-121">Puede iniciar esta herramienta; para ello, vaya a **Inicio** y haga clic en **Ejecutar** y escriba `perfmon.exe` en el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-121">You can launch this tool by going to **Start**, and click **Run** and type `perfmon.exe` in the dialog box.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cfd8-122">Se pueden lanzar instancias del contador de rendimiento antes de que el distribuidor del punto de conexión haya procesado los últimos mensajes.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-122">Performance counter instances may be released before the last messages have been processed by the endpoint dispatcher.</span></span> <span data-ttu-id="0cfd8-123">Esto puede dar lugar a que no se capturen los datos de rendimiento de algunos mensajes.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-123">This can result in performance data not being captured for a few messages.</span></span>  
  
## <a name="increasing-memory-size-for-performance-counters"></a><span data-ttu-id="0cfd8-124">Aumento del tamaño de la memoria para los contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0cfd8-124">Increasing Memory Size for Performance Counters</span></span>  

 <span data-ttu-id="0cfd8-125">WCF usa memoria compartida independiente para sus categorías de contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-125">WCF uses separate shared memory for its performance counter categories.</span></span>  
  
 <span data-ttu-id="0cfd8-126">De forma predeterminada, la memoria compartida independiente se establece en un cuarto del tamaño de la memoria global del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-126">By default, separate shared memory is set to a quarter the size of global performance counter memory.</span></span> <span data-ttu-id="0cfd8-127">La memoria global del contador de rendimiento predeterminada es 524.288 bytes.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-127">The default global performance counter memory is 524,288 bytes.</span></span> <span data-ttu-id="0cfd8-128">Por lo tanto, las tres categorías de contador de rendimiento de WCF tienen un tamaño predeterminado de aproximadamente 128 KB cada uno.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-128">Therefore, the three WCF performance counter categories have a default size of approximately 128KB each.</span></span> <span data-ttu-id="0cfd8-129">En función de las características de tiempo de ejecución de las aplicaciones WCF en un equipo, se puede agotar la memoria del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-129">Depending upon the runtime characteristics of the WCF applications on a machine, performance counter memory may be exhausted.</span></span> <span data-ttu-id="0cfd8-130">Cuando esto sucede, WCF escribe un error en el registro de eventos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-130">When this happens, WCF writes an error to the application event log.</span></span> <span data-ttu-id="0cfd8-131">El contenido del error indica que no se cargó un contador de rendimiento, y la entrada contiene la excepción "System.InvalidOperationException: Memoria insuficiente para la vista personaliza del archivo de contadores".</span><span class="sxs-lookup"><span data-stu-id="0cfd8-131">The content of the error states that a performance counter was not loaded, and the entry contains the exception "System.InvalidOperationException: Custom counters file view is out of memory."</span></span> <span data-ttu-id="0cfd8-132">Si se habilita la traza en el nivel de error, también se sigue la traza del error.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-132">If tracing is enabled at the error level, this failure is also traced.</span></span> <span data-ttu-id="0cfd8-133">Si se agota la memoria del contador de rendimiento, continuar ejecutando las aplicaciones WCF con los contadores de rendimiento habilitados podría provocar una degradación del rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-133">If performance counter memory is exhausted, continuing to run your WCF applications with performance counters enabled could result in performance degradation.</span></span> <span data-ttu-id="0cfd8-134">Si es administrador de la máquina, configúrela y asigne memoria suficiente para admitir el número máximo de contadores de rendimiento que puedan existir en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-134">If you are an administrator of the machine, you should configure it to allocate enough memory to support the maximum number of performance counters that can exist at any time.</span></span>  
  
 <span data-ttu-id="0cfd8-135">Puede cambiar la cantidad de memoria del contador de rendimiento para las categorías de WCF en el registro.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-135">You can change the amount of performance counter memory for WCF categories in the registry.</span></span> <span data-ttu-id="0cfd8-136">Para cambiarla, es necesario agregar un nuevo valor DWORD, denominado `FileMappingSize`, a las tres ubicaciones siguientes y establecerlo en el valor en bytes deseado.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-136">To do so, you need to add a new DWORD value named `FileMappingSize` to the three following locations, and set it to the desired value in bytes.</span></span> <span data-ttu-id="0cfd8-137">Reinicie su equipo para que estos cambios se hagan efectivos.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-137">Reboot your machine so that these changes are taken into effect.</span></span>  
  
- <span data-ttu-id="0cfd8-138">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0cfd8-138">HKLM\System\CurrentControlSet\Services\ServiceModelEndpoint 4.0.0.0\Performance</span></span>  
  
- <span data-ttu-id="0cfd8-139">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0cfd8-139">HKLM\System\CurrentControlSet\Services\ServiceModelOperation 4.0.0.0\Performance</span></span>  
  
- <span data-ttu-id="0cfd8-140">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span><span class="sxs-lookup"><span data-stu-id="0cfd8-140">HKLM\System\CurrentControlSet\Services\ServiceModelService 4.0.0.0\Performance</span></span>  
  
 <span data-ttu-id="0cfd8-141">Cuando se elimina un número importante de objetos (por ejemplo, ServiceHost) pero se espera recopilar los elementos no usados, el contador de rendimiento `PrivateBytes` registra un número excepcionalmente alto.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-141">When a large number of objects (for example, ServiceHost) are disposed of but waiting to be garbage-collected, the `PrivateBytes` performance counter will register an unusually high number.</span></span> <span data-ttu-id="0cfd8-142">Para solucionar este problema, puede agregar sus propios contadores específicos de la aplicación, o utilizar el atributo `performanceCounters` para habilitar solo los contadores del nivel de servicio.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-142">To resolve this problem, you can either add your own application-specific counters, or use the `performanceCounters` attribute to enable only service-level counters.</span></span>  
  
## <a name="types-of-performance-counters"></a><span data-ttu-id="0cfd8-143">Tipos de contadores de rendimiento</span><span class="sxs-lookup"><span data-stu-id="0cfd8-143">Types of Performance Counters</span></span>  

 <span data-ttu-id="0cfd8-144">Los contadores de rendimiento abarcan tres niveles diferentes: servicio, punto de conexión y operación.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-144">Performance counters are scoped to three different levels: Service, Endpoint and Operation.</span></span>  
  
 <span data-ttu-id="0cfd8-145">Puede utilizar WMI para recuperar el nombre de una instancia del contador de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-145">You can use WMI to retrieve the name of a performance counter instance.</span></span> <span data-ttu-id="0cfd8-146">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="0cfd8-146">For example,</span></span>  
  
- <span data-ttu-id="0cfd8-147">El nombre de la instancia del contador de servicio se puede obtener a través de la propiedad "CounterInstanceName" de la instancia del [servicio](../wmi/service.md) WMI.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-147">Service counter instance name can be obtained through WMI [Service](../wmi/service.md) instance's "CounterInstanceName" property.</span></span>  
  
- <span data-ttu-id="0cfd8-148">El nombre de instancia del contador de extremo se puede obtener a través de la propiedad "CounterInstanceName" de la instancia del [punto de conexión](../wmi/endpoint.md) de WMI.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-148">Endpoint counter instance name can be obtained through WMI [Endpoint](../wmi/endpoint.md) instance's "CounterInstanceName" property.</span></span>  
  
- <span data-ttu-id="0cfd8-149">El nombre de la instancia del contador de operaciones se puede obtener a través del método "GetOperationCounterInstanceName" de la instancia del [punto de conexión](../wmi/endpoint.md) de WMI.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-149">Operation counter instance name can be obtained through WMI [Endpoint](../wmi/endpoint.md) instance's "GetOperationCounterInstanceName" method.</span></span>  
  
 <span data-ttu-id="0cfd8-150">Para obtener más información acerca de WMI, consulte [uso de instrumental de administración de Windows para diagnósticos](../wmi/index.md).</span><span class="sxs-lookup"><span data-stu-id="0cfd8-150">For more information on WMI, see [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md).</span></span>  
  
### <a name="service-performance-counters"></a><span data-ttu-id="0cfd8-151">Contadores de rendimiento del servicio</span><span class="sxs-lookup"><span data-stu-id="0cfd8-151">Service performance counters</span></span>  

 <span data-ttu-id="0cfd8-152">Los contadores de rendimiento del servicio miden el conjunto del comportamiento del servicio y se utilizan para diagnosticar el rendimiento de todo el servicio.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-152">Service performance counters measure the service behavior as a whole and can be used to diagnose the performance of the whole service.</span></span> <span data-ttu-id="0cfd8-153">Pueden encontrarse en el objeto de rendimiento `ServiceModelService 4.0.0.0` al visualizarlo con el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-153">They can be found under the `ServiceModelService 4.0.0.0` performance object when viewing with Performance Monitor.</span></span> <span data-ttu-id="0cfd8-154">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-154">The instances are named using the following pattern:</span></span>  
  
`ServiceName@ServiceBaseAddress`
  
 <span data-ttu-id="0cfd8-155">Se agrega un contador a un ámbito del servicio desde el contador de una colección de extremos.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-155">A counter in a service scope is aggregated from counter in a collection of endpoints.</span></span>  
  
 <span data-ttu-id="0cfd8-156">Los contadores de rendimiento de la creación de una instancia de servicio aumentan cuando se crea un nuevo InstanceContext.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-156">Performance counters for service instance creation are incremented when a new InstanceContext is created.</span></span> <span data-ttu-id="0cfd8-157">Tenga en cuenta que también se crea un nuevo InstanceContext cuando recibe un mensaje de no activación (con un servicio existente), o cuando se conecta a la instancia de una sesión, finaliza la sesión y, a continuación, se vuelve a conectar desde otra sesión.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-157">Note that a new InstanceContext is created even when you receive a non-activating message (with an existing service), or when you connect to an instance from one session, end the session, and then reconnect from another session.</span></span>  
  
### <a name="endpoint-performance-counters"></a><span data-ttu-id="0cfd8-158">Contadores de rendimiento del punto de conexión</span><span class="sxs-lookup"><span data-stu-id="0cfd8-158">Endpoint performance counters</span></span>  

 <span data-ttu-id="0cfd8-159">Los contadores de rendimiento del punto de conexión permiten examinar datos que reflejan la aceptación de los mensajes por un punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-159">Endpoint performance counters enable you to look at data reflecting how an endpoint is accepting messages.</span></span> <span data-ttu-id="0cfd8-160">Pueden encontrarse en el objeto de rendimiento `ServiceModelEndpoint 4.0.0.0` al visualizarlo mediante el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-160">They can be found under the `ServiceModelEndpoint 4.0.0.0` performance object when viewing using the Performance Monitor.</span></span> <span data-ttu-id="0cfd8-161">Los nombres de las instancias se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-161">The instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName)@(endpoint listener address)`
  
 <span data-ttu-id="0cfd8-162">Los datos son similares a los recopilados para las operaciones individuales, pero solo se agregan a lo largo del punto de conexión.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-162">The data is similar to what is collected for individual operations, but is only aggregated across the endpoint.</span></span>  
  
 <span data-ttu-id="0cfd8-163">Un contador en un ámbito de extremo se agrega desde los contadores de una colección de operaciones.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-163">A counter in an endpoint scope is aggregated from counters in a collection of operations.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cfd8-164">Si dos puntos de conexión poseen nombres y direcciones de contrato idénticos, se asignan a la misma instancia del contador.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-164">If two endpoints have identical contract names and addresses, they are mapped to the same counter instance.</span></span>  
  
### <a name="operation-performance-counters"></a><span data-ttu-id="0cfd8-165">Contadores de rendimiento de la operación</span><span class="sxs-lookup"><span data-stu-id="0cfd8-165">Operation performance counters</span></span>  

 <span data-ttu-id="0cfd8-166">Los contadores de rendimiento de la operación se encuentran en el objeto de rendimiento `ServiceModelOperation 4.0.0.0` al visualizarlo con el monitor de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-166">Operation performance counters are found under the `ServiceModelOperation 4.0.0.0` performance object when viewing with the Performance Monitor.</span></span> <span data-ttu-id="0cfd8-167">Cada operación posee una instancia individual.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-167">Each operation has an individual instance.</span></span> <span data-ttu-id="0cfd8-168">Es decir, si un contrato determinado posee 10 operaciones, se asociarán 10 instancias de contador de operación a ese contrato.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-168">That is, if a given contract has 10 operations, 10 operation counter instances are associated with that contract.</span></span> <span data-ttu-id="0cfd8-169">Los nombres de las instancias de objeto se establecen utilizando el siguiente patrón:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-169">The object instances are named using the following pattern:</span></span>  
  
`(ServiceName).(ContractName).(OperationName)@(first endpoint listener address)`
  
 <span data-ttu-id="0cfd8-170">Este contador permite medir la utilización de la llamada y el buen rendimiento de la operación.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-170">This counter enables you to measure how the call is being used and how well the operation is performing.</span></span>  
  
 <span data-ttu-id="0cfd8-171">Cuando los contadores son visibles en varios ámbitos, los datos recopilados de un ámbito superior se agregan a los datos de los ámbitos inferiores.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-171">When counters are visible at multiple scopes, data gathered from a higher scope are aggregated with data from lower scopes.</span></span> <span data-ttu-id="0cfd8-172">Por ejemplo, `Calls` a un punto de conexión representa la suma de todas las llamadas de la operación en el punto de conexión; `Calls` a un servicio representa la suma de todas las llamadas a todos los puntos de conexión del servicio.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-172">For example, `Calls` at an endpoint represents the sum of all operation calls within the endpoint; `Calls` at a service represents the sum of all calls to all endpoints within the service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0cfd8-173">Si existen nombres de la operación duplicados en un contrato, solo se obtiene una instancia de contador para ambas operaciones.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-173">If you have duplicate operation names on a contract, you only get one counter instances for both operations.</span></span>  
  
## <a name="programming-the-wcf-performance-counters"></a><span data-ttu-id="0cfd8-174">Programación de los contadores de rendimiento de WCF</span><span class="sxs-lookup"><span data-stu-id="0cfd8-174">Programming the WCF Performance Counters</span></span>  

<span data-ttu-id="0cfd8-175">Se instalan varios archivos en la carpeta de instalación del SDK para que pueda tener acceso a los contadores de rendimiento de WCF mediante programación.</span><span class="sxs-lookup"><span data-stu-id="0cfd8-175">Several files are installed in the SDK install folder so that you can access the WCF performance counters programmatically.</span></span> <span data-ttu-id="0cfd8-176">Estos archivos se enumeran de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="0cfd8-176">These files are listed as follows:</span></span>
  
- <span data-ttu-id="0cfd8-177">*\_ServiceModelEndpointPerfCounters. VRG*</span><span class="sxs-lookup"><span data-stu-id="0cfd8-177">*\_ServiceModelEndpointPerfCounters.vrg*</span></span>
- <span data-ttu-id="0cfd8-178">*\_ServiceModelOperationPerfCounters. VRG*</span><span class="sxs-lookup"><span data-stu-id="0cfd8-178">*\_ServiceModelOperationPerfCounters.vrg*</span></span>
- <span data-ttu-id="0cfd8-179">*\_ServiceModelServicePerfCounters. VRG*</span><span class="sxs-lookup"><span data-stu-id="0cfd8-179">*\_ServiceModelServicePerfCounters.vrg*</span></span>  
- <span data-ttu-id="0cfd8-180">*\_SMSvcHostPerfCounters. VRG*</span><span class="sxs-lookup"><span data-stu-id="0cfd8-180">*\_SMSvcHostPerfCounters.vrg*</span></span>
- <span data-ttu-id="0cfd8-181">*\_TransactionBridgePerfCounters. VRG*</span><span class="sxs-lookup"><span data-stu-id="0cfd8-181">*\_TransactionBridgePerfCounters.vrg*</span></span>
  
<span data-ttu-id="0cfd8-182">Para obtener más información sobre cómo obtener acceso a los contadores mediante programación, vea [arquitectura de programación del contador de rendimiento](/previous-versions/visualstudio/visual-studio-2008/5f9bkxzf(v=vs.90)).</span><span class="sxs-lookup"><span data-stu-id="0cfd8-182">For more information on how to access the counters programmatically, see [Performance Counter Programming Architecture](/previous-versions/visualstudio/visual-studio-2008/5f9bkxzf(v=vs.90)).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0cfd8-183">Vea también</span><span class="sxs-lookup"><span data-stu-id="0cfd8-183">See also</span></span>

- [<span data-ttu-id="0cfd8-184">Administración y diagnóstico</span><span class="sxs-lookup"><span data-stu-id="0cfd8-184">Administration and Diagnostics</span></span>](../index.md)
