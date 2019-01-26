---
title: '&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;sharedListeners&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add/filter
helpviewer_keywords:
- filter element for <add> for <sharedListeners>
- initializeData attribute
- <filter> element for <add> for <sharedListeners>
- filters, trace listeners
- trace listeners, filters
ms.assetid: 7d4e7faa-2e4e-4379-ac76-f6cd7f2f8fac
ms.openlocfilehash: a811d2ae8112bb1ab9386510fc8435d00f454f85
ms.sourcegitcommit: b351b0781a035616c90c68ccae6dd60aae66a953
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/26/2019
ms.locfileid: "55083800"
---
# <a name="ltfiltergt-element-for-ltaddgt-for-ltsharedlistenersgt"></a><span data-ttu-id="84b5e-102">&lt;filtro&gt; (elemento) para &lt;agregar&gt; para &lt;sharedListeners&gt;</span><span class="sxs-lookup"><span data-stu-id="84b5e-102">&lt;filter&gt; Element for &lt;add&gt; for &lt;sharedListeners&gt;</span></span>
<span data-ttu-id="84b5e-103">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="84b5e-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="84b5e-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="84b5e-104">\<configuration></span></span>  
<span data-ttu-id="84b5e-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="84b5e-105">\<system.diagnostics></span></span>  
<span data-ttu-id="84b5e-106">\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="84b5e-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="84b5e-107">\<add></span><span class="sxs-lookup"><span data-stu-id="84b5e-107">\<add></span></span>  
<span data-ttu-id="84b5e-108">\<filter></span><span class="sxs-lookup"><span data-stu-id="84b5e-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b5e-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84b5e-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84b5e-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="84b5e-110">Attributes and Elements</span></span>  
 <span data-ttu-id="84b5e-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="84b5e-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84b5e-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="84b5e-112">Attributes</span></span>  
  
|<span data-ttu-id="84b5e-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="84b5e-113">Attribute</span></span>|<span data-ttu-id="84b5e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="84b5e-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="84b5e-115">**type**</span><span class="sxs-lookup"><span data-stu-id="84b5e-115">**type**</span></span>|<span data-ttu-id="84b5e-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="84b5e-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="84b5e-117">Especifica el tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="84b5e-117">Specifies the type of the filter.</span></span> <span data-ttu-id="84b5e-118">Puede usar solo el nombre completo del tipo (en el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o bien puede usar el nombre de tipo completo, incluida la información de ensamblado (con el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad).</span><span class="sxs-lookup"><span data-stu-id="84b5e-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="84b5e-119">Para obtener información sobre la creación de un nombre de tipo completo, vea [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="84b5e-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="84b5e-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="84b5e-120">**initializeData**</span></span>|<span data-ttu-id="84b5e-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="84b5e-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="84b5e-122">La cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="84b5e-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="84b5e-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="84b5e-123">Child Elements</span></span>  
 <span data-ttu-id="84b5e-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="84b5e-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="84b5e-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="84b5e-125">Parent Elements</span></span>  
  
|<span data-ttu-id="84b5e-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="84b5e-126">Element</span></span>|<span data-ttu-id="84b5e-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="84b5e-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="84b5e-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84b5e-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="84b5e-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="84b5e-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="84b5e-130">Una colección de agentes de escucha que se puede hacer referencia a cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="84b5e-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="84b5e-131">Agrega un agente de escucha para el **sharedListeners** colección.</span><span class="sxs-lookup"><span data-stu-id="84b5e-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84b5e-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="84b5e-132">Remarks</span></span>  
 <span data-ttu-id="84b5e-133">Si un agente de escucha se define en un `<add>` elemento de la `<sharedListeners>` elemento, el filtro para ese agente de escucha debe definirse en un `<filter>` elemento que es un elemento secundario de la `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="84b5e-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="84b5e-134">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="84b5e-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84b5e-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84b5e-135">Example</span></span>  
 <span data-ttu-id="84b5e-136">El ejemplo siguiente muestra cómo usar el `<filter>` elemento para agregar un filtro a la escucha de seguimiento `console` en el `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="84b5e-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="myTraceSource" >  
        <listeners>  
          <add name="console" />  
          <remove name="Default" />  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="console"   
        type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"   
          initializeData="Error" />  
      </add>  
    </sharedListeners>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="84b5e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="84b5e-137">See also</span></span>
- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="84b5e-138">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="84b5e-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
