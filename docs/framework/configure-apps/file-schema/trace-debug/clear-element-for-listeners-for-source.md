---
title: <clear> Elemento para <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 63d3bb272fcdbee2c59b0569c85f8183cdac8666
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158358"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="a684c-102">\<Borrar > (elemento) para \<los agentes de escucha > para \<origen ></span><span class="sxs-lookup"><span data-stu-id="a684c-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="a684c-103">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a684c-103">Clears the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="a684c-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="a684c-104">\<configuration></span></span>  
<span data-ttu-id="a684c-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="a684c-105">\<system.diagnostics></span></span>  
<span data-ttu-id="a684c-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="a684c-106">\<sources></span></span>  
<span data-ttu-id="a684c-107">\<source></span><span class="sxs-lookup"><span data-stu-id="a684c-107">\<source></span></span>  
<span data-ttu-id="a684c-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="a684c-108">\<listeners></span></span>  
<span data-ttu-id="a684c-109">\<clear></span><span class="sxs-lookup"><span data-stu-id="a684c-109">\<clear></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a684c-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a684c-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a684c-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a684c-111">Attributes and Elements</span></span>  
 <span data-ttu-id="a684c-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a684c-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a684c-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="a684c-113">Attributes</span></span>  
 <span data-ttu-id="a684c-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a684c-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a684c-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a684c-115">Child Elements</span></span>  
 <span data-ttu-id="a684c-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a684c-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a684c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a684c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="a684c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="a684c-118">Element</span></span>|<span data-ttu-id="a684c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a684c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a684c-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a684c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a684c-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a684c-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="a684c-122">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a684c-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="a684c-123">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a684c-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="a684c-124">Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="a684c-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a684c-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a684c-125">Remarks</span></span>  
 <span data-ttu-id="a684c-126">El `<clear>` elemento quita todos los agentes de escucha desde el `Listeners` colección para un origen de seguimiento, incluido el <xref:System.Diagnostics.DefaultTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="a684c-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="a684c-127">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento que esté seguro de que no hay ningún otros agentes de escucha activos en la colección.</span><span class="sxs-lookup"><span data-stu-id="a684c-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="a684c-128">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="a684c-128">Configuration File</span></span>  
 <span data-ttu-id="a684c-129">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a684c-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a684c-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a684c-130">Example</span></span>  
 <span data-ttu-id="a684c-131">El ejemplo siguiente muestra cómo usar el `<clear>` elemento antes de usar el `<add>` elementos para agregar los agentes de escucha `console` y `textListener` a la `Listeners` recopilación para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="a684c-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a684c-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a684c-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="a684c-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="a684c-133">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="a684c-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="a684c-134">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
