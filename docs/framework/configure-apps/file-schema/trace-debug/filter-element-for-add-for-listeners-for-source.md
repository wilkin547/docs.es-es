---
title: Elemento @no__t 0 para <add> para <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: ec288685f47c8a35e2371c31d359b604a4967196
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697171"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="38ec5-102">\<filter > elemento para \<add > para \<listeners > para \<source ></span><span class="sxs-lookup"><span data-stu-id="38ec5-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>
<span data-ttu-id="38ec5-103">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="38ec5-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="38ec5-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="38ec5-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="38ec5-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="38ec5-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="38ec5-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="38ec5-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="38ec5-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="38ec5-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="38ec5-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="38ec5-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9[ **&nbsp;2add >** ](add-element-for-listeners-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="38ec5-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)</span></span>  
<span data-ttu-id="38ec5-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 @ no__t-8 @ no__t-9 @ no__t-10 @ no__t-11 **&nbsp;3filter >**</span><span class="sxs-lookup"><span data-stu-id="38ec5-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ec5-111">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38ec5-111">Syntax</span></span>  
  
```xml  
<filter   
  type="traceFilterClassName"   
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38ec5-112">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="38ec5-112">Attributes and Elements</span></span>  
 <span data-ttu-id="38ec5-113">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="38ec5-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38ec5-114">Atributos</span><span class="sxs-lookup"><span data-stu-id="38ec5-114">Attributes</span></span>  
  
|<span data-ttu-id="38ec5-115">Atributo</span><span class="sxs-lookup"><span data-stu-id="38ec5-115">Attribute</span></span>|<span data-ttu-id="38ec5-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ec5-116">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="38ec5-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="38ec5-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="38ec5-118">Especifica el tipo del filtro, que debe heredar de la clase <xref:System.Diagnostics.TraceFilter>.</span><span class="sxs-lookup"><span data-stu-id="38ec5-118">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="38ec5-119">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad <xref:System.Type.FullName%2A> del tipo, o puede usar el nombre de tipo completo, incluida la información del ensamblado, que corresponde a la propiedad <xref:System.Type.AssemblyQualifiedName%2A>.</span><span class="sxs-lookup"><span data-stu-id="38ec5-119">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="38ec5-120">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="38ec5-120">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="38ec5-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="38ec5-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="38ec5-122">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="38ec5-122">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38ec5-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="38ec5-123">Child Elements</span></span>  
 <span data-ttu-id="38ec5-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="38ec5-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38ec5-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="38ec5-125">Parent Elements</span></span>  
  
|<span data-ttu-id="38ec5-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="38ec5-126">Element</span></span>|<span data-ttu-id="38ec5-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="38ec5-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="38ec5-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="38ec5-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="38ec5-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="38ec5-130">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-130">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="38ec5-131">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-131">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="38ec5-132">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="38ec5-132">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="38ec5-133">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="38ec5-133">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="38ec5-134">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-134">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38ec5-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="38ec5-135">Remarks</span></span>  
 <span data-ttu-id="38ec5-136">El elemento `<filter>` debe estar incluido en un elemento `<add>` para un agente de escucha de origen de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en un [> \<sharedListeners](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="38ec5-136">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="38ec5-137">Si el agente de escucha se define en un [> \<sharedListeners](sharedlisteners-element.md), el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="38ec5-137">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="38ec5-138">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="38ec5-138">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38ec5-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="38ec5-139">Example</span></span>  
 <span data-ttu-id="38ec5-140">En el ejemplo siguiente se muestra cómo usar el elemento `<filter>` para agregar un filtro al agente de escucha `console` en la colección `Listeners` para el origen de seguimiento `myTraceSource`, especificando el nivel de evento de filtro como `Error`.</span><span class="sxs-lookup"><span data-stu-id="38ec5-140">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="38ec5-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="38ec5-141">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="38ec5-142">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="38ec5-142">Trace and Debug Settings Schema</span></span>](index.md)
