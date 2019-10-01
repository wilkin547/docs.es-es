---
title: Elemento @no__t 0 para <add> para <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: f6b1ec99c5aab8e85df7f1920aca32f49a5be066
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699360"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="378f1-102">\<filter > elemento para \<add > para \<listeners > para \<trace ></span><span class="sxs-lookup"><span data-stu-id="378f1-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="378f1-103">Agrega un filtro a un agente de escucha en la colección `Listeners` para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="378f1-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  
  
[<span data-ttu-id="378f1-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="378f1-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="378f1-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="378f1-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="378f1-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="378f1-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="378f1-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="378f1-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="378f1-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0add >** ](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="378f1-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>  
<span data-ttu-id="378f1-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 **&nbsp;1filter >**</span><span class="sxs-lookup"><span data-stu-id="378f1-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378f1-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="378f1-110">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="378f1-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="378f1-111">Attributes and Elements</span></span>  
 <span data-ttu-id="378f1-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="378f1-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="378f1-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="378f1-113">Attributes</span></span>  
  
|<span data-ttu-id="378f1-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="378f1-114">Attribute</span></span>|<span data-ttu-id="378f1-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="378f1-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="378f1-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="378f1-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="378f1-117">Especifica el tipo del filtro, que debe heredar de la clase <xref:System.Diagnostics.TraceFilter>.</span><span class="sxs-lookup"><span data-stu-id="378f1-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="378f1-118">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad <xref:System.Type.FullName%2A> del tipo, o puede usar el nombre de tipo completo, incluida la información del ensamblado, que corresponde a la propiedad <xref:System.Type.AssemblyQualifiedName%2A>.</span><span class="sxs-lookup"><span data-stu-id="378f1-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="378f1-119">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="378f1-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="378f1-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="378f1-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="378f1-121">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="378f1-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="378f1-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="378f1-122">Child Elements</span></span>  
 <span data-ttu-id="378f1-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="378f1-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="378f1-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="378f1-124">Parent Elements</span></span>  
  
|<span data-ttu-id="378f1-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="378f1-125">Element</span></span>|<span data-ttu-id="378f1-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="378f1-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="378f1-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="378f1-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="378f1-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="378f1-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="378f1-129">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="378f1-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="378f1-130">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="378f1-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="378f1-131">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="378f1-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="378f1-132">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="378f1-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="378f1-133">Comentarios</span><span class="sxs-lookup"><span data-stu-id="378f1-133">Remarks</span></span>  
 <span data-ttu-id="378f1-134">El elemento `<filter>` debe estar incluido en un elemento `<add>` para un agente de escucha de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en un [> \<sharedListeners](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="378f1-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="378f1-135">Si el agente de escucha se define en un [> \<sharedListeners](sharedlisteners-element.md), el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="378f1-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="378f1-136">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="378f1-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="378f1-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="378f1-137">Example</span></span>  
 <span data-ttu-id="378f1-138">En el ejemplo siguiente se muestra cómo usar el elemento `<filter>` para agregar un filtro al agente de escucha `console` en la colección `Listeners` para el seguimiento, especificando el nivel de evento de filtro como `Error`.</span><span class="sxs-lookup"><span data-stu-id="378f1-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="378f1-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="378f1-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="378f1-140">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="378f1-140">Trace and Debug Settings Schema</span></span>](index.md)
