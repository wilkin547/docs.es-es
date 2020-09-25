---
title: <sharedListeners> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sharedListeners
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners
helpviewer_keywords:
- <sharedListeners> element
- listeners
- shared listeners
- trace listeners, <sharedListeners> element
- sharedListeners element
ms.assetid: de200534-19dd-4156-86cf-c50521802c4c
ms.openlocfilehash: 7e249e59423740b36e42f59fae8854412d01a0cc
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173853"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="6b62f-102">\<sharedListeners> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="6b62f-102">\<sharedListeners> Element</span></span>

<span data-ttu-id="6b62f-103">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6b62f-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="6b62f-104">Estos agentes de escucha no reciben ningún seguimiento de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6b62f-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="6b62f-105">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="6b62f-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="6b62f-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b62f-106">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6b62f-107">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6b62f-107">Attributes and Elements</span></span>  

 <span data-ttu-id="6b62f-108">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6b62f-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6b62f-109">Atributos</span><span class="sxs-lookup"><span data-stu-id="6b62f-109">Attributes</span></span>  

 <span data-ttu-id="6b62f-110">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6b62f-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6b62f-111">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6b62f-111">Child Elements</span></span>  
  
|<span data-ttu-id="6b62f-112">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b62f-112">Element</span></span>|<span data-ttu-id="6b62f-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b62f-113">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="6b62f-114">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="6b62f-114">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6b62f-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6b62f-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6b62f-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="6b62f-116">Element</span></span>|<span data-ttu-id="6b62f-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="6b62f-117">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="6b62f-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6b62f-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="6b62f-119">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="6b62f-119">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6b62f-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6b62f-120">Remarks</span></span>  

 <span data-ttu-id="6b62f-121">Agregar un agente de escucha a la colección de agentes de escucha compartidos no lo convierte en un agente de escucha activo.</span><span class="sxs-lookup"><span data-stu-id="6b62f-121">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="6b62f-122">Todavía se debe agregar a un origen de seguimiento o a un seguimiento agregándolo a la `Listeners` colección para ese elemento Trace.</span><span class="sxs-lookup"><span data-stu-id="6b62f-122">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="6b62f-123">Las clases de agente de escucha del .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="6b62f-123">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="6b62f-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6b62f-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b62f-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6b62f-125">Example</span></span>  

 <span data-ttu-id="6b62f-126">En el ejemplo siguiente se muestra cómo usar el `<sharedListeners>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para <xref:System.Diagnostics.TraceSource> las <xref:System.Diagnostics.Trace> clases y.</span><span class="sxs-lookup"><span data-stu-id="6b62f-126">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="6b62f-127">El agente de escucha de seguimiento de la consola escribe información de seguimiento en la consola a través de llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="6b62f-127">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sharedListeners>  
      <add name="console" type="System.Diagnostics.ConsoleTraceListener" >  
        <filter type="System.Diagnostics.EventTypeFilter"  
          initializeData="Warning" />  
      </add>  
    </sharedListeners>  
    <sources>  
      <source name="mySource" switchName="sourceSwitch"  >  
        <listeners>  
          <add name="console" />  
        </listeners>  
      </source>  
    </sources>  
    <switches>  
      <add name="sourceSwitch" value="Verbose"/>  
    </switches>  
    <trace>  
      <listeners>  
        <add name="console" />  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="6b62f-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6b62f-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="6b62f-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="6b62f-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="6b62f-130">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="6b62f-130">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
