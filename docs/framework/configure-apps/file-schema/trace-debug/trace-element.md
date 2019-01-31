---
title: <trace> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
ms.openlocfilehash: d930e1fe9a9a4012e363bbbffe83e1ea7cc1c595
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257803"
---
# <a name="trace-element"></a><span data-ttu-id="758af-102">\<seguimiento > elemento</span><span class="sxs-lookup"><span data-stu-id="758af-102">\<trace> Element</span></span>
<span data-ttu-id="758af-103">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="758af-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="758af-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="758af-104">\<configuration></span></span>  
<span data-ttu-id="758af-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="758af-105">\<system.diagnostics></span></span>  
<span data-ttu-id="758af-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="758af-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758af-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="758af-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="758af-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="758af-108">Attributes and Elements</span></span>  
 <span data-ttu-id="758af-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="758af-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="758af-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="758af-110">Attributes</span></span>  
  
|<span data-ttu-id="758af-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="758af-111">Attribute</span></span>|<span data-ttu-id="758af-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="758af-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="758af-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="758af-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="758af-114">Especifica si los agentes de escucha de seguimiento automáticamente de vaciar el búfer de salida después de cada operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="758af-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="758af-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="758af-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="758af-116">Especifica el número de espacios para la sangría.</span><span class="sxs-lookup"><span data-stu-id="758af-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="758af-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="758af-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="758af-118">Indica si se debe utilizar el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="758af-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="758af-119">Atributo autoflush</span><span class="sxs-lookup"><span data-stu-id="758af-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="758af-120">Valor</span><span class="sxs-lookup"><span data-stu-id="758af-120">Value</span></span>|<span data-ttu-id="758af-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="758af-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="758af-122">No realiza automáticamente el vaciado de búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="758af-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="758af-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="758af-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="758af-124">Automáticamente se vacía el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="758af-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="758af-125">Atributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="758af-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="758af-126">Valor</span><span class="sxs-lookup"><span data-stu-id="758af-126">Value</span></span>|<span data-ttu-id="758af-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="758af-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="758af-128">No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; en caso contrario, utiliza el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="758af-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="758af-129">Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="758af-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="758af-130">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="758af-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="758af-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="758af-131">Child Elements</span></span>  
  
|<span data-ttu-id="758af-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="758af-132">Element</span></span>|<span data-ttu-id="758af-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="758af-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="758af-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="758af-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="758af-135">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="758af-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="758af-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="758af-136">Parent Elements</span></span>  
  
|<span data-ttu-id="758af-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="758af-137">Element</span></span>|<span data-ttu-id="758af-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="758af-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="758af-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="758af-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="758af-140">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="758af-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="758af-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="758af-141">Example</span></span>  
 <span data-ttu-id="758af-142">El ejemplo siguiente muestra cómo usar el `<trace>` elemento para agregar el agente de escucha `MyListener` a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="758af-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="758af-143">`MyListener` crea un archivo que se denomina `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="758af-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="758af-144">El `useGlobalLock` atributo está establecido en `false`, lo que hace que el bloqueo global no que se utilizará si el agente de escucha de seguimiento es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="758af-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="758af-145">El `autoflush` atributo está establecido en `true`, lo que hace que el agente de escucha de seguimiento escribir en el archivo independientemente de si el <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="758af-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="758af-146">El `indentsize` atributo está establecido en 0 (cero), lo que hace que el agente de escucha aplicar sangría a cero espacios cuando el <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="758af-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace useGlobalLock="false" autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="758af-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="758af-147">See also</span></span>
- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="758af-148">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="758af-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
