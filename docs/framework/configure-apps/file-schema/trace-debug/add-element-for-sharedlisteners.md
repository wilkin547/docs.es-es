---
description: 'Más información sobre: <add> elemento para <sharedListeners>'
title: Elemento <add> para <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: df3348fa0cbb357b2ceeb5d9db940a1ae3ae102c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726083"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="687b3-103">Elemento \<add> para \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="687b3-103">\<add> Element for \<sharedListeners></span></span>

<span data-ttu-id="687b3-104">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="687b3-104">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="687b3-105">`sharedListeners` es una colección de agentes de escucha a los que [\<source>](source-element.md) [\<trace>](trace-element.md) puede hacer referencia cualquier o.</span><span class="sxs-lookup"><span data-stu-id="687b3-105">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="687b3-106">De forma predeterminada, los agentes de escucha de la `sharedListeners` colección no se colocan en una `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="687b3-106">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="687b3-107">Se deben agregar por nombre a [\<source>](source-element.md) o [\<trace>](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="687b3-107">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="687b3-108">No es posible obtener los agentes de escucha de la `sharedListeners` colección en el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="687b3-108">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="687b3-109">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="687b3-109">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="687b3-110">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="687b3-110">Attributes and Elements</span></span>  

 <span data-ttu-id="687b3-111">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="687b3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="687b3-112">Atributos</span><span class="sxs-lookup"><span data-stu-id="687b3-112">Attributes</span></span>  
  
|<span data-ttu-id="687b3-113">Atributo</span><span class="sxs-lookup"><span data-stu-id="687b3-113">Attribute</span></span>|<span data-ttu-id="687b3-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="687b3-114">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="687b3-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="687b3-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="687b3-116">Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a una `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="687b3-116">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="687b3-117">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="687b3-117">Required attribute.</span></span><br /><br /> <span data-ttu-id="687b3-118">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="687b3-118">Specifies the type of the listener.</span></span> <span data-ttu-id="687b3-119">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="687b3-119">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="687b3-120">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="687b3-120">Optional attribute.</span></span><br /><br /> <span data-ttu-id="687b3-121">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="687b3-121">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="687b3-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="687b3-122">Optional attribute.</span></span><br/><br/><span data-ttu-id="687b3-123">Representación de cadena de uno o más <xref:System.Diagnostics.TraceOptions> miembros de la enumeración que indica los datos que se van a escribir en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="687b3-123">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="687b3-124">Varios elementos se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="687b3-124">Multiple items are separated by commas.</span></span> <span data-ttu-id="687b3-125">El valor predeterminado es "none".</span><span class="sxs-lookup"><span data-stu-id="687b3-125">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="687b3-126">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="687b3-126">Child Elements</span></span>  
  
|<span data-ttu-id="687b3-127">Elemento</span><span class="sxs-lookup"><span data-stu-id="687b3-127">Element</span></span>|<span data-ttu-id="687b3-128">Descripción</span><span class="sxs-lookup"><span data-stu-id="687b3-128">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="687b3-129">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="687b3-129">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="687b3-130">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="687b3-130">Parent Elements</span></span>  
  
|<span data-ttu-id="687b3-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="687b3-131">Element</span></span>|<span data-ttu-id="687b3-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="687b3-132">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="687b3-133">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="687b3-133">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="687b3-134">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="687b3-134">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="687b3-135">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="687b3-135">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="687b3-136">Observaciones</span><span class="sxs-lookup"><span data-stu-id="687b3-136">Remarks</span></span>  

 <span data-ttu-id="687b3-137">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="687b3-137">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="687b3-138">El valor del `name` atributo se usa para agregar el agente de escucha compartido a una `Listeners` colección para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="687b3-138">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="687b3-139">El valor del `initializeData` atributo depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="687b3-139">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="687b3-140">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="687b3-140">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="687b3-141">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="687b3-141">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="687b3-142">Esta advertencia se produce porque la configuración se valida con respecto a la clase base abstracta <xref:System.Diagnostics.TraceListener> , que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="687b3-142">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="687b3-143">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="687b3-143">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="687b3-144">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus `initializeData` atributos.</span><span class="sxs-lookup"><span data-stu-id="687b3-144">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="687b3-145">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="687b3-145">Trace listener class</span></span>|<span data-ttu-id="687b3-146">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="687b3-146">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="687b3-147">`useErrorStream`Valor del <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="687b3-147">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="687b3-148">Establezca el `initializeData` atributo en " `true` " para escribir el resultado de seguimiento y depuración en la secuencia de error estándar; establézcalo en " `false` " para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="687b3-148">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="687b3-149">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="687b3-149">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="687b3-150">Nombre de un origen existente del registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="687b3-150">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="687b3-151">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="687b3-151">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="687b3-152">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="687b3-152">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="687b3-153">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="687b3-153">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="687b3-154">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="687b3-154">Configuration File</span></span>  

 <span data-ttu-id="687b3-155">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="687b3-155">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="687b3-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="687b3-156">Example</span></span>  

 <span data-ttu-id="687b3-157">En el ejemplo siguiente se muestra cómo utilizar `<add>` los elementos para agregar <xref:System.Diagnostics.TextWriterTraceListener> `textListener` a la `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="687b3-157">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="687b3-158">`textListener` se agrega por nombre a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="687b3-158">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="687b3-159">El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="687b3-159">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <sources>  
      <source name="TraceSourceApp" switchName="sourceSwitch"
        switchType="System.Diagnostics.SourceSwitch">  
        <listeners>  
          <add name="console"
            type="System.Diagnostics.ConsoleTraceListener"/>  
          <add name="textListener"/>  
          <remove name="Default"/>  
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
  
## <a name="see-also"></a><span data-ttu-id="687b3-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="687b3-160">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="687b3-161">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="687b3-161">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="687b3-162">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="687b3-162">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
