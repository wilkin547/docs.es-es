---
title: Elemento @no__t 0 para <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 4a11308278f755ec8271477352d91d8797d105c5
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699496"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="d5962-102">\<remove > elemento para > \<listeners para \<source ></span><span class="sxs-lookup"><span data-stu-id="d5962-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d5962-103">Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5962-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
[<span data-ttu-id="d5962-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="d5962-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="d5962-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5962-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="d5962-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5962-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="d5962-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="d5962-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="d5962-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7[ **&nbsp;0listeners >** ](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="d5962-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>  
<span data-ttu-id="d5962-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<remove>**</span><span class="sxs-lookup"><span data-stu-id="d5962-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5962-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d5962-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d5962-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d5962-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d5962-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d5962-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d5962-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d5962-113">Attributes</span></span>  
  
|<span data-ttu-id="d5962-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d5962-114">Attribute</span></span>|<span data-ttu-id="d5962-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5962-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d5962-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="d5962-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="d5962-117">Nombre del agente de escucha que se va a quitar de la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="d5962-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d5962-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d5962-118">Child Elements</span></span>  
 <span data-ttu-id="d5962-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="d5962-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d5962-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d5962-120">Parent Elements</span></span>  
  
|<span data-ttu-id="d5962-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="d5962-121">Element</span></span>|<span data-ttu-id="d5962-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="d5962-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d5962-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d5962-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d5962-124">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5962-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d5962-125">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5962-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d5962-126">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5962-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d5962-127">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d5962-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d5962-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d5962-128">Remarks</span></span>  
 <span data-ttu-id="d5962-129">El elemento `<remove>` quita un agente de escucha especificado de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d5962-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d5962-130">Puede quitar un elemento de la colección `Listeners` para un origen de seguimiento mediante programación llamando al método <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> en la propiedad <xref:System.Diagnostics.TraceSource.Listeners%2A> de la instancia de <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="d5962-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="d5962-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d5962-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d5962-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d5962-132">Example</span></span>  
 <span data-ttu-id="d5962-133">En el ejemplo siguiente se muestra cómo usar el elemento `<remove>` antes de usar el elemento `<add>` para agregar el agente de escucha `console` a la colección `Listeners` para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="d5962-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="d5962-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="d5962-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="d5962-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="d5962-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d5962-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="d5962-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="d5962-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d5962-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
