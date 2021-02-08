---
description: 'Más información sobre: <filter> elemento para <add> para <listeners><source>'
title: <filter>(Elemento <add> ) para para <listeners><source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#filter
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add/filter
helpviewer_keywords:
- initializeData attribute
- <filter> element for <add> for <listeners> for <source>
- filter element for <add> for <listeners> for <source>
ms.assetid: 15808b80-4579-4c25-b385-178cfdf154ba
ms.openlocfilehash: 65233aa2d9ea000d1d27d0241c734bee7097b7ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782265"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="83175-103">\<filter>(Elemento \<add> ) para para \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="83175-103">\<filter> Element for \<add> for \<listeners> for \<source></span></span>

<span data-ttu-id="83175-104">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83175-104">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="83175-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83175-105">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83175-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83175-106">Attributes and Elements</span></span>  

 <span data-ttu-id="83175-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83175-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83175-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="83175-108">Attributes</span></span>  
  
|<span data-ttu-id="83175-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="83175-109">Attribute</span></span>|<span data-ttu-id="83175-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="83175-110">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="83175-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="83175-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="83175-112">Especifica el tipo del filtro, que debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="83175-112">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="83175-113">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad del tipo <xref:System.Type.FullName%2A> , o puede usar el nombre de tipo completo, incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="83175-113">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="83175-114">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="83175-114">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="83175-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="83175-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83175-116">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="83175-116">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83175-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83175-117">Child Elements</span></span>  

 <span data-ttu-id="83175-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="83175-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="83175-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83175-119">Parent Elements</span></span>  
  
|<span data-ttu-id="83175-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="83175-120">Element</span></span>|<span data-ttu-id="83175-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="83175-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83175-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83175-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="83175-123">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83175-123">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="83175-124">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83175-124">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="83175-125">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83175-125">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="83175-126">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="83175-126">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="83175-127">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="83175-127">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="83175-128">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83175-128">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83175-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="83175-129">Remarks</span></span>  

 <span data-ttu-id="83175-130">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de origen de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="83175-130">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="83175-131">Si el agente de escucha se define en [\<sharedListeners>](sharedlisteners-element.md) , el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="83175-131">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="83175-132">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83175-132">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83175-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83175-133">Example</span></span>  

 <span data-ttu-id="83175-134">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente `console` de escucha de la `Listeners` colección para el origen de seguimiento `myTraceSource` , especificando el nivel de evento de filtro como `Error` .</span><span class="sxs-lookup"><span data-stu-id="83175-134">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83175-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="83175-135">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="83175-136">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="83175-136">Trace and Debug Settings Schema</span></span>](index.md)
