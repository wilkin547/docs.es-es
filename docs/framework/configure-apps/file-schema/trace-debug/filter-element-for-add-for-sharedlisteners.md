---
title: Elemento <filter> de <add> de <sharedListeners>
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
ms.openlocfilehash: 739acedcc83cd207a7ef4c10c220d27695dd713d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55269307"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="af593-102">\<Filtro > (elemento) para \<Agregar > para \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="af593-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="af593-103">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="af593-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  
  
 <span data-ttu-id="af593-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="af593-104">\<configuration></span></span>  
<span data-ttu-id="af593-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="af593-105">\<system.diagnostics></span></span>  
<span data-ttu-id="af593-106">\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="af593-106">\<sharedListeners> Element</span></span>  
<span data-ttu-id="af593-107">\<add></span><span class="sxs-lookup"><span data-stu-id="af593-107">\<add></span></span>  
<span data-ttu-id="af593-108">\<filter></span><span class="sxs-lookup"><span data-stu-id="af593-108">\<filter></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af593-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="af593-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="af593-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="af593-110">Attributes and Elements</span></span>  
 <span data-ttu-id="af593-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="af593-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="af593-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="af593-112">Attributes</span></span>  
  
|<span data-ttu-id="af593-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="af593-113">Attribute</span></span>|<span data-ttu-id="af593-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="af593-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="af593-115">**type**</span><span class="sxs-lookup"><span data-stu-id="af593-115">**type**</span></span>|<span data-ttu-id="af593-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="af593-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="af593-117">Especifica el tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="af593-117">Specifies the type of the filter.</span></span> <span data-ttu-id="af593-118">Puede usar solo el nombre completo del tipo (en el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o bien puede usar el nombre de tipo completo, incluida la información de ensamblado (con el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad).</span><span class="sxs-lookup"><span data-stu-id="af593-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="af593-119">Para obtener información sobre la creación de un nombre de tipo completo, vea [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="af593-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="af593-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="af593-120">**initializeData**</span></span>|<span data-ttu-id="af593-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="af593-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="af593-122">La cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="af593-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="af593-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="af593-123">Child Elements</span></span>  
 <span data-ttu-id="af593-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="af593-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="af593-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="af593-125">Parent Elements</span></span>  
  
|<span data-ttu-id="af593-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="af593-126">Element</span></span>|<span data-ttu-id="af593-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="af593-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="af593-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="af593-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="af593-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="af593-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="af593-130">Una colección de agentes de escucha que se puede hacer referencia a cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="af593-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="af593-131">Agrega un agente de escucha para el **sharedListeners** colección.</span><span class="sxs-lookup"><span data-stu-id="af593-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af593-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="af593-132">Remarks</span></span>  
 <span data-ttu-id="af593-133">Si un agente de escucha se define en un `<add>` elemento de la `<sharedListeners>` elemento, el filtro para ese agente de escucha debe definirse en un `<filter>` elemento que es un elemento secundario de la `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="af593-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="af593-134">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af593-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af593-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="af593-135">Example</span></span>  
 <span data-ttu-id="af593-136">El ejemplo siguiente muestra cómo usar el `<filter>` elemento para agregar un filtro a la escucha de seguimiento `console` en el `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="af593-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="af593-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="af593-137">See also</span></span>
- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="af593-138">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="af593-138">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
