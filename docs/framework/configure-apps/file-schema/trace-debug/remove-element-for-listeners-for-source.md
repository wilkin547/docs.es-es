---
title: '&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: cc6772e7a9b98f09df21fd1acf24f578b66ae51e
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32754280"
---
# <a name="ltremovegt-element-for-ltlistenersgt-for-ltsourcegt"></a><span data-ttu-id="22794-102">&lt;quitar&gt; (elemento) para &lt;los agentes de escucha&gt; para &lt;origen&gt;</span><span class="sxs-lookup"><span data-stu-id="22794-102">&lt;remove&gt; Element for &lt;listeners&gt; for &lt;source&gt;</span></span>
<span data-ttu-id="22794-103">Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22794-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="22794-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="22794-104">\<configuration></span></span>  
<span data-ttu-id="22794-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="22794-105">\<system.diagnostics></span></span>  
<span data-ttu-id="22794-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="22794-106">\<sources></span></span>  
<span data-ttu-id="22794-107">\<origen ></span><span class="sxs-lookup"><span data-stu-id="22794-107">\<source></span></span>  
<span data-ttu-id="22794-108">\<los agentes de escucha ></span><span class="sxs-lookup"><span data-stu-id="22794-108">\<listeners></span></span>  
<span data-ttu-id="22794-109">\<Quitar ></span><span class="sxs-lookup"><span data-stu-id="22794-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22794-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="22794-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="22794-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="22794-111">Attributes and Elements</span></span>  
 <span data-ttu-id="22794-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="22794-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="22794-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="22794-113">Attributes</span></span>  
  
|<span data-ttu-id="22794-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="22794-114">Attribute</span></span>|<span data-ttu-id="22794-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="22794-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="22794-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="22794-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="22794-117">El nombre del agente de escucha que se quitará el `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="22794-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="22794-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="22794-118">Child Elements</span></span>  
 <span data-ttu-id="22794-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="22794-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="22794-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="22794-120">Parent Elements</span></span>  
  
|<span data-ttu-id="22794-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="22794-121">Element</span></span>|<span data-ttu-id="22794-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="22794-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="22794-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22794-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="22794-124">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22794-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="22794-125">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22794-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="22794-126">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22794-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="22794-127">Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="22794-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22794-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="22794-128">Remarks</span></span>  
 <span data-ttu-id="22794-129">El `<remove>` elemento quita un agente de escucha especificado desde el `Listeners` colección para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="22794-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="22794-130">Puede quitar un elemento de la `Listeners` colección para un origen de seguimiento mediante programación mediante una llamada a la <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en el <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.</span><span class="sxs-lookup"><span data-stu-id="22794-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="22794-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de aplicación.</span><span class="sxs-lookup"><span data-stu-id="22794-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22794-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22794-132">Example</span></span>  
 <span data-ttu-id="22794-133">En el ejemplo siguiente se muestra cómo utilizar el `<remove>` elemento antes de usar el `<add>` elemento que se va a agregar el agente de escucha `console` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="22794-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"   
         switchType="System.Diagnostics.SourceSwitch" >  
         <listeners>  
           <remove name="Default"/>  
           <add name="console"   
             type="System.Diagnostics.ConsoleTraceListener" />  
         </listeners>  
      </source>  
    </sources>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a><span data-ttu-id="22794-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="22794-134">See Also</span></span>  
 <xref:System.Diagnostics.TraceSource.Listeners%2A>  
 <xref:System.Diagnostics.TraceSource>  
 [<span data-ttu-id="22794-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="22794-135">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [<span data-ttu-id="22794-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="22794-136">\<clear></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/clear-element-for-listeners-for-source.md)  
 [<span data-ttu-id="22794-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="22794-137">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
