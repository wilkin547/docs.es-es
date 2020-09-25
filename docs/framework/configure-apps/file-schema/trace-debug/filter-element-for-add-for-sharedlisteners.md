---
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
ms.openlocfilehash: e140148a342e31d6ade7def8849d8a7738301704
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173931"
---
# <a name="filter-element-for-add-for-sharedlisteners"></a><span data-ttu-id="665b8-102">\<filter> (Elemento \<add> ) para \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="665b8-102">\<filter> Element for \<add> for \<sharedListeners></span></span>

<span data-ttu-id="665b8-103">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="665b8-103">Adds a filter to a listener in the `sharedListeners` collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<add>**](add-element-for-sharedlisteners.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<filter>**

## <a name="syntax"></a><span data-ttu-id="665b8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="665b8-104">Syntax</span></span>  
  
```xml  
<filter type="System.Diagnostics.EventTypeFilter"
  initializeData="Warning" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="665b8-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="665b8-105">Attributes and Elements</span></span>  

 <span data-ttu-id="665b8-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="665b8-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="665b8-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="665b8-107">Attributes</span></span>  
  
|<span data-ttu-id="665b8-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="665b8-108">Attribute</span></span>|<span data-ttu-id="665b8-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="665b8-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="665b8-110">**type**</span><span class="sxs-lookup"><span data-stu-id="665b8-110">**type**</span></span>|<span data-ttu-id="665b8-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="665b8-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="665b8-112">Especifica el tipo del filtro.</span><span class="sxs-lookup"><span data-stu-id="665b8-112">Specifies the type of the filter.</span></span> <span data-ttu-id="665b8-113">Solo se puede usar el nombre completo del tipo (en el formato de la <xref:System.Type.FullName%2A?displayProperty=nameWithType> propiedad), o bien se puede usar el nombre de tipo completo, incluida la información de ensamblado (en el formato de la <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> propiedad).</span><span class="sxs-lookup"><span data-stu-id="665b8-113">You can use only the full name of the type (in the format of the <xref:System.Type.FullName%2A?displayProperty=nameWithType> property), or you can use the fully qualified type name including the assembly information (in the format of the <xref:System.Type.AssemblyQualifiedName%2A?displayProperty=nameWithType> property).</span></span> <span data-ttu-id="665b8-114">Para obtener información sobre cómo crear un nombre de tipo completo, vea [especificar nombres de tipos completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="665b8-114">For information on creating a fully qualified type name, see [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="665b8-115">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="665b8-115">**initializeData**</span></span>|<span data-ttu-id="665b8-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="665b8-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="665b8-117">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="665b8-117">The string passed to the constructor for the specified class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="665b8-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="665b8-118">Child Elements</span></span>  

 <span data-ttu-id="665b8-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="665b8-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="665b8-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="665b8-120">Parent Elements</span></span>  
  
|<span data-ttu-id="665b8-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="665b8-121">Element</span></span>|<span data-ttu-id="665b8-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="665b8-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="665b8-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="665b8-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="665b8-124">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="665b8-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="665b8-125">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="665b8-125">A collection of listeners that any source or trace element can reference.</span></span>|  
|`add`|<span data-ttu-id="665b8-126">Agrega un agente de escucha a la colección **sharedListeners** .</span><span class="sxs-lookup"><span data-stu-id="665b8-126">Adds a listener to the **sharedListeners** collection.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="665b8-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="665b8-127">Remarks</span></span>  

 <span data-ttu-id="665b8-128">Si se define un agente de escucha en un `<add>` elemento del `<sharedListeners>` elemento, el filtro para ese agente de escucha debe definirse en un `<filter>` elemento secundario del `<add>` elemento.</span><span class="sxs-lookup"><span data-stu-id="665b8-128">If a listener is defined in an `<add>` element of the `<sharedListeners>` element, the filter for that listener should be defined in a `<filter>` element that is a child of the `<add>` element.</span></span>  
  
 <span data-ttu-id="665b8-129">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="665b8-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="665b8-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="665b8-130">Example</span></span>  

 <span data-ttu-id="665b8-131">En el ejemplo siguiente se muestra cómo usar el `<filter>` elemento para agregar un filtro al agente de escucha `console` de seguimiento de la `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="665b8-131">The following example shows how to use the `<filter>` element to add a filter to the trace listener `console` in the `sharedListeners` collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="665b8-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="665b8-132">See also</span></span>

- <xref:System.Diagnostics.TraceFilter>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="665b8-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="665b8-133">Trace and Debug Settings Schema</span></span>](index.md)
