---
title: <filter>Elemento <add> para <listeners> for for<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153471"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="5959f-102">\<filtrar> \<elemento para \<agregar> \<para los agentes de escucha> para el seguimiento></span><span class="sxs-lookup"><span data-stu-id="5959f-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="5959f-103">Agrega un filtro a un `Listeners` agente de escucha de la colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5959f-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

<span data-ttu-id="5959f-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="5959f-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="5959f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="5959f-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="5959f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<rastreo>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="5959f-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="5959f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="5959f-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="5959f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<añadir>**](add-element-for-listeners-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="5959f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)</span></span>\
<span data-ttu-id="5959f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>de filtro**</span><span class="sxs-lookup"><span data-stu-id="5959f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="5959f-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5959f-110">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5959f-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5959f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5959f-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5959f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5959f-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="5959f-113">Attributes</span></span>  
  
|<span data-ttu-id="5959f-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="5959f-114">Attribute</span></span>|<span data-ttu-id="5959f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="5959f-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="5959f-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="5959f-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="5959f-117">Especifica el tipo del filtro, que <xref:System.Diagnostics.TraceFilter> debe heredar de la clase.</span><span class="sxs-lookup"><span data-stu-id="5959f-117">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="5959f-118">Puede usar el nombre completo del espacio de nombres del <xref:System.Type.FullName%2A> tipo, que corresponde a la propiedad del tipo, o puede <xref:System.Type.AssemblyQualifiedName%2A> usar el nombre de tipo completo, incluida la información del ensamblado, que corresponde a la propiedad.</span><span class="sxs-lookup"><span data-stu-id="5959f-118">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="5959f-119">Para obtener información acerca de los nombres de tipo completos, vea Especificar nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="5959f-119">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="5959f-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="5959f-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="5959f-121">La cadena que se pasa al constructor para la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="5959f-121">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5959f-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5959f-122">Child Elements</span></span>  
 <span data-ttu-id="5959f-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5959f-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5959f-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5959f-124">Parent Elements</span></span>  
  
|<span data-ttu-id="5959f-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="5959f-125">Element</span></span>|<span data-ttu-id="5959f-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="5959f-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5959f-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5959f-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5959f-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5959f-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="5959f-129">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5959f-129">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5959f-130">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="5959f-130">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="5959f-131">Los agentes de escucha dirigen la salida de seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="5959f-131">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="5959f-132">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="5959f-132">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5959f-133">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5959f-133">Remarks</span></span>  
 <span data-ttu-id="5959f-134">El `<filter>` elemento debe estar `<add>` contenido en un elemento para un agente de escucha de seguimiento que especifica el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en un [ \<sharedListeners>](sharedlisteners-element.md).</span><span class="sxs-lookup"><span data-stu-id="5959f-134">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="5959f-135">Si el agente de escucha se define en un [ \<sharedListeners>](sharedlisteners-element.md), el filtro de ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="5959f-135">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="5959f-136">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5959f-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5959f-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5959f-137">Example</span></span>  
 <span data-ttu-id="5959f-138">En el ejemplo siguiente `<filter>` se muestra cómo utilizar `console` el `Listeners` elemento para agregar un filtro al `Error`agente de escucha de la colección para el seguimiento, especificando el nivel de evento de filtro como .</span><span class="sxs-lookup"><span data-stu-id="5959f-138">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5959f-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="5959f-139">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="5959f-140">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="5959f-140">Trace and Debug Settings Schema</span></span>](index.md)
