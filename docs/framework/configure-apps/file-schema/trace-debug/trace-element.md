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
ms.openlocfilehash: 617b42a0be2be272a78b33be997cce632d1c6dcb
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198930"
---
# <a name="trace-element"></a><span data-ttu-id="4fd77-102">\<trace> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="4fd77-102">\<trace> Element</span></span>

<span data-ttu-id="4fd77-103">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4fd77-103">Contains listeners that collect, store, and route tracing messages.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<trace>**  
  
## <a name="syntax"></a><span data-ttu-id="4fd77-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fd77-104">Syntax</span></span>  
  
```xml  
<trace autoflush="true|false"
       indentsize="indent value"  
       useGlobalLock="true| false"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4fd77-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4fd77-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4fd77-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4fd77-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4fd77-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4fd77-107">Attributes</span></span>  
  
|<span data-ttu-id="4fd77-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="4fd77-108">Attribute</span></span>|<span data-ttu-id="4fd77-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fd77-109">Description</span></span>|  
|---------------|-----------------|  
|`autoflush`|<span data-ttu-id="4fd77-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4fd77-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4fd77-111">Especifica si los agentes de escucha de seguimiento vacían automáticamente el búfer de salida después de cada operación de escritura.</span><span class="sxs-lookup"><span data-stu-id="4fd77-111">Specifies whether the trace listeners automatically flush the output buffer after every write operation.</span></span>|  
|`indentsize`|<span data-ttu-id="4fd77-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4fd77-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4fd77-113">Especifica el número de espacios a los que se va a aplicar sangría.</span><span class="sxs-lookup"><span data-stu-id="4fd77-113">Specifies the number of spaces to indent.</span></span>|  
|`useGlobalLock`|<span data-ttu-id="4fd77-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="4fd77-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="4fd77-115">Indica si se debe usar el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="4fd77-115">Indicates whether the global lock should be used.</span></span>|  
  
## <a name="autoflush-attribute"></a><span data-ttu-id="4fd77-116">AutoFlush (atributo)</span><span class="sxs-lookup"><span data-stu-id="4fd77-116">autoflush Attribute</span></span>  
  
|<span data-ttu-id="4fd77-117">Value</span><span class="sxs-lookup"><span data-stu-id="4fd77-117">Value</span></span>|<span data-ttu-id="4fd77-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fd77-118">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4fd77-119">No vacía automáticamente el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="4fd77-119">Does not automatically flush the output buffer.</span></span> <span data-ttu-id="4fd77-120">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4fd77-120">This is the default.</span></span>|  
|`true`|<span data-ttu-id="4fd77-121">Vacía automáticamente el búfer de salida.</span><span class="sxs-lookup"><span data-stu-id="4fd77-121">Automatically flushes the output buffer.</span></span>|  
  
## <a name="usegloballock-attribute"></a><span data-ttu-id="4fd77-122">Atributo useGlobalLock</span><span class="sxs-lookup"><span data-stu-id="4fd77-122">useGlobalLock Attribute</span></span>  
  
|<span data-ttu-id="4fd77-123">Value</span><span class="sxs-lookup"><span data-stu-id="4fd77-123">Value</span></span>|<span data-ttu-id="4fd77-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fd77-124">Description</span></span>|  
|-----------|-----------------|  
|`false`|<span data-ttu-id="4fd77-125">No utiliza el bloqueo global si el agente de escucha es seguro para subprocesos; de lo contrario, utiliza el bloqueo global.</span><span class="sxs-lookup"><span data-stu-id="4fd77-125">Does not use the global lock if the listener is thread safe; otherwise, uses the global lock.</span></span>|  
|`true`|<span data-ttu-id="4fd77-126">Utiliza el bloqueo global independientemente de si el agente de escucha es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4fd77-126">Uses the global lock regardless of whether the listener is thread safe.</span></span> <span data-ttu-id="4fd77-127">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="4fd77-127">This is the default.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4fd77-128">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4fd77-128">Child Elements</span></span>  
  
|<span data-ttu-id="4fd77-129">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fd77-129">Element</span></span>|<span data-ttu-id="4fd77-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fd77-130">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-trace.md)|<span data-ttu-id="4fd77-131">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4fd77-131">Specifies a listener that collects, stores, and routes messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4fd77-132">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4fd77-132">Parent Elements</span></span>  
  
|<span data-ttu-id="4fd77-133">Elemento</span><span class="sxs-lookup"><span data-stu-id="4fd77-133">Element</span></span>|<span data-ttu-id="4fd77-134">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fd77-134">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4fd77-135">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4fd77-135">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4fd77-136">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4fd77-136">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="4fd77-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4fd77-137">Example</span></span>  

 <span data-ttu-id="4fd77-138">En el ejemplo siguiente se muestra cómo usar el `<trace>` elemento para agregar el agente de escucha `MyListener` a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="4fd77-138">The following example shows how to use the `<trace>` element to add the listener `MyListener` to the `Listeners` collection.</span></span> <span data-ttu-id="4fd77-139">`MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="4fd77-139">`MyListener` creates a file that is named `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="4fd77-140">El `useGlobalLock` atributo se establece en `false` , lo que hace que no se use el bloqueo global si el agente de escucha de seguimiento es seguro para subprocesos.</span><span class="sxs-lookup"><span data-stu-id="4fd77-140">The `useGlobalLock` attribute is set to `false`, which causes the global lock not to be used if the trace listener is thread safe.</span></span> <span data-ttu-id="4fd77-141">El `autoflush` atributo se establece en `true` , que hace que el agente de escucha de seguimiento escriba en el archivo independientemente de si <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="4fd77-141">The `autoflush` attribute is set to `true`, which causes the trace listener to write to the file regardless of whether the <xref:System.Diagnostics.Trace.Flush%2A?displayProperty=nameWithType> method is called.</span></span> <span data-ttu-id="4fd77-142">El `indentsize` atributo se establece en 0 (cero), lo que hace que el agente de escucha Aplique sangría a cero espacios cuando <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> se llama al método.</span><span class="sxs-lookup"><span data-stu-id="4fd77-142">The `indentsize` attribute is set to 0 (zero), which causes the listener to indent zero spaces when the <xref:System.Diagnostics.Trace.Indent%2A?displayProperty=nameWithType> method is called.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4fd77-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4fd77-143">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="4fd77-144">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="4fd77-144">Trace and Debug Settings Schema</span></span>](index.md)
