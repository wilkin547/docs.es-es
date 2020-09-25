---
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
ms.openlocfilehash: 2b83fd10da506202427aaeee454411822ff1ae5b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201686"
---
# <a name="filter-element-for-add-for-listeners-for-source"></a><span data-ttu-id="6021a-102">\<filter>(Elemento \<add> ) para para \<listeners>\<source></span><span class="sxs-lookup"><span data-stu-id="6021a-102">\<filter> Element for \<add> for \<listeners> for \<source></span></span>

<span data-ttu-id="6021a-103">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6021a-103">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-listeners-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="6021a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6021a-104">Syntax</span></span>  
  
```xml  
<filter
  type="traceFilterClassName"
  initializeData="data" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6021a-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6021a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6021a-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6021a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6021a-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6021a-107">Attributes</span></span>  
  
|<span data-ttu-id="6021a-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="6021a-108">Attribute</span></span>|<span data-ttu-id="6021a-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6021a-109">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="6021a-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6021a-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="6021a-111">Especifica el tipo del filtro, que debe heredar de la <xref:System.Diagnostics.TraceFilter> clase.</span><span class="sxs-lookup"><span data-stu-id="6021a-111">Specifies the type of the filter, which should inherit from the <xref:System.Diagnostics.TraceFilter> class.</span></span> <span data-ttu-id="6021a-112">Puede usar el nombre completo del espacio de nombres del tipo, que corresponde a la propiedad del tipo <xref:System.Type.FullName%2A> , o puede usar el nombre de tipo completo, incluida la información de ensamblado, que corresponde a la <xref:System.Type.AssemblyQualifiedName%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="6021a-112">You can use the namespace-qualified name of the type, which corresponds to the type's <xref:System.Type.FullName%2A> property, or you can use the fully qualified type name including the assembly information, which corresponds to the <xref:System.Type.AssemblyQualifiedName%2A> property.</span></span> <span data-ttu-id="6021a-113">Para obtener información sobre los nombres de tipo completos, vea [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="6021a-113">For information about fully qualified type names, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="6021a-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="6021a-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="6021a-115">Cadena pasada al constructor de la clase de filtro especificada.</span><span class="sxs-lookup"><span data-stu-id="6021a-115">The string passed to the constructor for the specified filter class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6021a-116">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6021a-116">Child Elements</span></span>  

 <span data-ttu-id="6021a-117">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6021a-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6021a-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6021a-118">Parent Elements</span></span>  
  
|<span data-ttu-id="6021a-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="6021a-119">Element</span></span>|<span data-ttu-id="6021a-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="6021a-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6021a-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6021a-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6021a-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6021a-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="6021a-123">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6021a-123">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="6021a-124">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6021a-124">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="6021a-125">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="6021a-125">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="6021a-126">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="6021a-126">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`add`|<span data-ttu-id="6021a-127">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6021a-127">Adds a listener to the `Listeners` collection for a trace source.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6021a-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6021a-128">Remarks</span></span>  

 <span data-ttu-id="6021a-129">El `<filter>` elemento debe estar contenido en un `<add>` elemento para un agente de escucha de origen de seguimiento que especifique el tipo del agente de escucha, no solo el nombre de un agente de escucha definido en [\<sharedListeners>](sharedlisteners-element.md) .</span><span class="sxs-lookup"><span data-stu-id="6021a-129">The `<filter>` element must be contained in an `<add>` element for a trace source listener that specifies the type of the listener, not just the name of a listener defined in a [\<sharedListeners>](sharedlisteners-element.md).</span></span> <span data-ttu-id="6021a-130">Si el agente de escucha se define en [\<sharedListeners>](sharedlisteners-element.md) , el filtro para ese agente de escucha debe definirse en ese elemento.</span><span class="sxs-lookup"><span data-stu-id="6021a-130">If the listener is defined in a [\<sharedListeners>](sharedlisteners-element.md), the filter for that listener must be defined in that element.</span></span>  
  
 <span data-ttu-id="6021a-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6021a-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6021a-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6021a-132">Example</span></span>  

 <span data-ttu-id="6021a-133">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente `console` de escucha de la `Listeners` colección para el origen de seguimiento `myTraceSource` , especificando el nivel de evento de filtro como `Error` .</span><span class="sxs-lookup"><span data-stu-id="6021a-133">The following example shows how to use the `<filter>` element to add a filter to the listener `console` in the `Listeners` collection for the trace source `myTraceSource`, specifying the filter event level as `Error`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6021a-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6021a-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceListener.Filter%2A?displayProperty=nameWithType>
- <xref:System.Diagnostics.TraceFilter>
- [<span data-ttu-id="6021a-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="6021a-135">Trace and Debug Settings Schema</span></span>](index.md)
