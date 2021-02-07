---
description: 'Más información acerca de: <sharedListeners> elemento'
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
ms.openlocfilehash: 904648754c99464e1109a04a5a19b52ec1a1cace
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750564"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="84261-103">\<sharedListeners> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="84261-103">\<sharedListeners> Element</span></span>

<span data-ttu-id="84261-104">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="84261-104">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="84261-105">Estos agentes de escucha no reciben ningún seguimiento de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="84261-105">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="84261-106">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="84261-106">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[**\<configuration>**](../configuration-element.md)  
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)  
&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**  
  
## <a name="syntax"></a><span data-ttu-id="84261-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="84261-107">Syntax</span></span>  
  
```xml  
<sharedListeners>
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="84261-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="84261-108">Attributes and Elements</span></span>  

 <span data-ttu-id="84261-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="84261-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="84261-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="84261-110">Attributes</span></span>  

 <span data-ttu-id="84261-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="84261-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="84261-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="84261-112">Child Elements</span></span>  
  
|<span data-ttu-id="84261-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="84261-113">Element</span></span>|<span data-ttu-id="84261-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="84261-114">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="84261-115">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="84261-115">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="84261-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="84261-116">Parent Elements</span></span>  
  
|<span data-ttu-id="84261-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="84261-117">Element</span></span>|<span data-ttu-id="84261-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="84261-118">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="84261-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84261-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="84261-120">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="84261-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84261-121">Observaciones</span><span class="sxs-lookup"><span data-stu-id="84261-121">Remarks</span></span>  

 <span data-ttu-id="84261-122">Agregar un agente de escucha a la colección de agentes de escucha compartidos no lo convierte en un agente de escucha activo.</span><span class="sxs-lookup"><span data-stu-id="84261-122">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="84261-123">Todavía se debe agregar a un origen de seguimiento o a un seguimiento agregándolo a la `Listeners` colección para ese elemento Trace.</span><span class="sxs-lookup"><span data-stu-id="84261-123">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="84261-124">Las clases de agente de escucha del .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="84261-124">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="84261-125">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="84261-125">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="84261-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="84261-126">Example</span></span>  

 <span data-ttu-id="84261-127">En el ejemplo siguiente se muestra cómo usar el `<sharedListeners>` elemento para agregar el agente `console` de escucha a la `Listeners` colección para <xref:System.Diagnostics.TraceSource> las <xref:System.Diagnostics.Trace> clases y.</span><span class="sxs-lookup"><span data-stu-id="84261-127">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="84261-128">El agente de escucha de seguimiento de la consola escribe información de seguimiento en la consola a través de llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace> .</span><span class="sxs-lookup"><span data-stu-id="84261-128">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="84261-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="84261-129">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="84261-130">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="84261-130">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="84261-131">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="84261-131">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
