---
title: '&lt;origen&gt; elemento'
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: b7c2a71b129a0ad7d1c2a72b18b8a69a111f9495
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="ltsourcegt-element"></a><span data-ttu-id="fc801-102">&lt;origen&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="fc801-102">&lt;source&gt; Element</span></span>
<span data-ttu-id="fc801-103">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-103">Specifies a trace source that initiates tracing messages.</span></span>  
  
 <span data-ttu-id="fc801-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="fc801-104">\<configuration></span></span>  
<span data-ttu-id="fc801-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="fc801-105">\<system.diagnostics></span></span>  
<span data-ttu-id="fc801-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="fc801-106">\<sources></span></span>  
<span data-ttu-id="fc801-107">\<origen ></span><span class="sxs-lookup"><span data-stu-id="fc801-107">\<source></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc801-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc801-108">Syntax</span></span>  
  
```xml  
<source>   
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fc801-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fc801-109">Attributes and Elements</span></span>  
 <span data-ttu-id="fc801-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fc801-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fc801-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="fc801-111">Attributes</span></span>  
  
|<span data-ttu-id="fc801-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="fc801-112">Attribute</span></span>|<span data-ttu-id="fc801-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc801-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="fc801-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fc801-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fc801-115">Especifica el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="fc801-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fc801-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fc801-117">Especifica el nombre de una instancia de modificador de seguimiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc801-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="fc801-118">Si el conmutador no se identifica en un `<switches>` elemento, el valor especifica el nivel para el conmutador.</span><span class="sxs-lookup"><span data-stu-id="fc801-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="fc801-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fc801-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fc801-120">Especifica el tipo del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="fc801-121">Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="fc801-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="fc801-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fc801-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fc801-123">Especifica el valor de un atributo específico del origen de seguimiento identificado por la <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> método para ese origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fc801-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fc801-124">Child Elements</span></span>  
  
|<span data-ttu-id="fc801-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc801-125">Element</span></span>|<span data-ttu-id="fc801-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc801-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fc801-127">\<listeners></span><span class="sxs-lookup"><span data-stu-id="fc801-127">\<listeners></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/listeners-element-for-source.md)|<span data-ttu-id="fc801-128">Contiene los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fc801-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fc801-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fc801-129">Parent Elements</span></span>  
  
|<span data-ttu-id="fc801-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="fc801-130">Element</span></span>|<span data-ttu-id="fc801-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="fc801-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fc801-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fc801-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fc801-133">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fc801-134">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fc801-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fc801-135">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc801-135">Remarks</span></span>  
 <span data-ttu-id="fc801-136">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="fc801-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fc801-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fc801-137">Example</span></span>  
 <span data-ttu-id="fc801-138">En el ejemplo siguiente se muestra cómo utilizar el `<source>` elemento que se va a agregar el origen de seguimiento `mySource` y para establecer el nivel para el modificador de origen denominado `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="fc801-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="fc801-139">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="fc801-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch" switchType="System.Diagnostics.SourceSwitch"  >  
        <listeners>  
          <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
            <filter type="System.Diagnostics.EventTypeFilter" initializeData="Error" />  
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
  
## <a name="see-also"></a><span data-ttu-id="fc801-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc801-140">See Also</span></span>  
 [<span data-ttu-id="fc801-141">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="fc801-141">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="fc801-142">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fc801-142">Trace Switches</span></span>](../../../../../docs/framework/debug-trace-profile/trace-switches.md)
