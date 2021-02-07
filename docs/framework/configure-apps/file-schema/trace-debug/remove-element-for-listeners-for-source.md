---
description: 'Más información sobre: <remove> elemento para <listeners> para <source>'
title: <remove> (Elemento <listeners> ) para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 2f7a815fe97fda95d71bc2a5a1b8fdda7bc2a0ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750629"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="21aaa-103">\<remove> (Elemento \<listeners> ) para \<source></span><span class="sxs-lookup"><span data-stu-id="21aaa-103">\<remove> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="21aaa-104">Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="21aaa-104">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="21aaa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21aaa-105">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="21aaa-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="21aaa-106">Attributes and Elements</span></span>  

 <span data-ttu-id="21aaa-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="21aaa-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="21aaa-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="21aaa-108">Attributes</span></span>  
  
|<span data-ttu-id="21aaa-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="21aaa-109">Attribute</span></span>|<span data-ttu-id="21aaa-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="21aaa-110">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="21aaa-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="21aaa-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="21aaa-112">Nombre del agente de escucha que se va a quitar de la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="21aaa-112">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="21aaa-113">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="21aaa-113">Child Elements</span></span>  

 <span data-ttu-id="21aaa-114">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="21aaa-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="21aaa-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="21aaa-115">Parent Elements</span></span>  
  
|<span data-ttu-id="21aaa-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="21aaa-116">Element</span></span>|<span data-ttu-id="21aaa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="21aaa-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="21aaa-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="21aaa-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="21aaa-119">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="21aaa-119">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="21aaa-120">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="21aaa-120">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="21aaa-121">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="21aaa-121">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="21aaa-122">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="21aaa-122">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21aaa-123">Observaciones</span><span class="sxs-lookup"><span data-stu-id="21aaa-123">Remarks</span></span>  

 <span data-ttu-id="21aaa-124">El `<remove>` elemento quita un agente de escucha especificado de la `Listeners` colección para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="21aaa-124">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="21aaa-125">Puede quitar un elemento de la `Listeners` colección para un origen de seguimiento mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en la <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.</span><span class="sxs-lookup"><span data-stu-id="21aaa-125">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="21aaa-126">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21aaa-126">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21aaa-127">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="21aaa-127">Example</span></span>  

 <span data-ttu-id="21aaa-128">En el ejemplo siguiente se muestra cómo utilizar el `<remove>` elemento antes de usar el `<add>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="21aaa-128">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="21aaa-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="21aaa-129">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="21aaa-130">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="21aaa-130">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="21aaa-131">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="21aaa-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
