---
title: <remove> (Elemento <listeners> ) para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/remove
helpviewer_keywords:
- remove element for <listeners> for <source>
- <remove> element for <listeners> for <source>
ms.assetid: 3ff6b578-273d-407f-b07f-8251f1f9f5d0
ms.openlocfilehash: 53ba773ea1cb31955e59c1f57e1c0cc807227402
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173878"
---
# <a name="remove-element-for-listeners-for-source"></a><span data-ttu-id="05101-102">\<remove> (Elemento \<listeners> ) para \<source></span><span class="sxs-lookup"><span data-stu-id="05101-102">\<remove> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="05101-103">Quita un agente de escucha de la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="05101-103">Removes a listener from the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<remove>**

## <a name="syntax"></a><span data-ttu-id="05101-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="05101-104">Syntax</span></span>  
  
```xml  
<remove name="listenerName" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="05101-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="05101-105">Attributes and Elements</span></span>  

 <span data-ttu-id="05101-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="05101-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="05101-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="05101-107">Attributes</span></span>  
  
|<span data-ttu-id="05101-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="05101-108">Attribute</span></span>|<span data-ttu-id="05101-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="05101-109">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="05101-110">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="05101-110">Required attribute.</span></span><br /><br /> <span data-ttu-id="05101-111">Nombre del agente de escucha que se va a quitar de la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="05101-111">The name of the listener to remove from the `Listeners` collection.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="05101-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="05101-112">Child Elements</span></span>  

 <span data-ttu-id="05101-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="05101-113">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="05101-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="05101-114">Parent Elements</span></span>  
  
|<span data-ttu-id="05101-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="05101-115">Element</span></span>|<span data-ttu-id="05101-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="05101-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="05101-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="05101-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="05101-118">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="05101-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="05101-119">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="05101-119">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="05101-120">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="05101-120">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="05101-121">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="05101-121">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="05101-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="05101-122">Remarks</span></span>  

 <span data-ttu-id="05101-123">El `<remove>` elemento quita un agente de escucha especificado de la `Listeners` colección para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="05101-123">The `<remove>` element removes a specified listener from the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="05101-124">Puede quitar un elemento de la `Listeners` colección para un origen de seguimiento mediante programación llamando al <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> método en la <xref:System.Diagnostics.TraceSource.Listeners%2A> propiedad de la <xref:System.Diagnostics.TraceSource> instancia.</span><span class="sxs-lookup"><span data-stu-id="05101-124">You can remove an element from the `Listeners` collection for a trace source programmatically by calling the <xref:System.Diagnostics.TraceListenerCollection.Remove%2A> method on the <xref:System.Diagnostics.TraceSource.Listeners%2A> property of the <xref:System.Diagnostics.TraceSource> instance.</span></span>  
  
 <span data-ttu-id="05101-125">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="05101-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="05101-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="05101-126">Example</span></span>  

 <span data-ttu-id="05101-127">En el ejemplo siguiente se muestra cómo utilizar el `<remove>` elemento antes de usar el `<add>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="05101-127">The following example shows how to use the `<remove>` element before using the `<add>` element to add the listener `console` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="05101-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="05101-128">See also</span></span>

- <xref:System.Diagnostics.TraceSource.Listeners%2A>
- <xref:System.Diagnostics.TraceSource>
- [<span data-ttu-id="05101-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="05101-129">Trace and Debug Settings Schema</span></span>](index.md)
- [\<clear>](clear-element-for-listeners-for-source.md)
- [<span data-ttu-id="05101-130">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="05101-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
