---
title: Elemento <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 0eee325e01b41a15a19e4f40f479596f9d70f73b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153417"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="eb612-102">\<agentes de \<escucha> Element para el> de origen</span><span class="sxs-lookup"><span data-stu-id="eb612-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="eb612-103">Agrega o quita agentes <xref:System.Diagnostics.TraceSource.Listeners%2A> de escucha <xref:System.Diagnostics.TraceSource>de la colección para un archivo .</span><span class="sxs-lookup"><span data-stu-id="eb612-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="eb612-104">Un agente de escucha dirige la salida de seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="eb612-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[<span data-ttu-id="eb612-105">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="eb612-105">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="eb612-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb612-106">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="eb612-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb612-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>  
<span data-ttu-id="eb612-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuente>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="eb612-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>  
<span data-ttu-id="eb612-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oyentes>**</span><span class="sxs-lookup"><span data-stu-id="eb612-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb612-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb612-110">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="eb612-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="eb612-111">Attributes and Elements</span></span>  
 <span data-ttu-id="eb612-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="eb612-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="eb612-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="eb612-113">Attributes</span></span>  
 <span data-ttu-id="eb612-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="eb612-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="eb612-115">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="eb612-115">Child Elements</span></span>  
  
|<span data-ttu-id="eb612-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb612-116">Element</span></span>|<span data-ttu-id="eb612-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb612-117">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="eb612-118">\<añadir></span><span class="sxs-lookup"><span data-stu-id="eb612-118">\<add></span></span>](add-element-for-listeners-for-source.md)|<span data-ttu-id="eb612-119">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="eb612-119">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="eb612-120">\<eliminar></span><span class="sxs-lookup"><span data-stu-id="eb612-120">\<remove></span></span>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="eb612-121">Quita un agente `Listeners` de escucha de la colección.</span><span class="sxs-lookup"><span data-stu-id="eb612-121">Removes a listener from the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="eb612-122">\<>claro</span><span class="sxs-lookup"><span data-stu-id="eb612-122">\<clear></span></span>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="eb612-123">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb612-123">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="eb612-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="eb612-124">Parent Elements</span></span>  
  
|<span data-ttu-id="eb612-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="eb612-125">Element</span></span>|<span data-ttu-id="eb612-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb612-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="eb612-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="eb612-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="eb612-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb612-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="eb612-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb612-129">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="eb612-130">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="eb612-130">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb612-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb612-131">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="eb612-132">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="eb612-132">Configuration File</span></span>  
 <span data-ttu-id="eb612-133">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="eb612-133">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb612-134">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="eb612-134">Example</span></span>  
 <span data-ttu-id="eb612-135">En el ejemplo siguiente `<listeners>` se muestra cómo utilizar el `mySource` elemento para agregar un agente de escucha de seguimiento de consola al origen y quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="eb612-135">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="eb612-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb612-136">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="eb612-137">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="eb612-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="eb612-138">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="eb612-138">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
