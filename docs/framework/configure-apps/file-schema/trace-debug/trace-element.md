---
title: '&lt;seguimiento&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace
- http://schemas.microsoft.com/.NetConfiguration/v2.0#trace
helpviewer_keywords:
- <trace> element
- listeners
- trace element
- trace listener, <trace> element
ms.assetid: 7931c942-63c1-47c3-a045-9d9de3cacdbf
caps.latest.revision: "13"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 157adb6c7317aa047976cdb9e30711d20c9e543b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="lttracegt-element"></a><span data-ttu-id="1d55a-102">&lt;seguimiento&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="1d55a-102">&lt;trace&gt; Element</span></span>
<span data-ttu-id="1d55a-103">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1d55a-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
 <span data-ttu-id="1d55a-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1d55a-104">\<configuration></span></span>  
<span data-ttu-id="1d55a-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="1d55a-105">\<system.diagnostics></span></span>  
<span data-ttu-id="1d55a-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="1d55a-106">\<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d55a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d55a-107">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"   
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1d55a-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1d55a-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1d55a-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1d55a-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1d55a-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1d55a-110">Attributes</span></span>  
  
|<span data-ttu-id="1d55a-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1d55a-111">Attribute</span></span>|<span data-ttu-id="1d55a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d55a-112">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="1d55a-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1d55a-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1d55a-114">Especifica si los agentes de escucha de seguimiento vacían automáticamente o el búfer de salida después de cada operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="1d55a-114">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="1d55a-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1d55a-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1d55a-116">Especifica el número de espacios para la sangría.</span><span class="sxs-lookup"><span data-stu-id="1d55a-116">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="1d55a-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="1d55a-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="1d55a-118">Indica si se debe utilizar el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="1d55a-118">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="1d55a-119">Atributo autoflush</span><span class="sxs-lookup"><span data-stu-id="1d55a-119">autoflush Attribute</span></span>  
  
|<span data-ttu-id="1d55a-120">Valor</span><span class="sxs-lookup"><span data-stu-id="1d55a-120">Value</span></span>|<span data-ttu-id="1d55a-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d55a-121">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1d55a-122">No se vacíe automáticamente el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="1d55a-122">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="1d55a-123">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1d55a-123">This is the default.</span></span>|  
|`true`|<span data-ttu-id="1d55a-124">Automáticamente se vacía el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="1d55a-124">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="1d55a-125">Atributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="1d55a-125">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="1d55a-126">Valor</span><span class="sxs-lookup"><span data-stu-id="1d55a-126">Value</span></span>|<span data-ttu-id="1d55a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d55a-127">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="1d55a-128">No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; en caso contrario, utiliza el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="1d55a-128">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="1d55a-129">Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="1d55a-129">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="1d55a-130">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="1d55a-130">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1d55a-131">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1d55a-131">Child Elements</span></span>  
  
|<span data-ttu-id="1d55a-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d55a-132">Element</span></span>|<span data-ttu-id="1d55a-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d55a-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1d55a-134">\<listeners></span><span class="sxs-lookup"><span data-stu-id="1d55a-134">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-trace.md)|<span data-ttu-id="1d55a-135">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="1d55a-135">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1d55a-136">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1d55a-136">Parent Elements</span></span>  
  
|<span data-ttu-id="1d55a-137">Elemento</span><span class="sxs-lookup"><span data-stu-id="1d55a-137">Element</span></span>|<span data-ttu-id="1d55a-138">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d55a-138">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1d55a-139">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1d55a-139">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="1d55a-140">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1d55a-140">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1d55a-141">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1d55a-141">Example</span></span>  
 <span data-ttu-id="1d55a-142">En el ejemplo siguiente se muestra cómo utilizar el `<trace>` elemento que se va a agregar el agente de escucha `MyListener` a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="1d55a-142">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="1d55a-143">`MyListener`crea un archivo que se denomina `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="1d55a-143">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="1d55a-144">El `useGlobalLock` atributo está establecido en `false`, lo que hace que el bloqueo global no que se utilizará si el agente de escucha de seguimiento es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="1d55a-144">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="1d55a-145">El `autoflush` atributo está establecido en `true`, lo que hace que el agente de escucha de seguimiento escribir en el archivo independientemente de si el <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="1d55a-145">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="1d55a-146">El `indentsize` atributo está establecido en 0 (cero), lo que hace que el agente de escucha sangre cero espacios cuando el <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="1d55a-146">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="1d55a-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d55a-147">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="1d55a-148">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="1d55a-148">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
