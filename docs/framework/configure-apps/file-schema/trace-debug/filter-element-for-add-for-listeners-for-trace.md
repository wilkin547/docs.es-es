---
description: 'Más información sobre: <filter> elemento para <add> para <listeners><trace>'
title: <filter>(Elemento <add> ) para para <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: a47903a696fcbf2cd7f4eecda526f93955a31f11
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99754490"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="2a03e-103">\<filter>(Elemento \<add> ) para para \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="2a03e-103">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>

<span data-ttu-id="2a03e-104">Agrega un filtro a un agente de escucha de la `Listeners` colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2a03e-104">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="2a03e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a03e-105">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a03e-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="2a03e-106">Attributes and Elements</span></span>  

 <span data-ttu-id="2a03e-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="2a03e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a03e-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="2a03e-108">Attributes</span></span>  
  
|<span data-ttu-id="2a03e-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="2a03e-109">Attribute</span></span>|<span data-ttu-id="2a03e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a03e-110">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="2a03e-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="2a03e-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="2a03e-112">Especifica el tipo del filtro, que debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="2a03e-112">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="2a03e-113">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad del tipo <xref:System.Type.FullName%2A> , o puede usar el nombre de tipo completo, incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="2a03e-113">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="2a03e-114">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="2a03e-114">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="2a03e-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="2a03e-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="2a03e-116">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="2a03e-116">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a03e-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="2a03e-117">Child Elements</span></span>  

 <span data-ttu-id="2a03e-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="2a03e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2a03e-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="2a03e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="2a03e-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="2a03e-120">Element</span></span>|<span data-ttu-id="2a03e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="2a03e-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="2a03e-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="2a03e-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="2a03e-123">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2a03e-123">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="2a03e-124">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="2a03e-124">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="2a03e-125">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="2a03e-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="2a03e-126">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="2a03e-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="2a03e-127">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="2a03e-127">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a03e-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2a03e-128">Remarks</span></span>  

 <span data-ttu-id="2a03e-129">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="2a03e-129">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="2a03e-130">Si el agente de escucha se define en [\<sharedListeners>](sharedlisteners-element.md) , el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="2a03e-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="2a03e-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="2a03e-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2a03e-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="2a03e-132">Example</span></span>  

 <span data-ttu-id="2a03e-133">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente `console` de escucha de la `Listeners` colección para el seguimiento, especificando el nivel de evento de filtro como `Error` .</span><span class="sxs-lookup"><span data-stu-id="2a03e-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2a03e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a03e-134">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="2a03e-135">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="2a03e-135">Trace and Debug Settings Schema</span></span>](index.md)
