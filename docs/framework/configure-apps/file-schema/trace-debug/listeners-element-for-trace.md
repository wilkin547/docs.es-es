---
title: <listeners> (elemento) para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: f9f12d9e61e2472b897169727bbb4fbf9833efd6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179119"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="cbf9b-102">\<los agentes de escucha > (elemento) para \<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="cbf9b-102">\<listeners> Element for \<trace></span></span>
<span data-ttu-id="cbf9b-103">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="cbf9b-104">Los agentes de escucha dirigen los resultados de seguimiento a un destino apropiado.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-104">Listeners direct the tracing output to an appropriate target.</span></span>  
  
 <span data-ttu-id="cbf9b-105">\<Configuración > elemento</span><span class="sxs-lookup"><span data-stu-id="cbf9b-105">\<configuration> Element</span></span>  
<span data-ttu-id="cbf9b-106">\<System.Diagnostics > elemento</span><span class="sxs-lookup"><span data-stu-id="cbf9b-106">\<system.diagnostics> Element</span></span>  
<span data-ttu-id="cbf9b-107">\<seguimiento > elemento</span><span class="sxs-lookup"><span data-stu-id="cbf9b-107">\<trace> Element</span></span>  
<span data-ttu-id="cbf9b-108">\<los agentes de escucha > (elemento) para \<seguimiento ></span><span class="sxs-lookup"><span data-stu-id="cbf9b-108">\<listeners> Element for \<trace></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbf9b-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cbf9b-109">Syntax</span></span>  
  
```xml  
<listeners>   
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="cbf9b-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="cbf9b-110">Attributes and Elements</span></span>  
 <span data-ttu-id="cbf9b-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="cbf9b-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="cbf9b-112">Attributes</span></span>  
 <span data-ttu-id="cbf9b-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="cbf9b-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="cbf9b-114">Child Elements</span></span>  
  
|<span data-ttu-id="cbf9b-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="cbf9b-115">Element</span></span>|<span data-ttu-id="cbf9b-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbf9b-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="cbf9b-117">\<add></span><span class="sxs-lookup"><span data-stu-id="cbf9b-117">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-listeners-for-trace.md)|<span data-ttu-id="cbf9b-118">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-118">Adds a listener to the `Listeners` collection.</span></span>|  
|[<span data-ttu-id="cbf9b-119">\<clear></span><span class="sxs-lookup"><span data-stu-id="cbf9b-119">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-trace.md)|<span data-ttu-id="cbf9b-120">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-120">Clears the `Listeners` collection for trace.</span></span>|  
|[<span data-ttu-id="cbf9b-121">\<remove></span><span class="sxs-lookup"><span data-stu-id="cbf9b-121">\<remove></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)|<span data-ttu-id="cbf9b-122">Quita un agente de escucha el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-122">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="cbf9b-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="cbf9b-123">Parent Elements</span></span>  
  
|<span data-ttu-id="cbf9b-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="cbf9b-124">Element</span></span>|<span data-ttu-id="cbf9b-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="cbf9b-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="cbf9b-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="cbf9b-127">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-127">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="cbf9b-128">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-128">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbf9b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cbf9b-129">Remarks</span></span>  
 <span data-ttu-id="cbf9b-130">El <xref:System.Diagnostics.Debug> y <xref:System.Diagnostics.Trace> clases comparten el mismo **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-130">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="cbf9b-131">Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase usa el mismo agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-131">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="cbf9b-132">Las clases de agente de escucha incluidas en .NET Framework se derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-132">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="cbf9b-133">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="cbf9b-133">Configuration File</span></span>  
 <span data-ttu-id="cbf9b-134">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-134">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cbf9b-135">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cbf9b-135">Example</span></span>  
 <span data-ttu-id="cbf9b-136">El ejemplo siguiente muestra cómo usar el  **\<los agentes de escucha >** elemento para agregar los agentes de escucha `MyListener` y `MyEventListener` a la **los agentes de escucha** colección.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-136">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> `MyListener` <span data-ttu-id="cbf9b-137">crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-137">creates a file called `MyListener.log` and writes the output to the file.</span></span> `MyEventListener` <span data-ttu-id="cbf9b-138">crea una entrada en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="cbf9b-138">creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"   
          type="System.Diagnostics.TextWriterTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"   
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,   
            system, version=1.0.3300.0, Culture=neutral,   
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cbf9b-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="cbf9b-139">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="cbf9b-140">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="cbf9b-140">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
