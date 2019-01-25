---
title: '&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 2e0970fe197ecf6e0fbcf94f410364cb59d267e6
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54732614"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="5c188-102">&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;</span><span class="sxs-lookup"><span data-stu-id="5c188-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="5c188-103">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5c188-103">Clears the `Listeners` collection for trace.</span></span>  
  
 <span data-ttu-id="5c188-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="5c188-104">\<configuration></span></span>  
<span data-ttu-id="5c188-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="5c188-105">\<system.diagnostics></span></span>  
<span data-ttu-id="5c188-106">\<trace></span><span class="sxs-lookup"><span data-stu-id="5c188-106">\<trace></span></span>  
<span data-ttu-id="5c188-107">\<listeners></span><span class="sxs-lookup"><span data-stu-id="5c188-107">\<listeners></span></span>  
<span data-ttu-id="5c188-108">\<clear></span><span class="sxs-lookup"><span data-stu-id="5c188-108">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c188-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5c188-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5c188-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="5c188-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5c188-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="5c188-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5c188-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="5c188-112">Attributes</span></span>  
 <span data-ttu-id="5c188-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5c188-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5c188-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="5c188-114">Child Elements</span></span>  
 <span data-ttu-id="5c188-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="5c188-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5c188-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="5c188-116">Parent Elements</span></span>  
  
|<span data-ttu-id="5c188-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="5c188-117">Element</span></span>|<span data-ttu-id="5c188-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="5c188-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="5c188-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5c188-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="5c188-120">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5c188-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="5c188-121">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5c188-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="5c188-122">Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="5c188-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="5c188-123">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="5c188-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5c188-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5c188-124">Remarks</span></span>  
 <span data-ttu-id="5c188-125">El `<clear>` elemento quita todos los agentes de escucha desde el `Listeners` colección de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5c188-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="5c188-126">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento que esté seguro de que no hay ningún otros agentes de escucha activos en la colección.</span><span class="sxs-lookup"><span data-stu-id="5c188-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="5c188-127">Puede borrar el `Listeners` colección mediante programación mediante una llamada a la <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> método en el <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> propiedad (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="5c188-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="5c188-128">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5c188-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c188-129">El `<clear>` elemento quita el <xref:System.Diagnostics.DefaultTraceListener> desde el `Listeners` colección, alterar el comportamiento de la <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="5c188-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="5c188-130">Una llamada a un `Assert` o `Fail` método normalmente da como resultado de la presentación de un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="5c188-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="5c188-131">Sin embargo, no se muestra el cuadro de mensaje si el <xref:System.Diagnostics.DefaultTraceListener> no está en el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="5c188-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5c188-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5c188-132">Example</span></span>  
 <span data-ttu-id="5c188-133">En el ejemplo siguiente se muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elemento para agregar el agente de escucha `console` a la `Listeners` recopilación para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="5c188-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="5c188-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="5c188-134">See also</span></span>
- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="5c188-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="5c188-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="5c188-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="5c188-136">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="5c188-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="5c188-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
