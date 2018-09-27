---
title: '&lt;los agentes de escucha&gt; (elemento) para &lt;origen&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 86b85779f4eff72e8ab910a5ccd32fd369270509
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47399013"
---
# <a name="ltlistenersgt-element-for-ltsourcegt"></a><span data-ttu-id="95805-102">&lt;los agentes de escucha&gt; (elemento) para &lt;origen&gt;</span><span class="sxs-lookup"><span data-stu-id="95805-102">&lt;listeners&gt; Element for &lt;source&gt;</span></span>
<span data-ttu-id="95805-103">Agrega o quita los agentes de escucha en el <xref:System.Diagnostics.TraceSource.Listeners%2A> colección para un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="95805-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="95805-104">Un agente de escucha dirige los resultados del seguimiento a un destino apropiado, como un registro, la ventana o el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="95805-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="95805-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="95805-105">\<configuration></span></span>  
<span data-ttu-id="95805-106">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="95805-106">\<system.diagnostics></span></span>  
<span data-ttu-id="95805-107">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="95805-107">\<sources></span></span>  
<span data-ttu-id="95805-108">\<origen ></span><span class="sxs-lookup"><span data-stu-id="95805-108">\<source></span></span>  
<span data-ttu-id="95805-109">\<los agentes de escucha > elemento</span><span class="sxs-lookup"><span data-stu-id="95805-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95805-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="95805-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="95805-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="95805-111">Attributes and Elements</span></span>  
 <span data-ttu-id="95805-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="95805-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="95805-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="95805-113">Attributes</span></span>  
 <span data-ttu-id="95805-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="95805-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="95805-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="95805-115">Child Elements</span></span>  
  
|<span data-ttu-id="95805-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="95805-116">Element</span></span>|<span data-ttu-id="95805-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="95805-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="95805-118">\<add></span><span class="sxs-lookup"><span data-stu-id="95805-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="95805-119">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="95805-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="95805-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="95805-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="95805-121">Quita un agente de escucha el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="95805-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="95805-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="95805-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="95805-123">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95805-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="95805-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="95805-124">Parent Elements</span></span>  
  
|<span data-ttu-id="95805-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="95805-125">Element</span></span>|<span data-ttu-id="95805-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="95805-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="95805-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="95805-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="95805-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95805-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="95805-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95805-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="95805-130">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="95805-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="95805-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="95805-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="95805-132">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="95805-132">Configuration File</span></span>  
 <span data-ttu-id="95805-133">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="95805-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="95805-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="95805-134">Example</span></span>  
 <span data-ttu-id="95805-135">El ejemplo siguiente muestra cómo usar el `<listeners>` elemento para agregar un agente de escucha de seguimiento de consola a la `mySource` origen y para quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="95805-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="95805-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="95805-136">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="95805-137">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="95805-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="95805-138">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="95805-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
