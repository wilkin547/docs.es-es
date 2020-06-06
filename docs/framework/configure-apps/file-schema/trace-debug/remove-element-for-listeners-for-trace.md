---
title: <remove>(Elemento <listeners> ) para<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/remove
helpviewer_keywords:
- remove element
- <remove> element
ms.assetid: 9a5cd1b5-be1a-485f-8f0c-2890ad3ef3e0
ms.openlocfilehash: f06973ec30d5061e4a200d6bf7e68adcf6302018
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088846"
---
# <a name="remove-element-for-listeners-for-trace"></a><span data-ttu-id="6e1de-102">\<remove>(Elemento \<listeners> ) para\<trace></span><span class="sxs-lookup"><span data-stu-id="6e1de-102">\<remove> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="6e1de-103">Quita un agente de escucha de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="6e1de-103">Removes a listener from the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="6e1de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6e1de-104">Syntax</span></span>  
  
```xml  
<remove name="listener name" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e1de-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6e1de-105">Attributes and Elements</span></span>  
 <span data-ttu-id="6e1de-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6e1de-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e1de-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6e1de-107">Attributes</span></span>  
  
|<span data-ttu-id="6e1de-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="6e1de-108">Attribute</span></span>|<span data-ttu-id="6e1de-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e1de-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6e1de-110">**name**</span><span class="sxs-lookup"><span data-stu-id="6e1de-110">**name**</span></span>|<span data-ttu-id="6e1de-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="6e1de-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="6e1de-112">Nombre del agente de escucha que se va a quitar de la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="6e1de-112">The name of the listener to remove from the **Listeners** collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e1de-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6e1de-113">Child Elements</span></span>  
 <span data-ttu-id="6e1de-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6e1de-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e1de-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6e1de-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6e1de-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="6e1de-116">Element</span></span>|<span data-ttu-id="6e1de-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6e1de-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6e1de-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6e1de-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="6e1de-119">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="6e1de-119">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="6e1de-120">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="6e1de-120">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6e1de-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e1de-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`trace`|<span data-ttu-id="6e1de-122">Configura el servicio de traza de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6e1de-122">Configures the ASP.NET trace service.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6e1de-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6e1de-123">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6e1de-124">Al quitar <xref:System.Diagnostics.DefaultTraceListener> de la `Listeners` colección se modifica el comportamiento de los <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType> métodos,, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType> y <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="6e1de-124">Removing the <xref:System.Diagnostics.DefaultTraceListener> from the `Listeners` collection alters the behavior of the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, and <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="6e1de-125">La llamada a un `Assert` `Fail` método o suele tener como resultado la presentación de un cuadro de mensaje; sin embargo, el cuadro de mensaje no se muestra si <xref:System.Diagnostics.DefaultTraceListener> no está en la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="6e1de-125">Calling an `Assert` or `Fail` method normally results in the display of a message box, however the message box is not displayed if the <xref:System.Diagnostics.DefaultTraceListener> is not in the `Listeners` collection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e1de-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6e1de-126">Example</span></span>  
 <span data-ttu-id="6e1de-127">En el ejemplo siguiente se muestra cómo quitar el agente de escucha de seguimiento predeterminado de la colección de **agentes de escucha** de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6e1de-127">The following example shows how to remove the default trace listener from the trace **Listeners** collection.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6e1de-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6e1de-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- [<span data-ttu-id="6e1de-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="6e1de-129">Trace and Debug Settings Schema</span></span>](index.md)
