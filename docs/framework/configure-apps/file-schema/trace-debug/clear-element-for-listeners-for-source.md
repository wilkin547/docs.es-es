---
description: 'Más información sobre: <clear> elemento para <listeners> para <source>'
title: <clear> (Elemento <listeners> ) para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 731c23c73b6d149bd37672e91eca1d70431b2789
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639710"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="3c618-103">\<clear> (Elemento \<listeners> ) para \<source></span><span class="sxs-lookup"><span data-stu-id="3c618-103">\<clear> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="3c618-104">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c618-104">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="3c618-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c618-105">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3c618-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3c618-106">Attributes and Elements</span></span>  

 <span data-ttu-id="3c618-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3c618-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3c618-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="3c618-108">Attributes</span></span>  

 <span data-ttu-id="3c618-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c618-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="3c618-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3c618-110">Child Elements</span></span>  

 <span data-ttu-id="3c618-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="3c618-111">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="3c618-112">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3c618-112">Parent Elements</span></span>  
  
|<span data-ttu-id="3c618-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="3c618-113">Element</span></span>|<span data-ttu-id="3c618-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c618-114">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3c618-115">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3c618-115">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3c618-116">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c618-116">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="3c618-117">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c618-117">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="3c618-118">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3c618-118">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="3c618-119">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="3c618-119">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3c618-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3c618-120">Remarks</span></span>  

 <span data-ttu-id="3c618-121">El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para un origen de seguimiento, incluido <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="3c618-121">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="3c618-122">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="3c618-122">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="3c618-123">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3c618-123">Configuration File</span></span>  

 <span data-ttu-id="3c618-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3c618-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c618-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3c618-125">Example</span></span>  

 <span data-ttu-id="3c618-126">En el ejemplo siguiente se muestra cómo utilizar el `<clear>` elemento antes de usar los `<add>` elementos para agregar los agentes `console` de escucha y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="3c618-126">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3c618-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c618-127">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="3c618-128">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="3c618-128">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3c618-129">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3c618-129">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
