---
title: <add>Elemento <listeners> para for<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 883eef32172c5a7f900197995b4c57c3d5a84e19
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153690"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="e9b9b-102">\<agregue> \<Element para \<los agentes de escucha> para el origen></span><span class="sxs-lookup"><span data-stu-id="e9b9b-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="e9b9b-103">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="e9b9b-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b9b-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="e9b9b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b9b-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="e9b9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuentes>**](sources-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b9b-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="e9b9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<fuente>**](source-element.md)</span><span class="sxs-lookup"><span data-stu-id="e9b9b-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="e9b9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oyentes>**](listeners-element-for-source.md)</span><span class="sxs-lookup"><span data-stu-id="e9b9b-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="e9b9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<añadir>**</span><span class="sxs-lookup"><span data-stu-id="e9b9b-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="e9b9b-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e9b9b-110">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9b9b-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e9b9b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="e9b9b-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9b9b-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="e9b9b-113">Attributes</span></span>  
  
|<span data-ttu-id="e9b9b-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="e9b9b-114">Attribute</span></span>|<span data-ttu-id="e9b9b-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9b9b-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="e9b9b-116">Atributo requerido, a menos que haga `sharedListeners` referencia a un agente de escucha de la colección, en cuyo caso solo necesita hacer referencia a él por su nombre (consulte el [ejemplo](#example)).</span><span class="sxs-lookup"><span data-stu-id="e9b9b-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="e9b9b-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-117">Specifies the type of the listener.</span></span> <span data-ttu-id="e9b9b-118">Debe utilizar una cadena que cumpla los requisitos especificados en Especificación de nombres de [tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="e9b9b-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="e9b9b-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9b9b-120">La cadena que se pasa al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="e9b9b-121">A <xref:System.Configuration.ConfigurationException> se produce si la clase no tiene un constructor que toma una cadena.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="e9b9b-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9b9b-123">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="e9b9b-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="e9b9b-125">Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="e9b9b-126">[atributos personalizados]</span><span class="sxs-lookup"><span data-stu-id="e9b9b-126">[custom attributes]</span></span>|<span data-ttu-id="e9b9b-127">Atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="e9b9b-128">Especifica el valor de los atributos <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> específicos del agente de escucha identificados por el método para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="e9b9b-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>es un ejemplo de un <xref:System.Diagnostics.DelimitedListTraceListener> atributo adicional único para la clase.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9b9b-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e9b9b-130">Child Elements</span></span>  
  
|<span data-ttu-id="e9b9b-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9b9b-131">Element</span></span>|<span data-ttu-id="e9b9b-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9b9b-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9b9b-133">\<>de filtro</span><span class="sxs-lookup"><span data-stu-id="e9b9b-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="e9b9b-134">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9b9b-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e9b9b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="e9b9b-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="e9b9b-136">Element</span></span>|<span data-ttu-id="e9b9b-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="e9b9b-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e9b9b-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="e9b9b-139">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="e9b9b-140">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="e9b9b-141">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="e9b9b-142">Especifica los agentes de escucha que recopilan, almacenan y enrutan mensajes.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9b9b-143">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e9b9b-143">Remarks</span></span>  
 <span data-ttu-id="e9b9b-144">Las clases de agente de escucha <xref:System.Diagnostics.TraceListener> incluidas con .NET Framework derivan de la clase.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="e9b9b-145">Si no especifica `name` el atributo del agente <xref:System.Diagnostics.TraceListener.Name%2A> de escucha de seguimiento, la propiedad del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="e9b9b-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="e9b9b-146">Si la aplicación solo tiene un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo especificando una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="e9b9b-147">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la colección.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b9b-148">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el `Listeners` mismo nombre da como resultado que solo se agregue un agente de escucha de seguimiento de ese tipo y nombre a la colección.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="e9b9b-149">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="e9b9b-150">El valor `initializeData` del atributo depende del tipo de agente de escucha que cree.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="e9b9b-151">No todos los agentes `initializeData`de escucha de seguimiento requieren que especifique .</span><span class="sxs-lookup"><span data-stu-id="e9b9b-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e9b9b-152">Cuando se `initializeData` utiliza el atributo, puede obtener la advertencia del compilador "El atributo 'initializeData' no se declara."</span><span class="sxs-lookup"><span data-stu-id="e9b9b-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="e9b9b-153">Esta advertencia se produce porque los valores de <xref:System.Diagnostics.TraceListener>configuración se validan con la clase base abstracta, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="e9b9b-154">Normalmente, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="e9b9b-155">En la tabla siguiente se muestran los agentes de escucha de `initializeData` seguimiento que se incluyen con .NET Framework y se describe el valor de sus atributos.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="e9b9b-156">Clase de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e9b9b-156">Trace listener class</span></span>|<span data-ttu-id="e9b9b-157">initializeData valor del atributo</span><span class="sxs-lookup"><span data-stu-id="e9b9b-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-158">El `useErrorStream` valor <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="e9b9b-159">Establezca `initializeData` el atributo`true`en " " para escribir la salida de seguimiento y depuración en la secuencia de errores estándar; establecerlo en`false`" " para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-160">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-161">Nombre de un origen existente del registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-162">El nombre del archivo <xref:System.Diagnostics.EventSchemaTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-163">El nombre del archivo <xref:System.Diagnostics.TextWriterTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="e9b9b-164">El nombre del archivo <xref:System.Diagnostics.XmlWriterTraceListener> en el que escribe el archivo.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="e9b9b-165">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="e9b9b-165">Configuration File</span></span>  
 <span data-ttu-id="e9b9b-166">Este elemento se puede utilizar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e9b9b-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e9b9b-167">Example</span></span>  
 <span data-ttu-id="e9b9b-168">En el ejemplo siguiente `<add>` se muestra cómo `console` `textListener` utilizar `Listeners` elementos para `TraceSourceApp`agregar los agentes de escucha y a la colección para el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="e9b9b-169">El `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.</span><span class="sxs-lookup"><span data-stu-id="e9b9b-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e9b9b-170">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e9b9b-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="e9b9b-171">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="e9b9b-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="e9b9b-172">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="e9b9b-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
