---
title: Configuración recomendada para el seguimiento y el registro de mensajes
ms.date: 03/30/2017
ms.assetid: c6aca6e8-704e-4779-a9ef-50c46850249e
ms.openlocfilehash: 9d2586570a3f590735c2a8e1ca176580886c8d92
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84578921"
---
# <a name="recommended-settings-for-tracing-and-message-logging"></a><span data-ttu-id="9b96e-102">Configuración recomendada para el seguimiento y el registro de mensajes</span><span class="sxs-lookup"><span data-stu-id="9b96e-102">Recommended Settings for Tracing and Message Logging</span></span>
<span data-ttu-id="9b96e-103">En este tema se describen la traza recomendada y configuración del registro de mensajes para los entornos operativos diferentes.</span><span class="sxs-lookup"><span data-stu-id="9b96e-103">This topic describes recommended tracing and message logging settings for different operating environments.</span></span>  
  
## <a name="recommended-settings-for-a-production-environment"></a><span data-ttu-id="9b96e-104">Configuración recomendada para un entorno de producción</span><span class="sxs-lookup"><span data-stu-id="9b96e-104">Recommended Settings for a Production Environment</span></span>  
 <span data-ttu-id="9b96e-105">Para un entorno de producción, si está utilizando los orígenes de seguimiento de WCF, establezca `switchValue` a Advertencia.</span><span class="sxs-lookup"><span data-stu-id="9b96e-105">For a production environment, if you are using WCF trace sources, set the `switchValue` to Warning.</span></span> <span data-ttu-id="9b96e-106">Si está utilizando el origen de seguimiento de WCF `System.ServiceModel`, establezca el atributo `switchValue` a `Warning` y el atributo `propagateActivity` a `true`.</span><span class="sxs-lookup"><span data-stu-id="9b96e-106">If you are using the WCF `System.ServiceModel` trace source, set the `switchValue` attribute to `Warning` and the `propagateActivity` attribute to `true`.</span></span> <span data-ttu-id="9b96e-107">Si está utilizando un origen de seguimiento definido por un usuario, establezca el atributo `switchValue` a `Warning, ActivityTracing`.</span><span class="sxs-lookup"><span data-stu-id="9b96e-107">If you are using a user-defined trace source, set the `switchValue` attribute to `Warning, ActivityTracing`.</span></span> <span data-ttu-id="9b96e-108">Esto se puede hacer manualmente mediante la [herramienta editor de configuración (SvcConfigEditor. exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span><span class="sxs-lookup"><span data-stu-id="9b96e-108">This can be done manually using the [Configuration Editor Tool (SvcConfigEditor.exe)](../../configuration-editor-tool-svcconfigeditor-exe.md).</span></span> <span data-ttu-id="9b96e-109">Si no visualiza una repercusión en el rendimiento, puede establecer el atributo `switchValue` en `Information` en todos los casos mencionados previamente, lo cual genera una cantidad bastante grande de información de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b96e-109">If you do not anticipate a hit in performance, you can set the `switchValue` attribute to `Information` in all the previously mentioned cases, which generates a fairly large amount of trace data.</span></span> <span data-ttu-id="9b96e-110">El ejemplo siguiente muestra estos valores recomendados.</span><span class="sxs-lookup"><span data-stu-id="9b96e-110">The following example demonstrates these recommended settings.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Warning"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Warning, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
<system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="recommended-settings-for-deployment-or-debugging"></a><span data-ttu-id="9b96e-111">Configuración recomendada para la implementación o depurando</span><span class="sxs-lookup"><span data-stu-id="9b96e-111">Recommended Settings for Deployment or Debugging</span></span>  
 <span data-ttu-id="9b96e-112">Para la implementar o depurar el entorno, elija `Information` o `Verbose`, junto con `ActivityTracing` para o un origen de seguimiento definido por el usuario o `System.ServiceModel`.</span><span class="sxs-lookup"><span data-stu-id="9b96e-112">For deployment or debugging environment, choose `Information` or `Verbose`, along with `ActivityTracing` for either a user-defined or `System.ServiceModel` trace source.</span></span> <span data-ttu-id="9b96e-113">Para mejorar la depuración, debería agregar también un origen de seguimiento adicional (`System.ServiceModel.MessageLogging`) a la configuración para habilitar el registro de mensajes.</span><span class="sxs-lookup"><span data-stu-id="9b96e-113">To enhance debugging, you should also add an additional trace source (`System.ServiceModel.MessageLogging`) to the configuration to enable message logging.</span></span> <span data-ttu-id="9b96e-114">Tenga en cuenta que el atributo `switchValue` no tiene ningún impacto en este origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9b96e-114">Notice that the `switchValue` attribute has no impact on this trace source.</span></span>  
  
 <span data-ttu-id="9b96e-115">El ejemplo siguiente muestra los valores recomendados, mediante un agente de escucha compartido que utiliza `XmlWriterTraceListener`.</span><span class="sxs-lookup"><span data-stu-id="9b96e-115">The following example demonstrates the recommended settings, using a shared listener that utilizes the `XmlWriterTraceListener`.</span></span>  
  
```xml  
<configuration>  
 <system.diagnostics>  
  <sources>  
    <source name="System.ServiceModel"  
            switchValue="Information, ActivityTracing"  
            propagateActivity="true" >  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="System.ServiceModel.MessageLogging">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
    <source name="myUserTraceSource"  
            switchValue="Information, ActivityTracing">  
      <listeners>  
        <add name="xml"/>  
      </listeners>  
    </source>  
  </sources>  
  <sharedListeners>  
    <add name="xml"  
         type="System.Diagnostics.XmlWriterTraceListener"  
               initializeData="C:\logs\Traces.svclog" />  
  </sharedListeners>  
 </system.diagnostics>  
  
 <system.serviceModel>  
  <diagnostics wmiProviderEnabled="true">  
      <messageLogging
           logEntireMessage="true"
           logMalformedMessages="true"  
           logMessagesAtServiceLevel="true"
           logMessagesAtTransportLevel="true"  
           maxMessagesToLog="3000"
       />  
  </diagnostics>  
 </system.serviceModel>  
</configuration>  
```  
  
## <a name="using-wmi-to-modify-settings"></a><span data-ttu-id="9b96e-116">Utilizar WMI para modificar la configuración</span><span class="sxs-lookup"><span data-stu-id="9b96e-116">Using WMI to Modify Settings</span></span>  
 <span data-ttu-id="9b96e-117">Puede utilizar WMI para cambiar la configuración en el tiempo de ejecución (habilitando el atributo `wmiProviderEnabled` en la configuración, tal y como se ha mostrado previamente en el ejemplo de configuración).</span><span class="sxs-lookup"><span data-stu-id="9b96e-117">You can use WMI to change configuration settings at runtime (by enabling the `wmiProviderEnabled` attribute in the configuration, as demonstrated in the previously configuration example).</span></span> <span data-ttu-id="9b96e-118">Por ejemplo, puede utilizar WMI dentro del CIM Studio para cambiar el origen de seguimiento desde Advertencia a Información en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9b96e-118">For example, you can use WMI within the CIM Studio to change the trace source levels from Warning to Information at runtime.</span></span> <span data-ttu-id="9b96e-119">Debe ser consciente de que el coste del rendimiento de la depuración activa de este modo puede ser muy elevado.</span><span class="sxs-lookup"><span data-stu-id="9b96e-119">You should be aware that the performance cost of live debugging in this way can be very high.</span></span> <span data-ttu-id="9b96e-120">Para obtener más información sobre el uso de WMI, consulte el tema [uso de instrumental de administración de Windows para diagnósticos](../wmi/index.md) .</span><span class="sxs-lookup"><span data-stu-id="9b96e-120">For more information about using WMI, see the [Using Windows Management Instrumentation for Diagnostics](../wmi/index.md) topic.</span></span>  
  
## <a name="enable-correlated-events-in-aspnet-tracing"></a><span data-ttu-id="9b96e-121">Habilitación de eventos correlativos en el seguimiento ASP.NET</span><span class="sxs-lookup"><span data-stu-id="9b96e-121">Enable Correlated Events in ASP.NET Tracing</span></span>  
 <span data-ttu-id="9b96e-122">Los eventos ASP.NET no establecen el id. de correlación (ActivityID) a menos que esté activado el seguimiento de evento ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="9b96e-122">ASP.NET events do not set the correlation ID (ActivityID) unless ASP.NET event tracing is turned on.</span></span> <span data-ttu-id="9b96e-123">Para ver los eventos correlacionados correctamente, tiene que activar el seguimiento de eventos de ASP.NET con el siguiente comando en la consola de comandos, que se puede invocar desde **Inicio**, **Ejecutar** y escriba **cmd**.</span><span class="sxs-lookup"><span data-stu-id="9b96e-123">To see correlated events properly, you have to turn on ASP.NET events tracing using the following command in the command console, which can be invoked by going to **Start**, **Run** and type **cmd**,</span></span>  
  
```console  
logman start mytrace -pf logman.providers -o test.etl –ets  
```  
  
 <span data-ttu-id="9b96e-124">Para desactivar el seguimiento de eventos ASP.NET, utilice el siguiente comando,</span><span class="sxs-lookup"><span data-stu-id="9b96e-124">To turn off tracing of ASP.NET events, use the following command,</span></span>  
  
```console
logman stop mytrace -ets  
```  
  
## <a name="see-also"></a><span data-ttu-id="9b96e-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="9b96e-125">See also</span></span>

- [<span data-ttu-id="9b96e-126">Uso de Instrumental de administración de Windows para diagnósticos</span><span class="sxs-lookup"><span data-stu-id="9b96e-126">Using Windows Management Instrumentation for Diagnostics</span></span>](../wmi/index.md)
