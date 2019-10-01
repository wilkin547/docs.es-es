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
ms.openlocfilehash: 0c7665898f8c625c2d07b67ea6c7fe25113fddd8
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699474"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="fab7b-102">\<add > elemento para \<sharedListeners ></span><span class="sxs-lookup"><span data-stu-id="fab7b-102">\<add> Element for \<sharedListeners></span></span>
<span data-ttu-id="fab7b-103">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="fab7b-104">`sharedListeners` es una colección de agentes de escucha a los que puede hacer referencia cualquier [> \<source](source-element.md) o [@no__t-> 4trace](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="fab7b-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="fab7b-105">De forma predeterminada, los agentes de escucha de la colección `sharedListeners` no se colocan en una colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="fab7b-106">Se deben agregar por nombre al > [@no__t-> 1source](source-element.md) o [\<trace](trace-element.md).</span><span class="sxs-lookup"><span data-stu-id="fab7b-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="fab7b-107">No es posible obtener los agentes de escucha de la colección `sharedListeners` en el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="fab7b-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  
  
[<span data-ttu-id="fab7b-108"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="fab7b-108">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="fab7b-109">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fab7b-109">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="fab7b-110">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<sharedListeners >** ](sharedlisteners-element.md)</span><span class="sxs-lookup"><span data-stu-id="fab7b-110">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)</span></span>  
<span data-ttu-id="fab7b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="fab7b-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fab7b-112">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fab7b-112">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fab7b-113">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fab7b-113">Attributes and Elements</span></span>  
 <span data-ttu-id="fab7b-114">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fab7b-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fab7b-115">Atributos</span><span class="sxs-lookup"><span data-stu-id="fab7b-115">Attributes</span></span>  
  
|<span data-ttu-id="fab7b-116">Atributo</span><span class="sxs-lookup"><span data-stu-id="fab7b-116">Attribute</span></span>|<span data-ttu-id="fab7b-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab7b-117">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="fab7b-118">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="fab7b-118">Required attribute.</span></span><br /><br /> <span data-ttu-id="fab7b-119">Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a una colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-119">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="fab7b-120">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="fab7b-120">Required attribute.</span></span><br /><br /> <span data-ttu-id="fab7b-121">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fab7b-121">Specifies the type of the listener.</span></span> <span data-ttu-id="fab7b-122">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fab7b-122">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fab7b-123">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fab7b-123">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fab7b-124">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="fab7b-124">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="fab7b-125">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fab7b-125">Optional attribute.</span></span><br/><br/><span data-ttu-id="fab7b-126">Representación de cadena de uno o más miembros de la enumeración <xref:System.Diagnostics.TraceOptions> que indica los datos que se van a escribir en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fab7b-126">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="fab7b-127">Varios elementos se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="fab7b-127">Multiple items are separated by commas.</span></span> <span data-ttu-id="fab7b-128">El valor predeterminado es "none".</span><span class="sxs-lookup"><span data-stu-id="fab7b-128">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="fab7b-129">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fab7b-129">Child Elements</span></span>  
  
|<span data-ttu-id="fab7b-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="fab7b-130">Element</span></span>|<span data-ttu-id="fab7b-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab7b-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fab7b-132">\<filter></span><span class="sxs-lookup"><span data-stu-id="fab7b-132">\<filter></span></span>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="fab7b-133">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-133">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fab7b-134">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fab7b-134">Parent Elements</span></span>  
  
|<span data-ttu-id="fab7b-135">Elemento</span><span class="sxs-lookup"><span data-stu-id="fab7b-135">Element</span></span>|<span data-ttu-id="fab7b-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="fab7b-136">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fab7b-137">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fab7b-137">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fab7b-138">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fab7b-138">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="fab7b-139">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fab7b-139">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fab7b-140">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fab7b-140">Remarks</span></span>  
 <span data-ttu-id="fab7b-141">Las clases de agente de escucha incluidas con el .NET Framework derivan de la clase <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fab7b-141">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="fab7b-142">El valor del atributo `name` se usa para agregar el agente de escucha compartido a una colección `Listeners` para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fab7b-142">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="fab7b-143">El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="fab7b-143">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="fab7b-144">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-144">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fab7b-145">Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="fab7b-145">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="fab7b-146">Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-146">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="fab7b-147">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="fab7b-147">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="fab7b-148">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de los atributos `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-148">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="fab7b-149">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fab7b-149">Trace listener class</span></span>|<span data-ttu-id="fab7b-150">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="fab7b-150">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="fab7b-151">El valor `useErrorStream` para el constructor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="fab7b-151">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="fab7b-152">Establezca el atributo `initializeData` en "`true`" para escribir la salida de seguimiento y de depuración en la secuencia de error estándar. establézcalo en "`false`" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="fab7b-152">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="fab7b-153">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="fab7b-153">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fab7b-154">Nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="fab7b-154">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fab7b-155">Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fab7b-155">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fab7b-156">Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fab7b-156">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="fab7b-157">Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fab7b-157">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="fab7b-158">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="fab7b-158">Configuration File</span></span>  
 <span data-ttu-id="fab7b-159">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fab7b-159">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fab7b-160">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fab7b-160">Example</span></span>  
 <span data-ttu-id="fab7b-161">En el ejemplo siguiente se muestra cómo usar los elementos `<add>` para agregar el <xref:System.Diagnostics.TextWriterTraceListener> @ no__t-2 a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-161">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="fab7b-162">`textListener` se agrega por nombre a la colección `Listeners` para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="fab7b-162">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="fab7b-163">El agente de escucha `textListener` escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="fab7b-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fab7b-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="fab7b-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fab7b-165">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="fab7b-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fab7b-166">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fab7b-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
