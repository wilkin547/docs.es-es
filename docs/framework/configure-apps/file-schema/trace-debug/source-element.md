---
description: 'Más información acerca de: <source> elemento'
title: <source> (Elemento)
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: acf510dd5813900f36ac431418d55bbc6c2f364a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750590"
---
# <a name="source-element"></a><span data-ttu-id="31a56-103">\<source> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="31a56-103">\<source> Element</span></span>

<span data-ttu-id="31a56-104">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-104">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="31a56-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31a56-105">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31a56-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31a56-106">Attributes and Elements</span></span>  

 <span data-ttu-id="31a56-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31a56-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31a56-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="31a56-108">Attributes</span></span>  
  
|<span data-ttu-id="31a56-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="31a56-109">Attribute</span></span>|<span data-ttu-id="31a56-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a56-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="31a56-111">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="31a56-111">Optional attribute.</span></span><br /><br /> <span data-ttu-id="31a56-112">Especifica el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-112">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="31a56-113">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="31a56-113">Optional attribute.</span></span><br /><br /> <span data-ttu-id="31a56-114">Especifica el nombre de una instancia del modificador de seguimiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31a56-114">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="31a56-115">Si no se identifica el modificador en un `<switches>` elemento, el valor especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="31a56-115">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="31a56-116">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="31a56-116">Optional attribute.</span></span><br /><br /> <span data-ttu-id="31a56-117">Especifica el tipo del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-117">Specifies the type of the trace switch.</span></span> <span data-ttu-id="31a56-118">Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="31a56-118">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="31a56-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="31a56-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="31a56-120">Especifica el valor de un atributo específico del origen de seguimiento identificado por el <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> método para ese origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-120">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="31a56-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31a56-121">Child Elements</span></span>  
  
|<span data-ttu-id="31a56-122">Elemento</span><span class="sxs-lookup"><span data-stu-id="31a56-122">Element</span></span>|<span data-ttu-id="31a56-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a56-123">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="31a56-124">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="31a56-124">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31a56-125">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31a56-125">Parent Elements</span></span>  
  
|<span data-ttu-id="31a56-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="31a56-126">Element</span></span>|<span data-ttu-id="31a56-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a56-127">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="31a56-128">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31a56-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="31a56-129">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-129">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="31a56-130">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31a56-130">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31a56-131">Observaciones</span><span class="sxs-lookup"><span data-stu-id="31a56-131">Remarks</span></span>  

 <span data-ttu-id="31a56-132">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31a56-132">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31a56-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31a56-133">Example</span></span>  

 <span data-ttu-id="31a56-134">En el ejemplo siguiente se muestra cómo utilizar el `<source>` elemento para agregar el origen de seguimiento `mySource` y establecer el nivel para el modificador de origen denominado `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="31a56-134">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="31a56-135">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="31a56-135">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31a56-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="31a56-136">See also</span></span>

- [<span data-ttu-id="31a56-137">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="31a56-137">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="31a56-138">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="31a56-138">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
