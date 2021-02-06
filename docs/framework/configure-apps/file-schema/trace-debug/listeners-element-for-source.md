---
description: 'Más información sobre: <listeners> elemento para <source>'
title: Elemento <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners
helpviewer_keywords:
- listeners element for <source>
- <listeners> element for <source>
ms.assetid: a2991f43-b4d3-4614-a8e7-da392de9697f
ms.openlocfilehash: 6b857d4b114366d268eec1859afc7f33cc5b04a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639648"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="34b7c-103">Elemento \<listeners> para \<source></span><span class="sxs-lookup"><span data-stu-id="34b7c-103">\<listeners> Element for \<source></span></span>

<span data-ttu-id="34b7c-104">Agrega o quita los agentes de escucha de la <xref:System.Diagnostics.TraceSource.Listeners%2A> colección para <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="34b7c-104">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="34b7c-105">Un agente de escucha dirige los resultados del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="34b7c-105">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="34b7c-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34b7c-106">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="34b7c-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="34b7c-107">Attributes and Elements</span></span>  

 <span data-ttu-id="34b7c-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="34b7c-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="34b7c-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="34b7c-109">Attributes</span></span>  

 <span data-ttu-id="34b7c-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="34b7c-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="34b7c-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="34b7c-111">Child Elements</span></span>  
  
|<span data-ttu-id="34b7c-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="34b7c-112">Element</span></span>|<span data-ttu-id="34b7c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="34b7c-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="34b7c-114">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="34b7c-114">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="34b7c-115">Quita un agente de escucha de la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="34b7c-115">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="34b7c-116">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34b7c-116">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="34b7c-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="34b7c-117">Parent Elements</span></span>  
  
|<span data-ttu-id="34b7c-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="34b7c-118">Element</span></span>|<span data-ttu-id="34b7c-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="34b7c-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="34b7c-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="34b7c-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="34b7c-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34b7c-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="34b7c-122">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34b7c-122">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="34b7c-123">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="34b7c-123">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34b7c-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="34b7c-124">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="34b7c-125">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="34b7c-125">Configuration File</span></span>  

 <span data-ttu-id="34b7c-126">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="34b7c-126">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34b7c-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="34b7c-127">Example</span></span>  

 <span data-ttu-id="34b7c-128">En el ejemplo siguiente se muestra cómo usar el `<listeners>` elemento para agregar un agente de escucha de seguimiento de la consola al `mySource` origen y quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="34b7c-128">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="34b7c-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="34b7c-129">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="34b7c-130">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="34b7c-130">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="34b7c-131">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="34b7c-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
