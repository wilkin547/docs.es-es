---
title: <sources> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 2a76816ee73f516b3c7544877a77531acaa8e09c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153274"
---
# <a name="sources-element"></a><span data-ttu-id="dc97e-102">\<fuentes> Elemento</span><span class="sxs-lookup"><span data-stu-id="dc97e-102">\<sources> Element</span></span>
<span data-ttu-id="dc97e-103">Especifica los orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dc97e-103">Specifies trace sources that initiate tracing messages.</span></span>  

<span data-ttu-id="dc97e-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc97e-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="dc97e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="dc97e-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="dc97e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<fuentes>**</span><span class="sxs-lookup"><span data-stu-id="dc97e-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>

## <a name="syntax"></a><span data-ttu-id="dc97e-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dc97e-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc97e-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="dc97e-108">Attributes and Elements</span></span>  
 <span data-ttu-id="dc97e-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="dc97e-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc97e-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="dc97e-110">Attributes</span></span>  
 <span data-ttu-id="dc97e-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="dc97e-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc97e-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="dc97e-112">Child Elements</span></span>  
  
|<span data-ttu-id="dc97e-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc97e-113">Element</span></span>|<span data-ttu-id="dc97e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc97e-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc97e-115">\<fuente></span><span class="sxs-lookup"><span data-stu-id="dc97e-115">\<source></span></span>](source-element.md)|<span data-ttu-id="dc97e-116">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="dc97e-116">Required element.</span></span><br /><br /> <span data-ttu-id="dc97e-117">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dc97e-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="dc97e-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="dc97e-118">Parent Elements</span></span>  
  
|<span data-ttu-id="dc97e-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="dc97e-119">Element</span></span>|<span data-ttu-id="dc97e-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="dc97e-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="dc97e-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="dc97e-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="dc97e-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="dc97e-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc97e-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="dc97e-123">Remarks</span></span>  
 <span data-ttu-id="dc97e-124">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="dc97e-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dc97e-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="dc97e-125">Example</span></span>  
 <span data-ttu-id="dc97e-126">En el ejemplo siguiente `<sources>` se muestra cómo `mySource` utilizar el elemento para agregar `sourceSwitch`el origen de seguimiento y establecer el nivel para el modificador de origen denominado .</span><span class="sxs-lookup"><span data-stu-id="dc97e-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="dc97e-127">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="dc97e-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="dc97e-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dc97e-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="dc97e-129">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="dc97e-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="dc97e-130">\<fuente></span><span class="sxs-lookup"><span data-stu-id="dc97e-130">\<source></span></span>](source-element.md)
