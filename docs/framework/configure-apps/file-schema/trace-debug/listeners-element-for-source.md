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
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153417"
---
# <a name="listeners-element-for-source"></a><span data-ttu-id="79ace-102">Elemento \<listeners> para \<source></span><span class="sxs-lookup"><span data-stu-id="79ace-102">\<listeners> Element for \<source></span></span>
<span data-ttu-id="79ace-103">Agrega o quita los agentes de escucha de la <xref:System.Diagnostics.TraceSource.Listeners%2A> colección para <xref:System.Diagnostics.TraceSource> .</span><span class="sxs-lookup"><span data-stu-id="79ace-103">Adds or removes listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A> collection for a <xref:System.Diagnostics.TraceSource>.</span></span> <span data-ttu-id="79ace-104">Un agente de escucha dirige los resultados del seguimiento a un destino adecuado, como un registro, una ventana o un archivo de texto.</span><span class="sxs-lookup"><span data-stu-id="79ace-104">A listener directs the tracing output to an appropriate target, such as a log, window, or text file.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**  
  
## <a name="syntax"></a><span data-ttu-id="79ace-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79ace-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <remove ... />  
  <clear/>  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="79ace-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="79ace-106">Attributes and Elements</span></span>  
 <span data-ttu-id="79ace-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="79ace-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="79ace-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="79ace-108">Attributes</span></span>  
 <span data-ttu-id="79ace-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="79ace-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="79ace-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="79ace-110">Child Elements</span></span>  
  
|<span data-ttu-id="79ace-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="79ace-111">Element</span></span>|<span data-ttu-id="79ace-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ace-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-source.md)|<span data-ttu-id="79ace-113">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="79ace-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-source.md)|<span data-ttu-id="79ace-114">Quita un agente de escucha de la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="79ace-114">Removes a listener from the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-source.md)|<span data-ttu-id="79ace-115">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="79ace-115">Clears the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="79ace-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="79ace-116">Parent Elements</span></span>  
  
|<span data-ttu-id="79ace-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="79ace-117">Element</span></span>|<span data-ttu-id="79ace-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="79ace-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="79ace-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="79ace-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="79ace-120">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="79ace-120">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="79ace-121">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="79ace-121">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="79ace-122">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="79ace-122">Specifies a trace source that initiates tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79ace-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79ace-123">Remarks</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="79ace-124">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="79ace-124">Configuration File</span></span>  
 <span data-ttu-id="79ace-125">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="79ace-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79ace-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="79ace-126">Example</span></span>  
 <span data-ttu-id="79ace-127">En el ejemplo siguiente se muestra cómo usar el `<listeners>` elemento para agregar un agente de escucha de seguimiento de la consola al `mySource` origen y quitar el agente de escucha de seguimiento predeterminado.</span><span class="sxs-lookup"><span data-stu-id="79ace-127">The following example shows how to use the `<listeners>` element to add a console trace listener to the `mySource` source and to remove the default trace listener.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="79ace-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="79ace-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="79ace-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="79ace-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="79ace-130">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="79ace-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
