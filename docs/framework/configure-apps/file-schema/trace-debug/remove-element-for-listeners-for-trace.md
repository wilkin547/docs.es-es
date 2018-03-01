---
title: '&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
caps.latest.revision: 
author: mcleblanc
ms.author: markl
manager: markl
ms.workload:
- dotnet
ms.openlocfilehash: 7bc4136fb917ee9b63b7cca26ba1834de21f542e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-lttracegt"></a><span data-ttu-id="4f7be-102">&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;seguimiento&gt;</span><span class="sxs-lookup"><span data-stu-id="4f7be-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;trace&gt;</span></span>
<span data-ttu-id="4f7be-103">Quita un agente de escucha de la **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="4f7be-103">Removes a listener from the **Listeners** collection.</span></span>  
  
 <span data-ttu-id="4f7be-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4f7be-104">\<configuration></span></span>  
<span data-ttu-id="4f7be-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="4f7be-105">\<system.diagnostics></span></span>  
<span data-ttu-id="4f7be-106">\<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="4f7be-106">\<trace></span></span>  
<span data-ttu-id="4f7be-107">\<los agentes de escucha ></span><span class="sxs-lookup"><span data-stu-id="4f7be-107">\<listeners></span></span>  
<span data-ttu-id="4f7be-108">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="4f7be-108">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f7be-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4f7be-109">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f7be-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4f7be-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4f7be-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4f7be-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f7be-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="4f7be-112">Attributes</span></span>  
  
|<span data-ttu-id="4f7be-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="4f7be-113">Attribute</span></span>|<span data-ttu-id="4f7be-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f7be-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4f7be-115">**name**</span><span class="sxs-lookup"><span data-stu-id="4f7be-115">**name**</span></span>|<span data-ttu-id="4f7be-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="4f7be-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="4f7be-117">El nombre del agente de escucha que se va a quitar de la **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="4f7be-117">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f7be-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4f7be-118">Child Elements</span></span>  
 <span data-ttu-id="4f7be-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4f7be-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f7be-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4f7be-120">Parent Elements</span></span>  
  
|<span data-ttu-id="4f7be-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="4f7be-121">Element</span></span>|<span data-ttu-id="4f7be-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f7be-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4f7be-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4f7be-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="4f7be-124">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="4f7be-124">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="4f7be-125">Agentes de escucha dirigen los resultados del seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="4f7be-125">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4f7be-126">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4f7be-126">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="4f7be-127">Configura el servicio de seguimiento ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="4f7be-127">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4f7be-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4f7be-128">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4f7be-129">Quitar el <xref:System.Diagnostics.DefaultTraceListener> desde el `Listeners` colección modifica el comportamiento de la <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="4f7be-129">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="4f7be-130">Llamar a un `Assert` o `Fail` método normalmente da como resultado la presentación de un cuadro de mensaje, sin embargo, no se muestra el cuadro de mensaje si la <xref:System.Diagnostics.DefaultTraceListener> no está en el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="4f7be-130">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4f7be-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f7be-131">Example</span></span>  
 <span data-ttu-id="4f7be-132">En el ejemplo siguiente se muestra cómo quitar el agente de escucha de seguimiento predeterminado de la traza **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="4f7be-132">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4f7be-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f7be-133">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 [<span data-ttu-id="4f7be-134">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="4f7be-134">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
