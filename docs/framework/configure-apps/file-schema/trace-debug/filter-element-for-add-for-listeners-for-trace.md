---
title: '&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 85d81beead84be48730ba3a4469e8efdff1bbb0b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523702"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="d35d7-102">&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;</span><span class="sxs-lookup"><span data-stu-id="d35d7-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="d35d7-103">Agrega un filtro a un agente de escucha en el `Listeners` colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d35d7-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
 <span data-ttu-id="d35d7-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d35d7-104">\<configuration></span></span>  
<span data-ttu-id="d35d7-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d35d7-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d35d7-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="d35d7-106">\<trace></span></span>  
<span data-ttu-id="d35d7-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="d35d7-107">\<listeners></span></span>  
<span data-ttu-id="d35d7-108">\<add></span><span class="sxs-lookup"><span data-stu-id="d35d7-108">\<add></span></span>  
<span data-ttu-id="d35d7-109">\<filter></span><span class="sxs-lookup"><span data-stu-id="d35d7-109">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d35d7-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d35d7-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d35d7-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d35d7-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d35d7-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d35d7-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d35d7-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d35d7-113">Attributes</span></span>  
  
|<span data-ttu-id="d35d7-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d35d7-114">Attribute</span></span>|<span data-ttu-id="d35d7-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d35d7-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d35d7-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d35d7-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d35d7-117">Especifica el tipo del filtro, que se debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="d35d7-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="d35d7-118">Puede usar el nombre calificado de espacio de nombres del tipo, que se corresponde con el tipo <xref:System.Type.FullName%2A> propiedad, o bien puede usar el nombre de tipo completo incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d35d7-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="d35d7-119">Para obtener información acerca de los nombres de tipo completo, vea [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d35d7-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d35d7-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d35d7-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d35d7-121">Cadena pasada al constructor de la clase de filtro especificado.</span><span class="sxs-lookup"><span data-stu-id="d35d7-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d35d7-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d35d7-122">Child Elements</span></span>  
 <span data-ttu-id="d35d7-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d35d7-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d35d7-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d35d7-124">Parent Elements</span></span>  
  
|<span data-ttu-id="d35d7-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d35d7-125">Element</span></span>|<span data-ttu-id="d35d7-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="d35d7-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d35d7-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d35d7-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d35d7-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d35d7-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d35d7-129">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d35d7-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d35d7-130">Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d35d7-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d35d7-131">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="d35d7-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="d35d7-132">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="d35d7-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d35d7-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d35d7-133">Remarks</span></span>  
 <span data-ttu-id="d35d7-134">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de seguimiento que especifica el tipo del agente de escucha, no sólo el nombre de un agente de escucha definido en un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="d35d7-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md).</span></span> <span data-ttu-id="d35d7-135">Si el agente de escucha se define en un [ \<sharedListeners >](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="d35d7-135">If the listener is defined in a [\<sharedListeners>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="d35d7-136">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d35d7-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d35d7-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d35d7-137">Example</span></span>  
 <span data-ttu-id="d35d7-138">El ejemplo siguiente muestra cómo usar el `<filter>` elemento para agregar un filtro al agente de escucha `console` en el `Listeners` colección para seguimiento, especificando el nivel de evento de filtro como `Error`.</span><span class="sxs-lookup"><span data-stu-id="d35d7-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
        <remove name="Default" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d35d7-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="d35d7-139">See also</span></span>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="d35d7-140">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="d35d7-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
