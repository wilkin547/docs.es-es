---
title: '&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: d5e8518f2ca8a04d91f5bfdd9f6389c741d0278e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="22dd0-102">&lt;Borrar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;</span><span class="sxs-lookup"><span data-stu-id="22dd0-102">&lt;clear&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="22dd0-103">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22dd0-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="22dd0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22dd0-104">\<configuration></span></span>  
<span data-ttu-id="22dd0-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="22dd0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="22dd0-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="22dd0-106">\<sources></span></span>  
<span data-ttu-id="22dd0-107">\<origen ></span><span class="sxs-lookup"><span data-stu-id="22dd0-107">\<source></span></span>  
<span data-ttu-id="22dd0-108">\<los agentes de escucha ></span><span class="sxs-lookup"><span data-stu-id="22dd0-108">\<listeners></span></span>  
<span data-ttu-id="22dd0-109">\<Borrar ></span><span class="sxs-lookup"><span data-stu-id="22dd0-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22dd0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22dd0-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22dd0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22dd0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22dd0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22dd0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22dd0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="22dd0-113">Attributes</span></span>  
 <span data-ttu-id="22dd0-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22dd0-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="22dd0-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22dd0-115">Child Elements</span></span>  
 <span data-ttu-id="22dd0-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22dd0-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22dd0-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22dd0-117">Parent Elements</span></span>  
  
|<span data-ttu-id="22dd0-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="22dd0-118">Element</span></span>|<span data-ttu-id="22dd0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="22dd0-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22dd0-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22dd0-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="22dd0-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22dd0-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="22dd0-122">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22dd0-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="22dd0-123">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22dd0-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="22dd0-124">Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="22dd0-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22dd0-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22dd0-125">Remarks</span></span>  
 <span data-ttu-id="22dd0-126">El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para un origen de seguimiento, incluido el <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="22dd0-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="22dd0-127">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="22dd0-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="22dd0-128">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="22dd0-128">Configuration File</span></span>  
 <span data-ttu-id="22dd0-129">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="22dd0-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22dd0-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22dd0-130">Example</span></span>  
 <span data-ttu-id="22dd0-131">En el ejemplo siguiente se muestra cómo utilizar el `<clear>` elemento antes de usar el `<add>` elementos que se agregan los agentes de escucha `console` y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="22dd0-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
       <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <clear/>  
          <add name="console"   
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
        </listeners>  
      </source>  
    </sources>  
    <sharedListeners>  
      <add name="textListener"   
        type="System.Diagnostics.TextWriterTraceListener"   
        initializeData="myListener.log"/>  
    </sharedListeners>  
    <switches>  
      <add name="sourceSwitch" value="Warning"/>  
    </switches>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="22dd0-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="22dd0-132">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource>  
 <xref:System.Diagnostics.TraceListener>  
 [<span data-ttu-id="22dd0-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="22dd0-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="22dd0-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="22dd0-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
