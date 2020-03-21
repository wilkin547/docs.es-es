---
title: <clear>Elemento <listeners> para for<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153586"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="c97cb-102">\<elemento> \<claro para \<los agentes de escucha> para el> de origen</span><span class="sxs-lookup"><span data-stu-id="c97cb-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="c97cb-103">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c97cb-103">Clears the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="c97cb-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="c97cb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="c97cb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="c97cb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="c97cb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="c97cb-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="c97cb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuente>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="c97cb-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="c97cb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="c97cb-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="c97cb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<>claro**</span><span class="sxs-lookup"><span data-stu-id="c97cb-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**</span></span>

## <a name="syntax"></a><span data-ttu-id="c97cb-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c97cb-110">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c97cb-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c97cb-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c97cb-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c97cb-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c97cb-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="c97cb-113">Attributes</span></span>  
 <span data-ttu-id="c97cb-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c97cb-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c97cb-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c97cb-115">Child Elements</span></span>  
 <span data-ttu-id="c97cb-116">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c97cb-116">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c97cb-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c97cb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="c97cb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="c97cb-118">Element</span></span>|<span data-ttu-id="c97cb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c97cb-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c97cb-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c97cb-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="c97cb-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c97cb-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="c97cb-122">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c97cb-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="c97cb-123">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c97cb-123">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="c97cb-124">Especifica los agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="c97cb-124">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c97cb-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c97cb-125">Remarks</span></span>  
 <span data-ttu-id="c97cb-126">El `<clear>` elemento quita todos los `Listeners` agentes de escucha <xref:System.Diagnostics.DefaultTraceListener>de la colección para un origen de seguimiento, incluido el archivo .</span><span class="sxs-lookup"><span data-stu-id="c97cb-126">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="c97cb-127">Puede usar `<clear>` el elemento `<add>` antes de usar el elemento para estar seguro de que no hay otros agentes de escucha activos en la colección.</span><span class="sxs-lookup"><span data-stu-id="c97cb-127">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="c97cb-128">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="c97cb-128">Configuration File</span></span>  
 <span data-ttu-id="c97cb-129">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c97cb-129">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c97cb-130">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c97cb-130">Example</span></span>  
 <span data-ttu-id="c97cb-131">En el ejemplo siguiente `<clear>` se muestra `<add>` cómo utilizar el `console` elemento `textListener` antes `Listeners` de utilizar `TraceSourceApp`los elementos para agregar los agentes de escucha y a la colección para el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c97cb-131">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c97cb-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c97cb-132">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="c97cb-133">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="c97cb-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="c97cb-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="c97cb-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
