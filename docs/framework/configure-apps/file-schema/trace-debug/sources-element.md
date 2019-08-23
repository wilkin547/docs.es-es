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
ms.openlocfilehash: 73d4eb2741bdbe5a07704ca0f3b2f779706e66dc
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926953"
---
# <a name="sources-element"></a><span data-ttu-id="69be2-102">\<sources > elemento</span><span class="sxs-lookup"><span data-stu-id="69be2-102">\<sources> Element</span></span>
<span data-ttu-id="69be2-103">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69be2-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
 <span data-ttu-id="69be2-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="69be2-104">\<configuration></span></span>  
<span data-ttu-id="69be2-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="69be2-105">\<system.diagnostics></span></span>  
<span data-ttu-id="69be2-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="69be2-106">\<sources></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69be2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69be2-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69be2-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="69be2-108">Attributes and Elements</span></span>  
 <span data-ttu-id="69be2-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="69be2-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69be2-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="69be2-110">Attributes</span></span>  
 <span data-ttu-id="69be2-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="69be2-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="69be2-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="69be2-112">Child Elements</span></span>  
  
|<span data-ttu-id="69be2-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="69be2-113">Element</span></span>|<span data-ttu-id="69be2-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69be2-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69be2-115">\<source></span><span class="sxs-lookup"><span data-stu-id="69be2-115">\<source></span></span>](source-element.md)|<span data-ttu-id="69be2-116">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="69be2-116">Required element.</span></span><br /><br /> <span data-ttu-id="69be2-117">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69be2-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69be2-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="69be2-118">Parent Elements</span></span>  
  
|<span data-ttu-id="69be2-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="69be2-119">Element</span></span>|<span data-ttu-id="69be2-120">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="69be2-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="69be2-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="69be2-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="69be2-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="69be2-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69be2-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69be2-123">Remarks</span></span>  
 <span data-ttu-id="69be2-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="69be2-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="69be2-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="69be2-125">Example</span></span>  
 <span data-ttu-id="69be2-126">En el ejemplo siguiente se muestra cómo utilizar `<sources>` el elemento para agregar el origen `mySource` de seguimiento y establecer el nivel para el modificador `sourceSwitch`de origen denominado.</span><span class="sxs-lookup"><span data-stu-id="69be2-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="69be2-127">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="69be2-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="69be2-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="69be2-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="69be2-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="69be2-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="69be2-130">\<source></span><span class="sxs-lookup"><span data-stu-id="69be2-130">\<source></span></span>](source-element.md)
