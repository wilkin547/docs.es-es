---
title: '&lt;orígenes&gt; elemento'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
author: mcleblanc
ms.author: markl
ms.openlocfilehash: a9c5c5529e349eca2ba089ed6fb71da4bd48430a
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "47203334"
---
# <a name="ltsourcesgt-element"></a><span data-ttu-id="22a2d-102">&lt;orígenes&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="22a2d-102">&lt;sources&gt; Element</span></span>
<span data-ttu-id="22a2d-103">Especifica los orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22a2d-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="22a2d-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22a2d-104">\<configuration></span></span>  
<span data-ttu-id="22a2d-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="22a2d-105">\<system.diagnostics></span></span>  
<span data-ttu-id="22a2d-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="22a2d-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22a2d-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22a2d-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22a2d-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22a2d-108">Attributes and Elements</span></span>  
 <span data-ttu-id="22a2d-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22a2d-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22a2d-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="22a2d-110">Attributes</span></span>  
 <span data-ttu-id="22a2d-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22a2d-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22a2d-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22a2d-112">Child Elements</span></span>  
  
|<span data-ttu-id="22a2d-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="22a2d-113">Element</span></span>|<span data-ttu-id="22a2d-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a2d-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="22a2d-115">\<source></span><span class="sxs-lookup"><span data-stu-id="22a2d-115">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)|<span data-ttu-id="22a2d-116">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="22a2d-116">Required element.</span></span><br /><br /> <span data-ttu-id="22a2d-117">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22a2d-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="22a2d-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22a2d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="22a2d-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="22a2d-119">Element</span></span>|<span data-ttu-id="22a2d-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="22a2d-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22a2d-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22a2d-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="22a2d-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22a2d-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22a2d-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22a2d-123">Remarks</span></span>  
 <span data-ttu-id="22a2d-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22a2d-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22a2d-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22a2d-125">Example</span></span>  
 <span data-ttu-id="22a2d-126">El ejemplo siguiente muestra cómo usar el `<sources>` elemento va a agregar el origen de seguimiento `mySource` y establecer el nivel del modificador de origen denominado `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="22a2d-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="22a2d-127">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="22a2d-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="22a2d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="22a2d-128">See Also</span></span>  
 <xref:System.Diagnostics.TraceListener>  
 <xref:System.Diagnostics.DefaultTraceListener>  
 <xref:System.Diagnostics.TextWriterTraceListener>  
 <xref:System.Diagnostics.ConsoleTraceListener>  
 <xref:System.Diagnostics.EventLogTraceListener>  
 <xref:System.Diagnostics.XmlWriterTraceListener>  
 [<span data-ttu-id="22a2d-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="22a2d-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="22a2d-130">\<source></span><span class="sxs-lookup"><span data-stu-id="22a2d-130">\<source></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/source-element.md)
