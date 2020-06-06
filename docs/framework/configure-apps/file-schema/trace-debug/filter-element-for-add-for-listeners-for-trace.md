---
title: <filter>(Elemento <add> ) para para <listeners><trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- filter element for <add> for <listeners> for <trace>
- <filter> element for <add> for <listeners> for <trace>
ms.assetid: eb9c18f5-dfa8-47c5-b91b-e4b93e76e1cc
ms.openlocfilehash: b6c2c2bf7fe953a75f9d8129039ef33b4d8a3f56
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153471"
---
# <a name="filter-element-for-add-for-listeners-for-trace"></a><span data-ttu-id="17871-102">\<filter>(Elemento \<add> ) para para \<listeners>\<trace></span><span class="sxs-lookup"><span data-stu-id="17871-102">\<filter> Element for \<add> for \<listeners> for \<trace></span></span>
<span data-ttu-id="17871-103">Agrega un filtro a un agente de escucha de la `Listeners` colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="17871-103">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="17871-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17871-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="17871-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="17871-105">Attributes and Elements</span></span>  
 <span data-ttu-id="17871-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="17871-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="17871-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="17871-107">Attributes</span></span>  
  
|<span data-ttu-id="17871-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="17871-108">Attribute</span></span>|<span data-ttu-id="17871-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="17871-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="17871-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="17871-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="17871-111">Especifica el tipo del filtro, que debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="17871-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="17871-112">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad del tipo <xref:System.Type.FullName%2A> , o puede usar el nombre de tipo completo, incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="17871-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="17871-113">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="17871-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="17871-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="17871-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="17871-115">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="17871-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="17871-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="17871-116">Child Elements</span></span>  
 <span data-ttu-id="17871-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="17871-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="17871-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="17871-118">Parent Elements</span></span>  
  
|<span data-ttu-id="17871-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="17871-119">Element</span></span>|<span data-ttu-id="17871-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="17871-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="17871-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="17871-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="17871-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="17871-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="17871-123">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="17871-123">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="17871-124">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="17871-124">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="17871-125">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="17871-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="17871-126">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="17871-126">Adds a listener to the `Listeners` collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="17871-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="17871-127">Remarks</span></span>  
 <span data-ttu-id="17871-128">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="17871-128">The `<filter>` element must be contained in an `<add>` element for a trace listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="17871-129">Si el agente de escucha se define en [\<sharedListeners>](sharedlisteners-element.md) , el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="17871-129">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="17871-130">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="17871-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="17871-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="17871-131">Example</span></span>  
 <span data-ttu-id="17871-132">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente `console` de escucha de la `Listeners` colección para el seguimiento, especificando el nivel de evento de filtro como `Error` .</span><span class="sxs-lookup"><span data-stu-id="17871-132">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for trace, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="17871-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="17871-133">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="17871-134">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="17871-134">Trace and Debug Settings Schema</span></span>](index.md)
