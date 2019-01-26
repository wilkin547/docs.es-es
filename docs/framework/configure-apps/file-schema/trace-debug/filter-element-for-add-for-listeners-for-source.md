---
title: '&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;los agentes de escucha&gt; para &lt;origen&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 76aecf0b97a1b203d790dc34d83bc01ea1de5236
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083293"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="fa74e-102">&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;los agentes de escucha&gt; para &lt;origen&gt;</span><span class="sxs-lookup"><span data-stu-id="fa74e-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="fa74e-103">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="fa74e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fa74e-104">\<configuration></span></span>  
<span data-ttu-id="fa74e-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="fa74e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="fa74e-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="fa74e-106">\<sources></span></span>  
<span data-ttu-id="fa74e-107">\<source></span><span class="sxs-lookup"><span data-stu-id="fa74e-107">\<source></span></span>  
<span data-ttu-id="fa74e-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="fa74e-108">\<listeners></span></span>  
<span data-ttu-id="fa74e-109">\<add></span><span class="sxs-lookup"><span data-stu-id="fa74e-109">\<add></span></span>  
<span data-ttu-id="fa74e-110">\<filter></span><span class="sxs-lookup"><span data-stu-id="fa74e-110">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa74e-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa74e-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa74e-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa74e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="fa74e-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa74e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa74e-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa74e-114">Attributes</span></span>  
  
|<span data-ttu-id="fa74e-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="fa74e-115">Attribute</span></span>|<span data-ttu-id="fa74e-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa74e-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="fa74e-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="fa74e-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="fa74e-118">Especifica el tipo del filtro, que se debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="fa74e-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="fa74e-119">Puede usar el nombre calificado de espacio de nombres del tipo, que se corresponde con el tipo <xref:System.Type.FullName%2A> propiedad, o bien puede usar el nombre de tipo completo incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fa74e-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="fa74e-120">Para obtener información acerca de los nombres de tipo completo, vea [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fa74e-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fa74e-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fa74e-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fa74e-122">Cadena pasada al constructor de la clase de filtro especificado.</span><span class="sxs-lookup"><span data-stu-id="fa74e-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa74e-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa74e-123">Child Elements</span></span>  
 <span data-ttu-id="fa74e-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="fa74e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa74e-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa74e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="fa74e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa74e-126">Element</span></span>|<span data-ttu-id="fa74e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa74e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa74e-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa74e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fa74e-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fa74e-130">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fa74e-131">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fa74e-132">Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa74e-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="fa74e-133">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="fa74e-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="fa74e-134">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa74e-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa74e-135">Remarks</span></span>  
 <span data-ttu-id="fa74e-136">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha del origen de seguimiento que especifica el tipo del agente de escucha, no sólo el nombre de un agente de escucha definido en un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="fa74e-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="fa74e-137">Si el agente de escucha se define en un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="fa74e-137">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="fa74e-138">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa74e-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa74e-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa74e-139">Example</span></span>  
 <span data-ttu-id="fa74e-140">El ejemplo siguiente muestra cómo usar el `<filter>` elemento para agregar un filtro al agente de escucha `console` en el `Listeners` recopilación para el origen de seguimiento `myTraceSource`, especificando el nivel de evento de filtro como `Error`.</span><span class="sxs-lookup"><span data-stu-id="fa74e-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" switchName="SourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error" />  
          </add>  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="SourceSwitch" value="Warning" />  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fa74e-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa74e-141">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="fa74e-142">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="fa74e-142">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
