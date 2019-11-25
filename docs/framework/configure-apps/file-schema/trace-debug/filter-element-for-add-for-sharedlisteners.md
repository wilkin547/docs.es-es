---
title: <filter> elemento de <add> para <sharedListeners>
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
ms.openlocfilehash: e04ecd773bd6aa7791858711edbd72128dc391ea
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088880"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="b0f83-102">\<filtro de > elemento para \<agregar > para \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="b0f83-102">\<filter> Element for \<add> for \<sharedListeners></span></span>
<span data-ttu-id="b0f83-103">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="b0f83-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

<span data-ttu-id="b0f83-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0f83-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b0f83-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="b0f83-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="b0f83-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<sharedListeners**](sharedlisteners-element.md) ></span><span class="sxs-lookup"><span data-stu-id="b0f83-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="b0f83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agregar >** ](add-element-for-sharedlisteners.md)</span><span class="sxs-lookup"><span data-stu-id="b0f83-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)</span></span>\
<span data-ttu-id="b0f83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **&nbsp;&nbsp;\<** ></span><span class="sxs-lookup"><span data-stu-id="b0f83-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b0f83-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0f83-109">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"   
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0f83-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0f83-110">Attributes and Elements</span></span>  
 <span data-ttu-id="b0f83-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0f83-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0f83-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0f83-112">Attributes</span></span>  
  
|<span data-ttu-id="b0f83-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0f83-113">Attribute</span></span>|<span data-ttu-id="b0f83-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f83-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b0f83-115">**type**</span><span class="sxs-lookup"><span data-stu-id="b0f83-115">**type**</span></span>|<span data-ttu-id="b0f83-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b0f83-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b0f83-117">Especifica el tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="b0f83-117">Specifies the type of the filter.</span></span> <span data-ttu-id="b0f83-118">Solo se puede usar el nombre completo del tipo (en el formato de la propiedad <xref:System.Type.FullName%2A?displayProperty=nameWithType>), o bien se puede usar el nombre de tipo completo, incluida la información de ensamblado (en el formato de la propiedad <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType>).</span><span class="sxs-lookup"><span data-stu-id="b0f83-118">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="b0f83-119">Para obtener información sobre cómo crear un nombre de tipo completo, vea [especificar nombres de tipos completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="b0f83-119">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="b0f83-120">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="b0f83-120">**initializeData**</span></span>|<span data-ttu-id="b0f83-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="b0f83-121">Optional attribute.</span></span><br /><br /> <span data-ttu-id="b0f83-122">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="b0f83-122">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0f83-123">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0f83-123">Child Elements</span></span>  
 <span data-ttu-id="b0f83-124">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0f83-124">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0f83-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0f83-125">Parent Elements</span></span>  
  
|<span data-ttu-id="b0f83-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0f83-126">Element</span></span>|<span data-ttu-id="b0f83-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0f83-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0f83-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0f83-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b0f83-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0f83-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="b0f83-130">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0f83-130">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="b0f83-131">Agrega un agente de escucha a la colección **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="b0f83-131">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0f83-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0f83-132">Remarks</span></span>  
 <span data-ttu-id="b0f83-133">Si se define un agente de escucha en un elemento `<add>` del elemento `<sharedListeners>`, el filtro para ese agente de escucha debe definirse en un elemento `<filter>` que sea un elemento secundario del elemento `<add>`.</span><span class="sxs-lookup"><span data-stu-id="b0f83-133">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="b0f83-134">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0f83-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0f83-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0f83-135">Example</span></span>  
 <span data-ttu-id="b0f83-136">En el ejemplo siguiente se muestra cómo utilizar el elemento `<filter>` para agregar un filtro a la `console` del agente de escucha de seguimiento de la colección de `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="b0f83-136">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0f83-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0f83-137">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b0f83-138">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="b0f83-138">Trace and Debug Settings Schema</span></span>](index.md)
