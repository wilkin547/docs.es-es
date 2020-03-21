---
title: Elemento <add> para <sharedListeners>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sharedListeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <sharedListeners>
- add element for <sharedListeners>
ms.assetid: 1595e1bc-2492-421f-8384-7f382eb8eb57
ms.openlocfilehash: 5588892ec75a791eda1eb043936c0af95e79354e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153612"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="ebf63-102">\<agregue> \<Element para sharedListeners></span><span class="sxs-lookup"><span data-stu-id="ebf63-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="ebf63-103">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ebf63-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="ebf63-104">`sharedListeners`es una colección de [ \<](source-element.md) agentes de escucha a los que puede hacer referencia cualquier>de origen o [ \<>](trace-element.md) de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="ebf63-105">De forma predeterminada, `sharedListeners` los agentes de `Listeners` escucha de la colección no se colocan en una colección.</span><span class="sxs-lookup"><span data-stu-id="ebf63-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="ebf63-106">Deben agregarse por nombre al [ \<>](source-element.md) de origen o [ \<seguimiento>](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="ebf63-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="ebf63-107">No es posible obtener los agentes de escucha de la `sharedListeners` colección en código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ebf63-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

<span data-ttu-id="ebf63-108">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebf63-108">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="ebf63-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebf63-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="ebf63-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="ebf63-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>\
<span data-ttu-id="ebf63-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="ebf63-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="ebf63-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebf63-112">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ebf63-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ebf63-113">Attributes and Elements</span></span>  
 <span data-ttu-id="ebf63-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ebf63-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ebf63-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="ebf63-115">Attributes</span></span>  
  
|<span data-ttu-id="ebf63-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="ebf63-116">Attribute</span></span>|<span data-ttu-id="ebf63-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebf63-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ebf63-118">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ebf63-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="ebf63-119">Especifica el nombre del agente de escucha que se `Listeners` usa para agregar el agente de escucha compartido a una colección.</span><span class="sxs-lookup"><span data-stu-id="ebf63-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="ebf63-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ebf63-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="ebf63-121">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ebf63-121">Specifies the type of the listener.</span></span> <span data-ttu-id="ebf63-122">Debe utilizar una cadena que cumpla los requisitos especificados en Especificación de nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="ebf63-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="ebf63-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebf63-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ebf63-124">La cadena que se pasa al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="ebf63-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="ebf63-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ebf63-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="ebf63-126">Representación de cadena <xref:System.Diagnostics.TraceOptions> de uno o varios miembros de enumeración que indica los datos que se van a escribir en la salida de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="ebf63-127">Varios elementos están separados por comas.</span><span class="sxs-lookup"><span data-stu-id="ebf63-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="ebf63-128">El valor predeterminado es "Ninguno".</span><span class="sxs-lookup"><span data-stu-id="ebf63-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ebf63-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ebf63-129">Child Elements</span></span>  
  
|<span data-ttu-id="ebf63-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebf63-130">Element</span></span>|<span data-ttu-id="ebf63-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebf63-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ebf63-132">\<>de filtro</span><span class="sxs-lookup"><span data-stu-id="ebf63-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="ebf63-133">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ebf63-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ebf63-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ebf63-134">Parent Elements</span></span>  
  
|<span data-ttu-id="ebf63-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="ebf63-135">Element</span></span>|<span data-ttu-id="ebf63-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="ebf63-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ebf63-137">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ebf63-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ebf63-138">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="ebf63-139">Colección de agentes de escucha a los que puede hacer referencia cualquier elemento de origen o de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ebf63-140">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ebf63-140">Remarks</span></span>  
 <span data-ttu-id="ebf63-141">Las clases de agente de escucha <xref:System.Diagnostics.TraceListener> incluidas con .NET Framework derivan de la clase.</span><span class="sxs-lookup"><span data-stu-id="ebf63-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="ebf63-142">El valor `name` del atributo se utiliza para `Listeners` agregar el agente de escucha compartido a una colección para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="ebf63-143">El valor `initializeData` del atributo depende del tipo de agente de escucha que cree.</span><span class="sxs-lookup"><span data-stu-id="ebf63-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="ebf63-144">No todos los agentes `initializeData`de escucha de seguimiento requieren que especifique .</span><span class="sxs-lookup"><span data-stu-id="ebf63-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ebf63-145">Cuando se `initializeData` utiliza el atributo, puede obtener la advertencia del compilador "El atributo 'initializeData' no se declara."</span><span class="sxs-lookup"><span data-stu-id="ebf63-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="ebf63-146">Esta advertencia se produce porque los valores de <xref:System.Diagnostics.TraceListener>configuración se validan con la clase base abstracta, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="ebf63-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="ebf63-147">Normalmente, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="ebf63-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="ebf63-148">En la tabla siguiente se muestran los agentes de escucha de `initializeData` seguimiento que se incluyen con .NET Framework y se describe el valor de sus atributos.</span><span class="sxs-lookup"><span data-stu-id="ebf63-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="ebf63-149">Clase de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ebf63-149">Trace listener class</span></span>|<span data-ttu-id="ebf63-150">initializeData valor del atributo</span><span class="sxs-lookup"><span data-stu-id="ebf63-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="ebf63-151">El `useErrorStream` valor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.</span><span class="sxs-lookup"><span data-stu-id="ebf63-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="ebf63-152">Establezca `initializeData` el atributo`true`en " " para escribir la salida de seguimiento y depuración en la secuencia de errores estándar; establecerlo en`false`" " para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="ebf63-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="ebf63-153">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ebf63-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ebf63-154">Nombre de un origen existente del registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="ebf63-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ebf63-155">El nombre del archivo <xref:System.Diagnostics.EventSchemaTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="ebf63-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ebf63-156">El nombre del archivo <xref:System.Diagnostics.TextWriterTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="ebf63-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="ebf63-157">El nombre del archivo <xref:System.Diagnostics.XmlWriterTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="ebf63-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="ebf63-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ebf63-158">Configuration File</span></span>  
 <span data-ttu-id="ebf63-159">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ebf63-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ebf63-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ebf63-160">Example</span></span>  
 <span data-ttu-id="ebf63-161">En el ejemplo siguiente `<add>` se muestra <xref:System.Diagnostics.TextWriterTraceListener> `textListener` cómo `sharedListeners` utilizar elementos para agregar el a la colección.</span><span class="sxs-lookup"><span data-stu-id="ebf63-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="ebf63-162">`textListener`se agrega por `Listeners` nombre a la `TraceSourceApp`colección para el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebf63-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="ebf63-163">El `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.</span><span class="sxs-lookup"><span data-stu-id="ebf63-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ebf63-164">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ebf63-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ebf63-165">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="ebf63-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ebf63-166">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ebf63-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
