---
title: <add>(Elemento <listeners> ) para<source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: 96bfde3ec425f6f77d1d655808d155eb0e6fcd0f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69927197"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="83170-102">\<Agregar > elemento para \<los agentes de escucha \<> para el origen ></span><span class="sxs-lookup"><span data-stu-id="83170-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="83170-103">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="83170-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="83170-104">\<configuration></span></span>  
<span data-ttu-id="83170-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="83170-105">\<system.diagnostics></span></span>  
<span data-ttu-id="83170-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="83170-106">\<sources></span></span>  
<span data-ttu-id="83170-107">\<> de origen</span><span class="sxs-lookup"><span data-stu-id="83170-107">\<source></span></span>  
<span data-ttu-id="83170-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="83170-108">\<listeners></span></span>  
<span data-ttu-id="83170-109">\<add></span><span class="sxs-lookup"><span data-stu-id="83170-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83170-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83170-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="83170-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="83170-111">Attributes and Elements</span></span>  
 <span data-ttu-id="83170-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="83170-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="83170-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="83170-113">Attributes</span></span>  
  
|<span data-ttu-id="83170-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="83170-114">Attribute</span></span>|<span data-ttu-id="83170-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83170-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="83170-116">Atributo required, a menos que haga referencia a un `sharedListeners` agente de escucha en la colección, en cuyo caso solo necesita hacer referencia a él por su nombre (vea el [ejemplo](#example)).</span><span class="sxs-lookup"><span data-stu-id="83170-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="83170-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="83170-117">Specifies the type of the listener.</span></span> <span data-ttu-id="83170-118">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="83170-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="83170-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="83170-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83170-120">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="83170-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="83170-121">Se <xref:System.Configuration.ConfigurationException> produce una excepción si la clase no tiene un constructor que toma una cadena.</span><span class="sxs-lookup"><span data-stu-id="83170-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="83170-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="83170-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83170-123">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="83170-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="83170-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="83170-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="83170-125">Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="83170-126">[atributos personalizados]</span><span class="sxs-lookup"><span data-stu-id="83170-126">[custom attributes]</span></span>|<span data-ttu-id="83170-127">Atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="83170-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="83170-128">Especifica el valor para los atributos específicos del agente de escucha identificados por el <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> método para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="83170-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="83170-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A>es un ejemplo de un atributo adicional que es único <xref:System.Diagnostics.DelimitedListTraceListener> para la clase.</span><span class="sxs-lookup"><span data-stu-id="83170-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="83170-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="83170-130">Child Elements</span></span>  
  
|<span data-ttu-id="83170-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="83170-131">Element</span></span>|<span data-ttu-id="83170-132">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83170-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="83170-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="83170-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="83170-134">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="83170-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="83170-135">Parent Elements</span></span>  
  
|<span data-ttu-id="83170-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="83170-136">Element</span></span>|<span data-ttu-id="83170-137">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="83170-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="83170-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="83170-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="83170-139">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="83170-140">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="83170-141">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="83170-142">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="83170-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="83170-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83170-143">Remarks</span></span>  
 <span data-ttu-id="83170-144">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="83170-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="83170-145">Si no especifica el `name` atributo del agente de escucha de seguimiento, la <xref:System.Diagnostics.TraceListener.Name%2A> propiedad del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="83170-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="83170-146">Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo si especifica una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="83170-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="83170-147">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> de seguimiento individuales en la colección.</span><span class="sxs-lookup"><span data-stu-id="83170-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83170-148">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado que solo se agregue a la `Listeners` colección un agente de escucha de seguimiento de ese tipo y nombre.</span><span class="sxs-lookup"><span data-stu-id="83170-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="83170-149">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos `Listeners` a la colección.</span><span class="sxs-lookup"><span data-stu-id="83170-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="83170-150">El valor `initializeData` del atributo depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="83170-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="83170-151">No todos los agentes de escucha de seguimiento requieren `initializeData`que se especifique.</span><span class="sxs-lookup"><span data-stu-id="83170-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="83170-152">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="83170-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="83170-153">Esta advertencia se produce porque la configuración se valida con respecto a la clase <xref:System.Diagnostics.TraceListener>base abstracta, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="83170-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="83170-154">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="83170-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="83170-155">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el `initializeData` valor de sus atributos.</span><span class="sxs-lookup"><span data-stu-id="83170-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="83170-156">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="83170-156">Trace listener class</span></span>|<span data-ttu-id="83170-157">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="83170-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-158">`useErrorStream` Valor<xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> del constructor.</span><span class="sxs-lookup"><span data-stu-id="83170-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="83170-159">Establezca el `initializeData` atributo en "`true`" para escribir el resultado de seguimiento y depuración en la secuencia de error estándar`false`; establézcalo en "" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="83170-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-160">Nombre del archivo <xref:System.Diagnostics.DelimitedListTraceListener> en el que escribe.</span><span class="sxs-lookup"><span data-stu-id="83170-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-161">Nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="83170-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-162">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="83170-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-163">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="83170-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="83170-164">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="83170-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="83170-165">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="83170-165">Configuration File</span></span>  
 <span data-ttu-id="83170-166">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="83170-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="83170-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="83170-167">Example</span></span>  
 <span data-ttu-id="83170-168">En el ejemplo siguiente se muestra cómo `<add>` utilizar los elementos para agregar los `console` agentes `textListener` de escucha `Listeners` y a la colección para `TraceSourceApp`el origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="83170-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="83170-169">El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="83170-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="83170-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="83170-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="83170-171">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="83170-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="83170-172">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="83170-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
