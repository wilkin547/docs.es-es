---
title: <clear>(Elemento <listeners> ) para<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 905dad8274fede80f4809ff3c7a014049f9df450
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153547"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="659a3-102">\<clear>(Elemento \<listeners> ) para\<trace></span><span class="sxs-lookup"><span data-stu-id="659a3-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="659a3-103">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="659a3-103">Clears the `Listeners` collection for trace.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="659a3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="659a3-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="659a3-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="659a3-105">Attributes and Elements</span></span>  
 <span data-ttu-id="659a3-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="659a3-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="659a3-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="659a3-107">Attributes</span></span>  
 <span data-ttu-id="659a3-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="659a3-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="659a3-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="659a3-109">Child Elements</span></span>  
 <span data-ttu-id="659a3-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="659a3-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="659a3-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="659a3-111">Parent Elements</span></span>  
  
|<span data-ttu-id="659a3-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="659a3-112">Element</span></span>|<span data-ttu-id="659a3-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="659a3-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="659a3-114">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="659a3-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="659a3-115">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="659a3-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="659a3-116">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="659a3-116">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="659a3-117">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="659a3-117">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="659a3-118">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="659a3-118">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="659a3-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="659a3-119">Remarks</span></span>  
 <span data-ttu-id="659a3-120">El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="659a3-120">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="659a3-121">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="659a3-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="659a3-122">Puede borrar la `Listeners` colección mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> método en la <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> propiedad ( `System.Diagnostics.Trace.Listeners.Clear()` ).</span><span class="sxs-lookup"><span data-stu-id="659a3-122">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="659a3-123">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="659a3-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="659a3-124">El `<clear>` elemento quita <xref:System.Diagnostics.DefaultTraceListener> de la `Listeners` colección, modificando el comportamiento de los <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> métodos, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> , <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="659a3-124">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="659a3-125">La llamada a un `Assert` `Fail` método o suele tener como resultado la presentación de un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="659a3-125">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="659a3-126">Sin embargo, el cuadro de mensaje no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="659a3-126">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="659a3-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="659a3-127">Example</span></span>  
 <span data-ttu-id="659a3-128">En el ejemplo siguiente se muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="659a3-128">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="659a3-129">Consulte también</span><span class="sxs-lookup"><span data-stu-id="659a3-129">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="659a3-130">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="659a3-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<remove>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="659a3-131">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="659a3-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
