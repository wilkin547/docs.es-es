---
title: '&lt;sharedListeners&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
author: mcleblanc
ms.author: markl
ms.openlocfilehash: b312ea8180c464fb9f955e7d7079cac930c8bf05
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070141"
---
# <a name="ltsharedlistenersgt-element"></a><span data-ttu-id="29fe9-102">&lt;sharedListeners&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="29fe9-102">&lt;sharedListeners&gt; Element</span></span>
<span data-ttu-id="29fe9-103">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29fe9-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="29fe9-104">Estos agentes de escucha no reciben los seguimientos de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="29fe9-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="29fe9-105">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar orígenes o seguimiento por nombre.</span><span class="sxs-lookup"><span data-stu-id="29fe9-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
 <span data-ttu-id="29fe9-106">\<configuration></span><span class="sxs-lookup"><span data-stu-id="29fe9-106">\<configuration></span></span>  
<span data-ttu-id="29fe9-107">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="29fe9-107">\<system.diagnostics></span></span>  
<span data-ttu-id="29fe9-108">\<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="29fe9-108">\<sharedListeners></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29fe9-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29fe9-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29fe9-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29fe9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="29fe9-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29fe9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29fe9-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="29fe9-112">Attributes</span></span>  
 <span data-ttu-id="29fe9-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29fe9-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29fe9-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29fe9-114">Child Elements</span></span>  
  
|<span data-ttu-id="29fe9-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="29fe9-115">Element</span></span>|<span data-ttu-id="29fe9-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="29fe9-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29fe9-117">\<add></span><span class="sxs-lookup"><span data-stu-id="29fe9-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="29fe9-118">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="29fe9-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29fe9-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29fe9-119">Parent Elements</span></span>  
  
|<span data-ttu-id="29fe9-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="29fe9-120">Element</span></span>|<span data-ttu-id="29fe9-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="29fe9-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="29fe9-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29fe9-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="29fe9-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="29fe9-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29fe9-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29fe9-124">Remarks</span></span>  
 <span data-ttu-id="29fe9-125">Agregar un agente de escucha a la colección de agentes de escucha compartidos no facilitan un agente de escucha activo.</span><span class="sxs-lookup"><span data-stu-id="29fe9-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="29fe9-126">Todavía se debe agregar a un origen de seguimiento o un seguimiento agregándolo a la `Listeners` colección para ese elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29fe9-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="29fe9-127">Las clases de agente de escucha en .NET Framework se derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="29fe9-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="29fe9-128">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29fe9-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29fe9-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29fe9-129">Example</span></span>  
 <span data-ttu-id="29fe9-130">El ejemplo siguiente muestra cómo usar el `<sharedListeners>` elemento para agregar el agente de escucha `console` a la `Listeners` colección tanto para el <xref:System.Diagnostics.TraceSource> y <xref:System.Diagnostics.Trace> clases.</span><span class="sxs-lookup"><span data-stu-id="29fe9-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="29fe9-131">El agente de escucha de seguimiento de consola escribe información de seguimiento en la consola a través de las llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="29fe9-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration></system.diagnostics>   
```  
  
## <a name="see-also"></a><span data-ttu-id="29fe9-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="29fe9-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="29fe9-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="29fe9-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="29fe9-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="29fe9-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
