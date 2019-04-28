---
title: Elemento <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: b15a30fb6d356f92312bf33bc1964c7922ba1383
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673763"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="4bfe5-102">\<los agentes de escucha > (elemento) para \<origen ></span><span class="sxs-lookup"><span data-stu-id="4bfe5-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="4bfe5-103">Agrega o quita los agentes de escucha en el <xref:System.Diagnostics.TraceSource.Listeners%2A> colección para un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="4bfe5-104">Un agente de escucha dirige los resultados del seguimiento a un destino apropiado, como un registro, la ventana o el archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="4bfe5-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4bfe5-105">\<configuration></span></span>  
<span data-ttu-id="4bfe5-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="4bfe5-106">\<system.diagnostics></span></span>  
<span data-ttu-id="4bfe5-107">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="4bfe5-107">\<sources></span></span>  
<span data-ttu-id="4bfe5-108">\<source></span><span class="sxs-lookup"><span data-stu-id="4bfe5-108">\<source></span></span>  
<span data-ttu-id="4bfe5-109">\<los agentes de escucha > elemento</span><span class="sxs-lookup"><span data-stu-id="4bfe5-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bfe5-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4bfe5-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4bfe5-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4bfe5-111">Attributes and Elements</span></span>  
 <span data-ttu-id="4bfe5-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4bfe5-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="4bfe5-113">Attributes</span></span>  
 <span data-ttu-id="4bfe5-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4bfe5-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4bfe5-115">Child Elements</span></span>  
  
|<span data-ttu-id="4bfe5-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bfe5-116">Element</span></span>|<span data-ttu-id="4bfe5-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bfe5-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4bfe5-118">\<add></span><span class="sxs-lookup"><span data-stu-id="4bfe5-118">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-source.md)|<span data-ttu-id="4bfe5-119">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="4bfe5-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="4bfe5-120">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-source.md)|<span data-ttu-id="4bfe5-121">Quita un agente de escucha el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="4bfe5-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="4bfe5-122">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)|<span data-ttu-id="4bfe5-123">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4bfe5-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4bfe5-124">Parent Elements</span></span>  
  
|<span data-ttu-id="4bfe5-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="4bfe5-125">Element</span></span>|<span data-ttu-id="4bfe5-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="4bfe5-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4bfe5-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4bfe5-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="4bfe5-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="4bfe5-130">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4bfe5-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4bfe5-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="4bfe5-132">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="4bfe5-132">Configuration File</span></span>  
 <span data-ttu-id="4bfe5-133">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4bfe5-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4bfe5-134">Example</span></span>  
 <span data-ttu-id="4bfe5-135">El ejemplo siguiente muestra cómo usar el `<listeners>` elemento para agregar un agente de escucha de seguimiento de consola a la `mySource` origen y para quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4bfe5-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4bfe5-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="4bfe5-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="4bfe5-137">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="4bfe5-137">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="4bfe5-138">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="4bfe5-138">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
