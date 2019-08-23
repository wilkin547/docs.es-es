---
title: <remove>(Elemento <listeners> ) para<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: edd27dd262004aead7db4d81db8ecab0e831dac1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69926990"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="b0701-102">\<quitar > elemento de \<los agentes de escucha \<> para el origen ></span><span class="sxs-lookup"><span data-stu-id="b0701-102">\<remove> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="b0701-103">Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b0701-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="b0701-104">\<configuration></span></span>  
<span data-ttu-id="b0701-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="b0701-105">\<system.diagnostics></span></span>  
<span data-ttu-id="b0701-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="b0701-106">\<sources></span></span>  
<span data-ttu-id="b0701-107">\<> de origen</span><span class="sxs-lookup"><span data-stu-id="b0701-107">\<source></span></span>  
<span data-ttu-id="b0701-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="b0701-108">\<listeners></span></span>  
<span data-ttu-id="b0701-109">\<remove></span><span class="sxs-lookup"><span data-stu-id="b0701-109">\<remove></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0701-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0701-110">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0701-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0701-111">Attributes and Elements</span></span>  
 <span data-ttu-id="b0701-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0701-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0701-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0701-113">Attributes</span></span>  
  
|<span data-ttu-id="b0701-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0701-114">Attribute</span></span>|<span data-ttu-id="b0701-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0701-115">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="b0701-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="b0701-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="b0701-117">Nombre del agente de escucha que se va a quitar `Listeners` de la colección.</span><span class="sxs-lookup"><span data-stu-id="b0701-117">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b0701-118">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0701-118">Child Elements</span></span>  
 <span data-ttu-id="b0701-119">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0701-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b0701-120">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0701-120">Parent Elements</span></span>  
  
|<span data-ttu-id="b0701-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0701-121">Element</span></span>|<span data-ttu-id="b0701-122">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="b0701-122">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0701-123">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0701-123">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b0701-124">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="b0701-125">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-125">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="b0701-126">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-126">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="b0701-127">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b0701-127">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0701-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b0701-128">Remarks</span></span>  
 <span data-ttu-id="b0701-129">El `<remove>` elemento quita un agente de escucha especificado de `Listeners` la colección para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-129">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="b0701-130">Puede quitar un elemento de `Listeners` la colección para un origen de seguimiento mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en la <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.</span><span class="sxs-lookup"><span data-stu-id="b0701-130">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="b0701-131">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0701-131">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0701-132">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0701-132">Example</span></span>  
 <span data-ttu-id="b0701-133">En el ejemplo siguiente se muestra cómo utilizar `<remove>` el elemento antes de `<add>` usar el elemento `console` para agregar el agente de `Listeners` escucha a la colección para `TraceSourceApp`el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0701-133">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b0701-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0701-134">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="b0701-135">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="b0701-135">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="b0701-136">\<clear></span><span class="sxs-lookup"><span data-stu-id="b0701-136">\<clear></span></span>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="b0701-137">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="b0701-137">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
