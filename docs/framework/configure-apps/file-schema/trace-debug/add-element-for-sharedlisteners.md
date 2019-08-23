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
ms.openlocfilehash: c4b83834fb7aaf64a696b85bd2c8da47cfba2397
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927212"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="3d02b-102">\<Agregue > elemento para \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="3d02b-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="3d02b-103">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="3d02b-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="3d02b-104">`sharedListeners`es una colección de agentes de escucha a los que puede hacer referencia cualquier [ \<> de origen](source-element.md) o [ \<> de seguimiento](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="3d02b-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="3d02b-105">De forma predeterminada, los agentes de `sharedListeners` escucha de la colección no se `Listeners` colocan en una colección.</span><span class="sxs-lookup"><span data-stu-id="3d02b-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="3d02b-106">Se deben agregar por nombre al [ \<> de origen](source-element.md) o [ \<> de seguimiento](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="3d02b-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="3d02b-107">No es posible obtener los agentes de escucha de la colección `sharedListeners` en el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3d02b-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
 <span data-ttu-id="3d02b-108">\<configuration></span><span class="sxs-lookup"><span data-stu-id="3d02b-108">\<configuration></span></span>  
<span data-ttu-id="3d02b-109">&nbsp;&nbsp;\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="3d02b-109">&nbsp;&nbsp;\<system.diagnostics></span></span>  
<span data-ttu-id="3d02b-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners > elemento</span><span class="sxs-lookup"><span data-stu-id="3d02b-110">&nbsp;&nbsp;&nbsp;&nbsp;\<sharedListeners> Element</span></span>  
<span data-ttu-id="3d02b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span><span class="sxs-lookup"><span data-stu-id="3d02b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d02b-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d02b-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3d02b-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="3d02b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="3d02b-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="3d02b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3d02b-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="3d02b-115">Attributes</span></span>  
  
|<span data-ttu-id="3d02b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="3d02b-116">Attribute</span></span>|<span data-ttu-id="3d02b-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d02b-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="3d02b-118">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3d02b-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="3d02b-119">Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a `Listeners` una colección.</span><span class="sxs-lookup"><span data-stu-id="3d02b-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="3d02b-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="3d02b-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="3d02b-121">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="3d02b-121">Specifies the type of the listener.</span></span> <span data-ttu-id="3d02b-122">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="3d02b-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="3d02b-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="3d02b-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="3d02b-124">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="3d02b-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="3d02b-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="3d02b-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="3d02b-126">Representación de cadena de uno o más <xref:System.Diagnostics.TraceOptions> miembros de la enumeración que indica los datos que se van a escribir en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d02b-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="3d02b-127">Varios elementos se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="3d02b-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="3d02b-128">El valor predeterminado es "none".</span><span class="sxs-lookup"><span data-stu-id="3d02b-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="3d02b-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="3d02b-129">Child Elements</span></span>  
  
|<span data-ttu-id="3d02b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d02b-130">Element</span></span>|<span data-ttu-id="3d02b-131">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d02b-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3d02b-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="3d02b-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="3d02b-133">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="3d02b-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3d02b-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="3d02b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="3d02b-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="3d02b-135">Element</span></span>|<span data-ttu-id="3d02b-136">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3d02b-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="3d02b-137">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3d02b-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="3d02b-138">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d02b-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="3d02b-139">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d02b-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3d02b-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3d02b-140">Remarks</span></span>  
 <span data-ttu-id="3d02b-141">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="3d02b-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="3d02b-142">El valor `name` del atributo se usa para agregar el agente de escucha compartido a una `Listeners` colección para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d02b-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="3d02b-143">El valor `initializeData` del atributo depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="3d02b-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="3d02b-144">No todos los agentes de escucha de seguimiento requieren `initializeData`que se especifique.</span><span class="sxs-lookup"><span data-stu-id="3d02b-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="3d02b-145">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="3d02b-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="3d02b-146">Esta advertencia se produce porque la configuración se valida con respecto a la clase <xref:System.Diagnostics.TraceListener>base abstracta, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="3d02b-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="3d02b-147">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="3d02b-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="3d02b-148">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el `initializeData` valor de sus atributos.</span><span class="sxs-lookup"><span data-stu-id="3d02b-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="3d02b-149">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3d02b-149">Trace listener class</span></span>|<span data-ttu-id="3d02b-150">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="3d02b-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="3d02b-151">`useErrorStream` Valor<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.</span><span class="sxs-lookup"><span data-stu-id="3d02b-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="3d02b-152">Establezca el `initializeData` atributo en "`true`" para escribir el resultado de seguimiento y depuración en la secuencia de error estándar`false`; establézcalo en "" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="3d02b-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="3d02b-153">Nombre del archivo <xref:System.Diagnostics.DelimitedListTraceListener> en el que escribe.</span><span class="sxs-lookup"><span data-stu-id="3d02b-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="3d02b-154">Nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="3d02b-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="3d02b-155">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="3d02b-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="3d02b-156">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="3d02b-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="3d02b-157">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="3d02b-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="3d02b-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="3d02b-158">Configuration File</span></span>  
 <span data-ttu-id="3d02b-159">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3d02b-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d02b-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d02b-160">Example</span></span>  
 <span data-ttu-id="3d02b-161">En el ejemplo siguiente se muestra cómo `<add>` utilizar los elementos para <xref:System.Diagnostics.TextWriterTraceListener> `textListener` agregar a `sharedListeners` la colección.</span><span class="sxs-lookup"><span data-stu-id="3d02b-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="3d02b-162">`textListener`se agrega por nombre a la `Listeners` colección para el origen `TraceSourceApp`de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="3d02b-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="3d02b-163">El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="3d02b-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="3d02b-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d02b-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="3d02b-165">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="3d02b-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="3d02b-166">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="3d02b-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
