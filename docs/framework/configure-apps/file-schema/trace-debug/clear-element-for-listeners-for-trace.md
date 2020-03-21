---
title: <clear>Elemento <listeners> para for<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153547"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="d03f6-102">\<desactive> \<Element para \<los agentes de escucha> para el seguimiento></span><span class="sxs-lookup"><span data-stu-id="d03f6-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="d03f6-103">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d03f6-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="d03f6-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d03f6-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d03f6-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d03f6-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="d03f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<rastreo>**](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="d03f6-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="d03f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="d03f6-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="d03f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="d03f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d03f6-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d03f6-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d03f6-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d03f6-110">Attributes and Elements</span></span>  
 <span data-ttu-id="d03f6-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d03f6-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d03f6-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="d03f6-112">Attributes</span></span>  
 <span data-ttu-id="d03f6-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d03f6-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="d03f6-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d03f6-114">Child Elements</span></span>  
 <span data-ttu-id="d03f6-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d03f6-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d03f6-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d03f6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="d03f6-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="d03f6-117">Element</span></span>|<span data-ttu-id="d03f6-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="d03f6-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d03f6-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d03f6-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d03f6-120">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d03f6-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="d03f6-121">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d03f6-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d03f6-122">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="d03f6-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="d03f6-123">Los agentes de escucha dirigen la salida de seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="d03f6-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d03f6-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d03f6-124">Remarks</span></span>  
 <span data-ttu-id="d03f6-125">El `<clear>` elemento quita todos los `Listeners` agentes de escucha de la colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d03f6-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="d03f6-126">Puede usar `<clear>` el elemento `<add>` antes de usar el elemento para estar seguro de que no hay otros agentes de escucha activos en la colección.</span><span class="sxs-lookup"><span data-stu-id="d03f6-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="d03f6-127">Puede borrar `Listeners` la colección mediante <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> programación <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> llamando`System.Diagnostics.Trace.Listeners.Clear()`al método de la propiedad ( ).</span><span class="sxs-lookup"><span data-stu-id="d03f6-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="d03f6-128">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d03f6-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d03f6-129">El `<clear>` elemento quita <xref:System.Diagnostics.DefaultTraceListener> el `Listeners` de la colección, <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>modificando el comportamiento de los métodos , , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>. <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="d03f6-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="d03f6-130">Llamar `Assert` a `Fail` un método o o normalmente da como resultado la visualización de un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="d03f6-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="d03f6-131">Sin embargo, el cuadro de <xref:System.Diagnostics.DefaultTraceListener> mensaje no `Listeners` se muestra si no está en la colección.</span><span class="sxs-lookup"><span data-stu-id="d03f6-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d03f6-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d03f6-132">Example</span></span>  
 <span data-ttu-id="d03f6-133">En el ejemplo siguiente `<clear>` se muestra `<add>` cómo utilizar el `console` elemento `Listeners` antes de usar el elemento para agregar el agente de escucha a la colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d03f6-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d03f6-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d03f6-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="d03f6-135">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="d03f6-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d03f6-136">\<eliminar></span><span class="sxs-lookup"><span data-stu-id="d03f6-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="d03f6-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d03f6-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
