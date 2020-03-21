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
ms.openlocfilehash: 69f15cc9583b397017ac30a0c567914495867c18
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153326"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="64114-102">\<sharedListeners> Element</span><span class="sxs-lookup"><span data-stu-id="64114-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="64114-103">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="64114-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="64114-104">Estos agentes de escucha no reciben ningún seguimiento de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="64114-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="64114-105">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="64114-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="64114-106">**\<configuración>**</span><span class="sxs-lookup"><span data-stu-id="64114-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="64114-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="64114-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="64114-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span><span class="sxs-lookup"><span data-stu-id="64114-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64114-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64114-109">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="64114-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="64114-110">Attributes and Elements</span></span>  
 <span data-ttu-id="64114-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="64114-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="64114-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="64114-112">Attributes</span></span>  
 <span data-ttu-id="64114-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="64114-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="64114-114">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="64114-114">Child Elements</span></span>  
  
|<span data-ttu-id="64114-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="64114-115">Element</span></span>|<span data-ttu-id="64114-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="64114-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="64114-117">\<añadir></span><span class="sxs-lookup"><span data-stu-id="64114-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="64114-118">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="64114-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="64114-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="64114-119">Parent Elements</span></span>  
  
|<span data-ttu-id="64114-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="64114-120">Element</span></span>|<span data-ttu-id="64114-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="64114-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="64114-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="64114-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="64114-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="64114-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64114-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="64114-124">Remarks</span></span>  
 <span data-ttu-id="64114-125">Agregar un agente de escucha a la colección de agentes de escucha compartidos no lo convierte en un agente de escucha activo.</span><span class="sxs-lookup"><span data-stu-id="64114-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="64114-126">Todavía debe agregarse a un origen de seguimiento `Listeners` o un seguimiento agregándolo a la colección para ese elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="64114-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="64114-127">Las clases de agente de <xref:System.Diagnostics.TraceListener> escucha de .NET Framework se derivan de la clase.</span><span class="sxs-lookup"><span data-stu-id="64114-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="64114-128">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="64114-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64114-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="64114-129">Example</span></span>  
 <span data-ttu-id="64114-130">En el ejemplo siguiente `<sharedListeners>` se muestra cómo `console` utilizar `Listeners` el elemento <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace> para agregar el agente de escucha a la colección para las clases y.</span><span class="sxs-lookup"><span data-stu-id="64114-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="64114-131">El agente de escucha de seguimiento de consola <xref:System.Diagnostics.TraceSource> <xref:System.Diagnostics.Trace>escribe información de seguimiento en la consola a través de llamadas a o .</span><span class="sxs-lookup"><span data-stu-id="64114-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="64114-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="64114-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="64114-133">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="64114-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="64114-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="64114-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
