---
title: Elemento <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: d7641611e5d8257b49bc6a6abd0a2fadfde66e91
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697300"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="321f6-102">\<listeners > elemento para \<source ></span><span class="sxs-lookup"><span data-stu-id="321f6-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="321f6-103">Agrega o quita agentes de escucha en la colección <xref:System.Diagnostics.TraceSource.Listeners%2A> para un <xref:System.Diagnostics.TraceSource>.</span><span class="sxs-lookup"><span data-stu-id="321f6-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="321f6-104">Un agente de escucha dirige los resultados del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="321f6-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="321f6-105"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="321f6-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="321f6-106">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="321f6-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="321f6-107">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sources >** ](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="321f6-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="321f6-108">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5[ **\<source >** ](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="321f6-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="321f6-109">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 @ no__t-4 @ no__t-5 @ no__t-6 @ no__t-7 **\<listeners >**</span><span class="sxs-lookup"><span data-stu-id="321f6-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="321f6-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="321f6-110">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="321f6-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="321f6-111">Attributes and Elements</span></span>  
 <span data-ttu-id="321f6-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="321f6-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="321f6-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="321f6-113">Attributes</span></span>  
 <span data-ttu-id="321f6-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="321f6-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="321f6-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="321f6-115">Child Elements</span></span>  
  
|<span data-ttu-id="321f6-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="321f6-116">Element</span></span>|<span data-ttu-id="321f6-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="321f6-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="321f6-118">\<add></span><span class="sxs-lookup"><span data-stu-id="321f6-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="321f6-119">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="321f6-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="321f6-120">\<remove></span><span class="sxs-lookup"><span data-stu-id="321f6-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="321f6-121">Quita un agente de escucha de la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="321f6-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="321f6-122">\<clear></span><span class="sxs-lookup"><span data-stu-id="321f6-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="321f6-123">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="321f6-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="321f6-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="321f6-124">Parent Elements</span></span>  
  
|<span data-ttu-id="321f6-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="321f6-125">Element</span></span>|<span data-ttu-id="321f6-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="321f6-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="321f6-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="321f6-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="321f6-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="321f6-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="321f6-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="321f6-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="321f6-130">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="321f6-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="321f6-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="321f6-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="321f6-132">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="321f6-132">Configuration File</span></span>  
 <span data-ttu-id="321f6-133">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="321f6-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="321f6-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="321f6-134">Example</span></span>  
 <span data-ttu-id="321f6-135">En el ejemplo siguiente se muestra cómo usar el elemento `<listeners>` para agregar un agente de escucha de seguimiento de consola al origen de `mySource` y para quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="321f6-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"   
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener">  
            <filter type="System.Diagnostics.EventTypeFilter"   
              initializeData="Error"/>  
          </add>  
          <remove name="Default"/>  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="321f6-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="321f6-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="321f6-137">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="321f6-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="321f6-138">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="321f6-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
