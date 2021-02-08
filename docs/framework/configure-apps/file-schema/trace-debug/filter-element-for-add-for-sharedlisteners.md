---
description: 'Más información sobre: <filter> elemento para <add> para <sharedListeners>'
title: <filter> (Elemento <add> ) para <sharedListeners>
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
ms.openlocfilehash: 5d6567ff029dea5ed98054dbc524bb7ed405324c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802377"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="34296-103">\<filter> (Elemento \<add> ) para \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="34296-103">\<filter> Element for \<add> for \<sharedListeners></span></span>

<span data-ttu-id="34296-104">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="34296-104">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="34296-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34296-105">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34296-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34296-106">Attributes and Elements</span></span>  

 <span data-ttu-id="34296-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34296-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34296-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="34296-108">Attributes</span></span>  
  
|<span data-ttu-id="34296-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="34296-109">Attribute</span></span>|<span data-ttu-id="34296-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="34296-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="34296-111">**type**</span><span class="sxs-lookup"><span data-stu-id="34296-111">**type**</span></span>|<span data-ttu-id="34296-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="34296-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="34296-113">Especifica el tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="34296-113">Specifies the type of the filter.</span></span> <span data-ttu-id="34296-114">Solo se puede usar el nombre completo del tipo (en el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o bien se puede usar el nombre de tipo completo, incluida la información de ensamblado (en el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad).</span><span class="sxs-lookup"><span data-stu-id="34296-114">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="34296-115">Para obtener información sobre cómo crear un nombre de tipo completo, vea [especificar nombres de tipos completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="34296-115">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="34296-116">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="34296-116">**initializeData**</span></span>|<span data-ttu-id="34296-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="34296-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="34296-118">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="34296-118">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="34296-119">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34296-119">Child Elements</span></span>  

 <span data-ttu-id="34296-120">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="34296-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="34296-121">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34296-121">Parent Elements</span></span>  
  
|<span data-ttu-id="34296-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="34296-122">Element</span></span>|<span data-ttu-id="34296-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="34296-123">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34296-124">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34296-124">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="34296-125">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34296-125">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="34296-126">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34296-126">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="34296-127">Agrega un agente de escucha a la colección **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="34296-127">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34296-128">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34296-128">Remarks</span></span>  

 <span data-ttu-id="34296-129">Si se define un agente de escucha en un `<add>` elemento del `<sharedListeners>` elemento, el filtro para ese agente de escucha debe definirse en un `<filter>` elemento secundario del `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="34296-129">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="34296-130">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34296-130">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34296-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34296-131">Example</span></span>  

 <span data-ttu-id="34296-132">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente de escucha `console` de seguimiento de la `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="34296-132">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34296-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="34296-133">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="34296-134">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="34296-134">Trace and Debug Settings Schema</span></span>](index.md)
