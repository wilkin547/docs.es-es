---
title: <System. Diagnostics (elemento>)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: 4f831592d7d178276b1625e1ef7d8512085342af
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153212"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="9e3fd-102">\<system.diagnostics> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9e3fd-102">\<system.diagnostics> Element</span></span>
<span data-ttu-id="9e3fd-103">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-103">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="9e3fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9e3fd-104">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9e3fd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9e3fd-105">Attributes and Elements</span></span>  
 <span data-ttu-id="9e3fd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9e3fd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="9e3fd-107">Attributes</span></span>  
 <span data-ttu-id="9e3fd-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9e3fd-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9e3fd-109">Child Elements</span></span>  
  
|<span data-ttu-id="9e3fd-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e3fd-110">Element</span></span>|<span data-ttu-id="9e3fd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e3fd-111">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="9e3fd-112">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-112">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="9e3fd-113">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-113">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="9e3fd-114">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-114">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="9e3fd-115">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-115">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="9e3fd-116">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-116">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="9e3fd-117">Contiene modificadores de seguimiento y los niveles en los que se establecen los modificadores de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-117">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="9e3fd-118">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-118">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9e3fd-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9e3fd-119">Parent Elements</span></span>  
  
|<span data-ttu-id="9e3fd-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="9e3fd-120">Element</span></span>|<span data-ttu-id="9e3fd-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="9e3fd-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9e3fd-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9e3fd-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9e3fd-123">Example</span></span>  
 <span data-ttu-id="9e3fd-124">En el ejemplo siguiente se muestra cómo insertar un modificador de seguimiento y un agente de escucha de seguimiento dentro del **\<system.diagnostics>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-124">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="9e3fd-125">El `General` modificador de seguimiento se establece en el <xref:System.Diagnostics.TraceLevel> nivel.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-125">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="9e3fd-126">El agente de escucha de seguimiento `myListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-126">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e3fd-127">En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-127">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="9e3fd-128">Por ejemplo, puede especificar `true` para un <xref:System.Diagnostics.BooleanSwitch> o usar el texto que representa un valor de enumeración como `Error` para <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="9e3fd-128">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="9e3fd-129">La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="9e3fd-129">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
      </switches>  
      <trace autoflush="true" indentsize="2">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, System, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="MyListener.log" traceOutputOptions="ProcessId, LogicalOperationStack, Timestamp, ThreadId, Callstack, DateTime" />  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="9e3fd-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9e3fd-130">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="9e3fd-131">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="9e3fd-131">Trace and Debug Settings Schema</span></span>](index.md)
