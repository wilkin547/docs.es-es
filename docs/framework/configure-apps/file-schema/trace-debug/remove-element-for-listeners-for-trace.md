---
description: 'Más información sobre: <remove> elemento para <listeners> para <trace>'
title: <remove> (Elemento <listeners> ) para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: 8b863cb535c28f090374e284717d5bf38f22e881
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750603"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="69602-103">\<remove> (Elemento \<listeners> ) para \<trace></span><span class="sxs-lookup"><span data-stu-id="69602-103">\<remove> Element for \<listeners> for \<trace></span></span>

<span data-ttu-id="69602-104">Quita un agente de escucha de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="69602-104">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="69602-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69602-105">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69602-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69602-106">Attributes and Elements</span></span>  

 <span data-ttu-id="69602-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69602-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69602-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="69602-108">Attributes</span></span>  
  
|<span data-ttu-id="69602-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="69602-109">Attribute</span></span>|<span data-ttu-id="69602-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="69602-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69602-111">**name**</span><span class="sxs-lookup"><span data-stu-id="69602-111">**name**</span></span>|<span data-ttu-id="69602-112">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="69602-112">Required attribute.</span></span><br /><br /> <span data-ttu-id="69602-113">Nombre del agente de escucha que se va a quitar de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="69602-113">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69602-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69602-114">Child Elements</span></span>  

 <span data-ttu-id="69602-115">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="69602-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69602-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69602-116">Parent Elements</span></span>  
  
|<span data-ttu-id="69602-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="69602-117">Element</span></span>|<span data-ttu-id="69602-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="69602-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69602-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69602-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="69602-120">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="69602-120">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="69602-121">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="69602-121">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="69602-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69602-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="69602-123">Configura el servicio de traza de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="69602-123">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69602-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="69602-124">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69602-125">Al quitar <xref:System.Diagnostics.DefaultTraceListener> de la `Listeners` colección se modifica el comportamiento de los <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> métodos,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="69602-125">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="69602-126">La llamada a un `Assert` `Fail` método o suele tener como resultado la presentación de un cuadro de mensaje; sin embargo, el cuadro de mensaje no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="69602-126">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69602-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69602-127">Example</span></span>  

 <span data-ttu-id="69602-128">En el ejemplo siguiente se muestra cómo quitar el agente de escucha de seguimiento predeterminado de la colección de **agentes de escucha** de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69602-128">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69602-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="69602-129">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="69602-130">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="69602-130">Trace and Debug Settings Schema</span></span>](index.md)
