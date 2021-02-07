---
description: 'Más información sobre: <elemento System. Diagnostics>'
title: <System. Diagnostics (elemento>)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.diagnostics
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics
helpviewer_keywords:
- <system.diagnostics> element
- system.diagnostics element
ms.assetid: 3f348f42-fa72-4ff2-aa1c-bb9eecad4bb2
ms.openlocfilehash: ac5b1feaa6c8e7ab25a5210999040835322ac7a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750460"
---
# <a name="systemdiagnostics-element"></a><span data-ttu-id="9a205-103">\<system.diagnostics> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9a205-103">\<system.diagnostics> Element</span></span>

<span data-ttu-id="9a205-104">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-104">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;**\<system.diagnostics>**  
  
## <a name="syntax"></a><span data-ttu-id="9a205-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9a205-105">Syntax</span></span>  
  
```xml  
<system.diagnostics>
</system.diagnostics>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9a205-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9a205-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9a205-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9a205-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9a205-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9a205-108">Attributes</span></span>  

 <span data-ttu-id="9a205-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9a205-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="9a205-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9a205-110">Child Elements</span></span>  
  
|<span data-ttu-id="9a205-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a205-111">Element</span></span>|<span data-ttu-id="9a205-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a205-112">Description</span></span>|  
|-------------|-----------------|  
|[\<assert>](assert-element.md)|<span data-ttu-id="9a205-113">Especifica si se muestra un cuadro de mensaje cuando se llama al método <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>; también indica el nombre del archivo para el que se van a escribir los mensajes.</span><span class="sxs-lookup"><span data-stu-id="9a205-113">Specifies whether to display a message box when you call the <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType> method; also specifies the name of the file to write messages to.</span></span>|  
|[\<performanceCounters>](performancecounters-element.md)|<span data-ttu-id="9a205-114">Especifica el tamaño de la memoria global que comparten los contadores de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-114">Specifies the size of the global memory shared by performance counters.</span></span>|  
|[\<sharedListeners>](sharedlisteners-element.md)|<span data-ttu-id="9a205-115">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-115">Contains listeners that any source or trace element can reference.</span></span> <span data-ttu-id="9a205-116">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="9a205-116">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>|  
|[\<sources>](sources-element.md)|<span data-ttu-id="9a205-117">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-117">Specifies trace sources that initiate tracing messages.</span></span>|  
|[\<switches>](switches-element.md)|<span data-ttu-id="9a205-118">Contiene modificadores de seguimiento y los niveles en los que se establecen los modificadores de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-118">Contains trace switches and the levels where the trace switches are set.</span></span>|  
|[\<trace>](trace-element.md)|<span data-ttu-id="9a205-119">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9a205-119">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9a205-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9a205-120">Parent Elements</span></span>  
  
|<span data-ttu-id="9a205-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="9a205-121">Element</span></span>|<span data-ttu-id="9a205-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="9a205-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9a205-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9a205-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9a205-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9a205-124">Example</span></span>  

 <span data-ttu-id="9a205-125">En el ejemplo siguiente se muestra cómo insertar un modificador de seguimiento y un agente de escucha de seguimiento dentro del **\<system.diagnostics>** elemento.</span><span class="sxs-lookup"><span data-stu-id="9a205-125">The following example shows how to embed a trace switch and a trace listener inside the **\<system.diagnostics>** element.</span></span> <span data-ttu-id="9a205-126">El `General` modificador de seguimiento se establece en el <xref:System.Diagnostics.TraceLevel> nivel.</span><span class="sxs-lookup"><span data-stu-id="9a205-126">The `General` trace switch is set to the <xref:System.Diagnostics.TraceLevel> level.</span></span> <span data-ttu-id="9a205-127">El agente de escucha de seguimiento `myListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="9a205-127">The trace listener `myListener` creates a file called `MyListener.log` and writes the output to the file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a205-128">En la versión 2.0 de .NET Framework, puede utilizar texto para especificar el valor de un modificador.</span><span class="sxs-lookup"><span data-stu-id="9a205-128">In the .NET Framework version 2.0, you can use text to specify the value for a switch.</span></span> <span data-ttu-id="9a205-129">Por ejemplo, puede especificar `true` para un <xref:System.Diagnostics.BooleanSwitch> o usar el texto que representa un valor de enumeración como `Error` para <xref:System.Diagnostics.TraceSwitch> .</span><span class="sxs-lookup"><span data-stu-id="9a205-129">For example, you can specify `true` for a <xref:System.Diagnostics.BooleanSwitch> or use the text representing an enumeration value such as `Error` for a <xref:System.Diagnostics.TraceSwitch>.</span></span> <span data-ttu-id="9a205-130">La línea `<add name="myTraceSwitch" value="Error" />` es equivalente a `<add name="myTraceSwitch" value="1" />`.</span><span class="sxs-lookup"><span data-stu-id="9a205-130">The line `<add name="myTraceSwitch" value="Error" />` is equivalent to `<add name="myTraceSwitch" value="1" />`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9a205-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="9a205-131">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- [<span data-ttu-id="9a205-132">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="9a205-132">Trace and Debug Settings Schema</span></span>](index.md)
