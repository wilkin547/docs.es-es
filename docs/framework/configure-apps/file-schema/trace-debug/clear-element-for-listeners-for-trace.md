---
description: 'Más información sobre: <clear> elemento para <listeners> para <trace>'
title: <clear> (Elemento <listeners> ) para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 3c1b3816f4ccd0ceb9e9bc0fc6acfd9b6e8ade85
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725979"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="75134-103">\<clear> (Elemento \<listeners> ) para \<trace></span><span class="sxs-lookup"><span data-stu-id="75134-103">\<clear> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="75134-104">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="75134-104">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="75134-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75134-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="75134-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="75134-106">Attributes and Elements</span></span>  

 <span data-ttu-id="75134-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="75134-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="75134-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="75134-108">Attributes</span></span>  

 <span data-ttu-id="75134-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75134-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="75134-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="75134-110">Child Elements</span></span>  

 <span data-ttu-id="75134-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="75134-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="75134-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="75134-112">Parent Elements</span></span>  
  
|<span data-ttu-id="75134-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="75134-113">Element</span></span>|<span data-ttu-id="75134-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="75134-114">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="75134-115">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="75134-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="75134-116">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="75134-116">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="75134-117">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="75134-117">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="75134-118">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="75134-118">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="75134-119">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="75134-119">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75134-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="75134-120">Remarks</span></span>  

 <span data-ttu-id="75134-121">El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="75134-121">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="75134-122">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="75134-122">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="75134-123">Puede borrar la `Listeners` colección mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> método en la <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> propiedad ( `System.Diagnostics.Trace.Listeners.Clear()` ).</span><span class="sxs-lookup"><span data-stu-id="75134-123">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="75134-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="75134-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="75134-125">El `<clear>` elemento quita <xref:System.Diagnostics.DefaultTraceListener> de la `Listeners` colección, modificando el comportamiento de los <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> métodos, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="75134-125">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="75134-126">La llamada a un `Assert` `Fail` método o suele tener como resultado la presentación de un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="75134-126">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="75134-127">Sin embargo, el cuadro de mensaje no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="75134-127">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75134-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="75134-128">Example</span></span>  

 <span data-ttu-id="75134-129">En el ejemplo siguiente se muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="75134-129">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="75134-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="75134-130">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="75134-131">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="75134-131">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="75134-132">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="75134-132">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
