---
title: Elemento <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 853bc94978218fd4d426e6070b3a36e20435cd6d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920491"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="425bd-102">\<agentes de escucha > elemento \<de > de origen</span><span class="sxs-lookup"><span data-stu-id="425bd-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="425bd-103">Agrega o quita los agentes de escucha <xref:System.Diagnostics.TraceSource.Listeners%2A> de la colección <xref:System.Diagnostics.TraceSource>para.</span><span class="sxs-lookup"><span data-stu-id="425bd-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="425bd-104">Un agente de escucha dirige los resultados del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="425bd-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
 <span data-ttu-id="425bd-105">\<configuration></span><span class="sxs-lookup"><span data-stu-id="425bd-105">\<configuration></span></span>  
<span data-ttu-id="425bd-106">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="425bd-106">\<system.diagnostics></span></span>  
<span data-ttu-id="425bd-107">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="425bd-107">\<sources></span></span>  
<span data-ttu-id="425bd-108">\<> de origen</span><span class="sxs-lookup"><span data-stu-id="425bd-108">\<source></span></span>  
<span data-ttu-id="425bd-109">\<agentes de escucha > elemento</span><span class="sxs-lookup"><span data-stu-id="425bd-109">\<listeners> Element</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="425bd-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="425bd-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="425bd-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="425bd-111">Attributes and Elements</span></span>  
 <span data-ttu-id="425bd-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="425bd-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="425bd-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="425bd-113">Attributes</span></span>  
 <span data-ttu-id="425bd-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="425bd-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="425bd-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="425bd-115">Child Elements</span></span>  
  
|<span data-ttu-id="425bd-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="425bd-116">Element</span></span>|<span data-ttu-id="425bd-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="425bd-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="425bd-118">\<add></span><span class="sxs-lookup"><span data-stu-id="425bd-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="425bd-119">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="425bd-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="425bd-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="425bd-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="425bd-121">Quita un agente de escucha de `Listeners` la colección.</span><span class="sxs-lookup"><span data-stu-id="425bd-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="425bd-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="425bd-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="425bd-123">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="425bd-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="425bd-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="425bd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="425bd-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="425bd-125">Element</span></span>|<span data-ttu-id="425bd-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="425bd-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="425bd-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="425bd-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="425bd-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="425bd-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="425bd-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="425bd-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="425bd-130">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="425bd-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="425bd-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="425bd-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="425bd-132">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="425bd-132">Configuration File</span></span>  
 <span data-ttu-id="425bd-133">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="425bd-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="425bd-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="425bd-134">Example</span></span>  
 <span data-ttu-id="425bd-135">En el ejemplo siguiente se muestra cómo usar `<listeners>` el elemento para agregar un agente de escucha de seguimiento `mySource` de la consola al origen y quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="425bd-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="425bd-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="425bd-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="425bd-137">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="425bd-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="425bd-138">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="425bd-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
