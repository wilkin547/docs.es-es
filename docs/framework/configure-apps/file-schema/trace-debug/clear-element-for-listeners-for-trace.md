---
title: <clear> elemento de <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
ms.openlocfilehash: 049b8e7ed17633c0f34b062915afaf719927dad6
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74088917"
---
# <a name="clear-element-for-listeners-for-trace"></a><span data-ttu-id="da6ea-102">\<borrar > elemento para \<agentes de escucha > para \<> de seguimiento</span><span class="sxs-lookup"><span data-stu-id="da6ea-102">\<clear> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="da6ea-103">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da6ea-103">Clears the `Listeners` collection for trace.</span></span>  

<span data-ttu-id="da6ea-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="da6ea-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="da6ea-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="da6ea-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="da6ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<** ](trace-element.md) > de seguimiento</span><span class="sxs-lookup"><span data-stu-id="da6ea-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>\
<span data-ttu-id="da6ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-trace.md) ></span><span class="sxs-lookup"><span data-stu-id="da6ea-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>\
<span data-ttu-id="da6ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**clear >**</span><span class="sxs-lookup"><span data-stu-id="da6ea-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="da6ea-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da6ea-109">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da6ea-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="da6ea-110">Attributes and Elements</span></span>  
 <span data-ttu-id="da6ea-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="da6ea-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da6ea-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="da6ea-112">Attributes</span></span>  
 <span data-ttu-id="da6ea-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="da6ea-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="da6ea-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="da6ea-114">Child Elements</span></span>  
 <span data-ttu-id="da6ea-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="da6ea-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da6ea-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="da6ea-116">Parent Elements</span></span>  
  
|<span data-ttu-id="da6ea-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="da6ea-117">Element</span></span>|<span data-ttu-id="da6ea-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="da6ea-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="da6ea-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="da6ea-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="da6ea-120">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da6ea-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="da6ea-121">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da6ea-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="da6ea-122">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="da6ea-122">Contains listeners that collect, store, and route messages.</span></span> <span data-ttu-id="da6ea-123">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="da6ea-123">Listeners direct the tracing output to an appropriate target.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="da6ea-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da6ea-124">Remarks</span></span>  
 <span data-ttu-id="da6ea-125">El elemento `<clear>` quita todos los agentes de escucha de la colección `Listeners` para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da6ea-125">The `<clear>` element removes all listeners from the `Listeners` collection for trace.</span></span> <span data-ttu-id="da6ea-126">Puede usar el elemento `<clear>` antes de usar el elemento `<add>` para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="da6ea-126">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
 <span data-ttu-id="da6ea-127">Puede borrar la colección de `Listeners` mediante programación llamando al método <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> en la propiedad <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> (`System.Diagnostics.Trace.Listeners.Clear()`).</span><span class="sxs-lookup"><span data-stu-id="da6ea-127">You can clear the `Listeners` collection programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> method on the <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> property (`System.Diagnostics.Trace.Listeners.Clear()`).</span></span>  
  
 <span data-ttu-id="da6ea-128">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="da6ea-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="da6ea-129">El elemento `<clear>` quita el <xref:System.Diagnostics.DefaultTraceListener> de la colección `Listeners`, modificando el comportamiento de los métodos <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="da6ea-129">The `<clear>` element removes the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection, altering the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="da6ea-130">La llamada a un método `Assert` o `Fail` suele tener como resultado la presentación de un cuadro de mensaje.</span><span class="sxs-lookup"><span data-stu-id="da6ea-130">Calling an `Assert` or `Fail` method normally results in the display of a message box.</span></span> <span data-ttu-id="da6ea-131">Sin embargo, el cuadro de mensaje no se muestra si el <xref:System.Diagnostics.DefaultTraceListener> no está en la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="da6ea-131">However, the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da6ea-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="da6ea-132">Example</span></span>  
 <span data-ttu-id="da6ea-133">En el ejemplo siguiente se muestra cómo utilizar el elemento `<clear>` antes de utilizar el elemento `<add>` para agregar el agente de escucha `console` a la colección de `Listeners` para el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="da6ea-133">The following example shows how to use the `<clear>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for trace.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="da6ea-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="da6ea-134">See also</span></span>

- <xref:System.Diagnostics.Trace.Listeners%2A>
- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="da6ea-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="da6ea-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="da6ea-136">\<remove></span><span class="sxs-lookup"><span data-stu-id="da6ea-136">\<remove></span></span>](remove-element-for-listeners-for-trace.md)
- [<span data-ttu-id="da6ea-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="da6ea-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
