---
title: <source> (Elemento)
ms.date: 09/29/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source
- http://schemas.microsoft.com/.NetConfiguration/v2.0#source
helpviewer_keywords:
- <source> element
- source element
ms.openlocfilehash: e9c6a06ca9e481ecc2277e1d1ea76a0b99edb158
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173827"
---
# <a name="source-element"></a><span data-ttu-id="bc6fd-102">\<source> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="bc6fd-102">\<source> Element</span></span>

<span data-ttu-id="bc6fd-103">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-103">Specifies a trace source that initiates tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<source>**

## <a name="syntax"></a><span data-ttu-id="bc6fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bc6fd-104">Syntax</span></span>  
  
```xml  
<source>
  <listeners>...</listeners>  
</source>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bc6fd-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="bc6fd-105">Attributes and Elements</span></span>  

 <span data-ttu-id="bc6fd-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bc6fd-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="bc6fd-107">Attributes</span></span>  
  
|<span data-ttu-id="bc6fd-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="bc6fd-108">Attribute</span></span>|<span data-ttu-id="bc6fd-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc6fd-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="bc6fd-110">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-110">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc6fd-111">Especifica el nombre del origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-111">Specifies the name of the trace source.</span></span>|  
|`switchName`|<span data-ttu-id="bc6fd-112">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-112">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc6fd-113">Especifica el nombre de una instancia del modificador de seguimiento en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-113">Specifies the name of a trace switch instance in the application.</span></span> <span data-ttu-id="bc6fd-114">Si no se identifica el modificador en un `<switches>` elemento, el valor especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-114">If the switch is not identified in a `<switches>` element, the value specifies the level for the switch.</span></span>|  
|`switchType`|<span data-ttu-id="bc6fd-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc6fd-116">Especifica el tipo del modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-116">Specifies the type of the trace switch.</span></span> <span data-ttu-id="bc6fd-117">Si está presente, el tipo debe ser un nombre de clase válido y no puede ser una cadena vacía.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-117">If present, the type must be a valid class name and cannot be an empty string.</span></span>|  
|`extraAttribute`|<span data-ttu-id="bc6fd-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="bc6fd-119">Especifica el valor de un atributo específico del origen de seguimiento identificado por el <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> método para ese origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-119">Specifies the value for a trace source-specific attribute identified by the <xref:System.Diagnostics.TraceSource.GetSupportedAttributes%2A> method for that trace source.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bc6fd-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="bc6fd-120">Child Elements</span></span>  
  
|<span data-ttu-id="bc6fd-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc6fd-121">Element</span></span>|<span data-ttu-id="bc6fd-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc6fd-122">Description</span></span>|  
|-------------|-----------------|  
|[\<listeners>](listeners-element-for-source.md)|<span data-ttu-id="bc6fd-123">Contiene agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-123">Contains listeners that collect, store, and route messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="bc6fd-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="bc6fd-124">Parent Elements</span></span>  
  
|<span data-ttu-id="bc6fd-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="bc6fd-125">Element</span></span>|<span data-ttu-id="bc6fd-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="bc6fd-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="bc6fd-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="bc6fd-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="bc6fd-129">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-129">Contains trace sources that initiate tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bc6fd-130">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bc6fd-130">Remarks</span></span>  

 <span data-ttu-id="bc6fd-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc6fd-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="bc6fd-132">Example</span></span>  

 <span data-ttu-id="bc6fd-133">En el ejemplo siguiente se muestra cómo utilizar el `<source>` elemento para agregar el origen de seguimiento `mySource` y establecer el nivel para el modificador de origen denominado `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="bc6fd-133">The following example shows how to use the `<source>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="bc6fd-134">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="bc6fd-134">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="bc6fd-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bc6fd-135">See also</span></span>

- [<span data-ttu-id="bc6fd-136">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="bc6fd-136">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="bc6fd-137">Modificadores de seguimiento</span><span class="sxs-lookup"><span data-stu-id="bc6fd-137">Trace Switches</span></span>](../../../debug-trace-profile/trace-switches.md)
