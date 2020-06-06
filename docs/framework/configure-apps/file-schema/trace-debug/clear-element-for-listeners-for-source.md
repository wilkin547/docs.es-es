---
title: <clear>(Elemento <listeners> ) para<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/clear
helpviewer_keywords:
- <clear> element for <listeners> for <source>
- clear element for <listeners> for <source>
ms.assetid: 76796bb2-9c0b-4526-8135-8bf18b16d8d9
ms.openlocfilehash: 7f9ddd93d27c3619119702c82c9e8752dab1af7b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153586"
---
# <a name="clear-element-for-listeners-for-source"></a><span data-ttu-id="f7002-102">\<clear>(Elemento \<listeners> ) para\<source></span><span class="sxs-lookup"><span data-stu-id="f7002-102">\<clear> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="f7002-103">Borra la colección `Listeners` de un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f7002-103">Clears the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<clear>**

## <a name="syntax"></a><span data-ttu-id="f7002-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7002-104">Syntax</span></span>  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f7002-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="f7002-105">Attributes and Elements</span></span>  
 <span data-ttu-id="f7002-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="f7002-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f7002-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="f7002-107">Attributes</span></span>  
 <span data-ttu-id="f7002-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7002-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="f7002-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="f7002-109">Child Elements</span></span>  
 <span data-ttu-id="f7002-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="f7002-110">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f7002-111">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="f7002-111">Parent Elements</span></span>  
  
|<span data-ttu-id="f7002-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="f7002-112">Element</span></span>|<span data-ttu-id="f7002-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f7002-113">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="f7002-114">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7002-114">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="f7002-115">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f7002-115">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="f7002-116">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f7002-116">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="f7002-117">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f7002-117">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="f7002-118">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="f7002-118">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f7002-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7002-119">Remarks</span></span>  
 <span data-ttu-id="f7002-120">El `<clear>` elemento quita todos los agentes de escucha de la `Listeners` colección para un origen de seguimiento, incluido <xref:System.Diagnostics.DefaultTraceListener> .</span><span class="sxs-lookup"><span data-stu-id="f7002-120">The `<clear>` element removes all listeners from the `Listeners` collection for a trace source, including the <xref:System.Diagnostics.DefaultTraceListener>.</span></span> <span data-ttu-id="f7002-121">Puede usar el `<clear>` elemento antes de usar el `<add>` elemento para estar seguro de que no hay ningún otro agente de escucha activo en la colección.</span><span class="sxs-lookup"><span data-stu-id="f7002-121">You can use the `<clear>` element before using the `<add>` element to be certain there are no other active listeners in the collection.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="f7002-122">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="f7002-122">Configuration File</span></span>  
 <span data-ttu-id="f7002-123">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7002-123">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f7002-124">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f7002-124">Example</span></span>  
 <span data-ttu-id="f7002-125">En el ejemplo siguiente se muestra cómo utilizar el `<clear>` elemento antes de usar los `<add>` elementos para agregar los agentes `console` de escucha y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="f7002-125">The following example shows how to use the `<clear>` element before using the `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f7002-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f7002-126">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="f7002-127">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="f7002-127">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="f7002-128">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="f7002-128">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
