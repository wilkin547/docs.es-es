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
ms.openlocfilehash: b419ecf451b79808e545525c7b8761175f390200
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699303"
---
# <a name="sharedlisteners-element"></a><span data-ttu-id="46dfc-102">\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="46dfc-102">\<sharedListeners> Element</span></span>
<span data-ttu-id="46dfc-103">Contiene los agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="46dfc-103">Contains listeners that any source or trace element can reference.</span></span>  <span data-ttu-id="46dfc-104">Estos agentes de escucha no reciben ningún seguimiento de forma predeterminada y no es posible recuperar estos agentes de escucha en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="46dfc-104">These listeners do not receive any traces by default, and it is not possible to retrieve these listeners at run time.</span></span> <span data-ttu-id="46dfc-105">Los agentes de escucha identificados como agentes de escucha compartidos se pueden agregar a orígenes o seguimientos por nombre.</span><span class="sxs-lookup"><span data-stu-id="46dfc-105">Listeners identified as shared listeners can be added to sources or traces by name.</span></span>  
  
[<span data-ttu-id="46dfc-106"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="46dfc-106">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="46dfc-107">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="46dfc-107">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="46dfc-108">&nbsp;&nbsp;&nbsp;&nbsp; **\<sharedListeners >**</span><span class="sxs-lookup"><span data-stu-id="46dfc-108">&nbsp;&nbsp;&nbsp;&nbsp;**\<sharedListeners>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46dfc-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="46dfc-109">Syntax</span></span>  
  
```xml  
<sharedListeners>   
  <add>...</add>  
</sharedListeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="46dfc-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="46dfc-110">Attributes and Elements</span></span>  
 <span data-ttu-id="46dfc-111">En las secciones siguientes se describen atributos, elementos secundarios y elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="46dfc-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="46dfc-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="46dfc-112">Attributes</span></span>  
 <span data-ttu-id="46dfc-113">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="46dfc-113">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="46dfc-114">Elemento secundario</span><span class="sxs-lookup"><span data-stu-id="46dfc-114">Child Elements</span></span>  
  
|<span data-ttu-id="46dfc-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="46dfc-115">Element</span></span>|<span data-ttu-id="46dfc-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="46dfc-116">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="46dfc-117">\<add></span><span class="sxs-lookup"><span data-stu-id="46dfc-117">\<add></span></span>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="46dfc-118">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="46dfc-118">Adds a listener to the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="46dfc-119">Elemento principal</span><span class="sxs-lookup"><span data-stu-id="46dfc-119">Parent Elements</span></span>  
  
|<span data-ttu-id="46dfc-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="46dfc-120">Element</span></span>|<span data-ttu-id="46dfc-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="46dfc-121">Description</span></span>|  
|-------------|-----------------|  
|`Configuration`|<span data-ttu-id="46dfc-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="46dfc-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="46dfc-123">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="46dfc-123">Specifies the root element for the ASP.NET configuration section.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="46dfc-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="46dfc-124">Remarks</span></span>  
 <span data-ttu-id="46dfc-125">Agregar un agente de escucha a la colección de agentes de escucha compartidos no lo convierte en un agente de escucha activo.</span><span class="sxs-lookup"><span data-stu-id="46dfc-125">Adding a listener to the shared listeners collection does not make it an active listener.</span></span> <span data-ttu-id="46dfc-126">Todavía se debe agregar a un origen de seguimiento o a un seguimiento agregándolo a la colección de `Listeners` de ese elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="46dfc-126">It must still be added to a trace source or a trace by adding it to the `Listeners` collection for that trace element.</span></span> <span data-ttu-id="46dfc-127">Las clases de agente de escucha del .NET Framework derivan de la clase <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="46dfc-127">The listener classes in the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="46dfc-128">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="46dfc-128">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46dfc-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="46dfc-129">Example</span></span>  
 <span data-ttu-id="46dfc-130">En el ejemplo siguiente se muestra cómo usar el elemento `<sharedListeners>` para agregar el agente de escucha `console` a la colección de `Listeners` para las clases <xref:System.Diagnostics.TraceSource> y <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="46dfc-130">The following example shows how to use the `<sharedListeners>` element to add the listener `console` to the `Listeners` collection for both the <xref:System.Diagnostics.TraceSource> and <xref:System.Diagnostics.Trace> classes.</span></span> <span data-ttu-id="46dfc-131">El agente de escucha de seguimiento de la consola escribe información de seguimiento en la consola a través de llamadas a <xref:System.Diagnostics.TraceSource> o <xref:System.Diagnostics.Trace>.</span><span class="sxs-lookup"><span data-stu-id="46dfc-131">The console trace listener writes trace information to the console through calls to either <xref:System.Diagnostics.TraceSource> or <xref:System.Diagnostics.Trace>.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="46dfc-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="46dfc-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="46dfc-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="46dfc-133">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="46dfc-134">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="46dfc-134">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
