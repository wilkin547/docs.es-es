---
title: Elemento @no__t 0 para <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 56d1e56514aed98d5f3b9f7363e461af6ac68a8c
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697222"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="c165a-102">\<remove > elemento para > \<listeners para \<trace ></span><span class="sxs-lookup"><span data-stu-id="c165a-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="c165a-103">Quita un agente de escucha de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="c165a-103">Removes a listener from the **Listeners** collection.</span></span>  
  
[<span data-ttu-id="c165a-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="c165a-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="c165a-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c165a-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="c165a-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<trace >** ](trace-element.md)</span><span class="sxs-lookup"><span data-stu-id="c165a-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)</span></span>  
<span data-ttu-id="c165a-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<listeners >** ](listeners-element-for-trace.md)</span><span class="sxs-lookup"><span data-stu-id="c165a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)</span></span>  
<span data-ttu-id="c165a-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<remove >**</span><span class="sxs-lookup"><span data-stu-id="c165a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c165a-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c165a-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c165a-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c165a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="c165a-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c165a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c165a-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="c165a-112">Attributes</span></span>  
  
|<span data-ttu-id="c165a-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="c165a-113">Attribute</span></span>|<span data-ttu-id="c165a-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="c165a-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c165a-115">**name**</span><span class="sxs-lookup"><span data-stu-id="c165a-115">**name**</span></span>|<span data-ttu-id="c165a-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="c165a-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="c165a-117">Nombre del agente de escucha que se va a quitar de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="c165a-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c165a-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c165a-118">Child Elements</span></span>  
 <span data-ttu-id="c165a-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c165a-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c165a-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c165a-120">Parent Elements</span></span>  
  
|<span data-ttu-id="c165a-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="c165a-121">Element</span></span>|<span data-ttu-id="c165a-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="c165a-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c165a-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c165a-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="c165a-124">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="c165a-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="c165a-125">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="c165a-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c165a-126">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c165a-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="c165a-127">Configura el servicio de seguimiento ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="c165a-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c165a-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c165a-128">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c165a-129">Al quitar el <xref:System.Diagnostics.DefaultTraceListener> de la colección `Listeners` se modifica el comportamiento de los métodos @no__t 2, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c165a-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="c165a-130">La llamada a un método `Assert` o `Fail` suele tener como resultado la presentación de un cuadro de mensaje; sin embargo, el cuadro de mensaje no se muestra si el <xref:System.Diagnostics.DefaultTraceListener> no está en la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="c165a-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c165a-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c165a-131">Example</span></span>  
 <span data-ttu-id="c165a-132">En el ejemplo siguiente se muestra cómo quitar el agente de escucha de seguimiento predeterminado de la colección de **agentes de escucha** de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c165a-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <remove name="Default" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c165a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="c165a-133">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="c165a-134">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="c165a-134">Trace and Debug Settings Schema</span></span>](index.md)
