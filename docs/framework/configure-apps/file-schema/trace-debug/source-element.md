---
title: <source> (Elemento)
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: 417722ce2f3865350158413307495e3ab435d386
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153300"
---
# <a name="source-element"></a><span data-ttu-id="d0d4b-102">\<fuente> Elemento</span><span class="sxs-lookup"><span data-stu-id="d0d4b-102">\<source> Element</span></span>
<span data-ttu-id="d0d4b-103">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-103">Specifies a trace source that initiates tracing messages.</span></span>  

<span data-ttu-id="d0d4b-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="d0d4b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="d0d4b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="d0d4b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="d0d4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="d0d4b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="d0d4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<fuente>**</span><span class="sxs-lookup"><span data-stu-id="d0d4b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**</span></span>

## <a name="syntax"></a><span data-ttu-id="d0d4b-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0d4b-108">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d0d4b-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d0d4b-109">Attributes and Elements</span></span>  
 <span data-ttu-id="d0d4b-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d0d4b-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="d0d4b-111">Attributes</span></span>  
  
|<span data-ttu-id="d0d4b-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="d0d4b-112">Attribute</span></span>|<span data-ttu-id="d0d4b-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0d4b-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="d0d4b-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d0d4b-115">Especifica el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-115">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="d0d4b-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d0d4b-117">Especifica el nombre de una instancia de modificador de seguimiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-117">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="d0d4b-118">Si el modificador no `<switches>` se identifica en un elemento, el valor especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-118">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="d0d4b-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d0d4b-120">Especifica el tipo del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-120">Specifies the type of the trace switch.</span></span> <span data-ttu-id="d0d4b-121">Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-121">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="d0d4b-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d0d4b-123">Especifica el valor de un atributo específico <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> del origen de seguimiento identificado por el método para ese origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-123">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d0d4b-124">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d0d4b-124">Child Elements</span></span>  
  
|<span data-ttu-id="d0d4b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0d4b-125">Element</span></span>|<span data-ttu-id="d0d4b-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0d4b-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d0d4b-127">\<oyentes></span><span class="sxs-lookup"><span data-stu-id="d0d4b-127">\<listeners></span></span>](listeners-element-for-source.md)|<span data-ttu-id="d0d4b-128">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-128">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d0d4b-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d0d4b-129">Parent Elements</span></span>  
  
|<span data-ttu-id="d0d4b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="d0d4b-130">Element</span></span>|<span data-ttu-id="d0d4b-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="d0d4b-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d0d4b-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d0d4b-133">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d0d4b-134">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-134">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0d4b-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d0d4b-135">Remarks</span></span>  
 <span data-ttu-id="d0d4b-136">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-136">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d0d4b-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d0d4b-137">Example</span></span>  
 <span data-ttu-id="d0d4b-138">En el ejemplo siguiente `<source>` se muestra cómo `mySource` utilizar el elemento para agregar `sourceSwitch`el origen de seguimiento y establecer el nivel para el modificador de origen denominado .</span><span class="sxs-lookup"><span data-stu-id="d0d4b-138">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="d0d4b-139">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="d0d4b-139">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d0d4b-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d0d4b-140">See also</span></span>

- [<span data-ttu-id="d0d4b-141">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="d0d4b-141">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="d0d4b-142">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d0d4b-142">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
