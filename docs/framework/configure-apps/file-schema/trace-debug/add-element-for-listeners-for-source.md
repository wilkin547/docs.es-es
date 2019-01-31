---
title: Elemento <add> de <listeners> de <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: ae5231f43e7c157b5250376f7ab97deccea595e5
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55277126"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="d40d0-102">\<Agregar > elemento para \<los agentes de escucha > para \<origen ></span><span class="sxs-lookup"><span data-stu-id="d40d0-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="d40d0-103">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  
  
 <span data-ttu-id="d40d0-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="d40d0-104">\<configuration></span></span>  
<span data-ttu-id="d40d0-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="d40d0-105">\<system.diagnostics></span></span>  
<span data-ttu-id="d40d0-106">\<orígenes ></span><span class="sxs-lookup"><span data-stu-id="d40d0-106">\<sources></span></span>  
<span data-ttu-id="d40d0-107">\<source></span><span class="sxs-lookup"><span data-stu-id="d40d0-107">\<source></span></span>  
<span data-ttu-id="d40d0-108">\<listeners></span><span class="sxs-lookup"><span data-stu-id="d40d0-108">\<listeners></span></span>  
<span data-ttu-id="d40d0-109">\<add></span><span class="sxs-lookup"><span data-stu-id="d40d0-109">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d40d0-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d40d0-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d40d0-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="d40d0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d40d0-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="d40d0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d40d0-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="d40d0-113">Attributes</span></span>  
  
|<span data-ttu-id="d40d0-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="d40d0-114">Attribute</span></span>|<span data-ttu-id="d40d0-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="d40d0-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="d40d0-116">Atributo, se requiere a menos que se hace referencia a un agente de escucha en el `sharedListeners` colección, en el que caso basta con hacer referencia a él por su nombre (consulte la [ejemplo](#example)).</span><span class="sxs-lookup"><span data-stu-id="d40d0-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="d40d0-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d40d0-117">Specifies the type of the listener.</span></span> <span data-ttu-id="d40d0-118">Debe usar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="d40d0-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../../../docs/framework/reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="d40d0-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d40d0-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d40d0-120">La cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="d40d0-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="d40d0-121">Un <xref:System.Configuration.ConfigurationException> se produce si la clase no tiene un constructor que toma una cadena.</span><span class="sxs-lookup"><span data-stu-id="d40d0-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="d40d0-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d40d0-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d40d0-123">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d40d0-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="d40d0-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="d40d0-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="d40d0-125">Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="d40d0-126">[atributos personalizados]</span><span class="sxs-lookup"><span data-stu-id="d40d0-126">[custom attributes]</span></span>|<span data-ttu-id="d40d0-127">Atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="d40d0-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="d40d0-128">Especifica el valor de atributos específicos del agente de escucha identificado por el <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> método para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="d40d0-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="d40d0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> es un ejemplo de un atributo adicional único para el <xref:System.Diagnostics.DelimitedListTraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="d40d0-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d40d0-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="d40d0-130">Child Elements</span></span>  
  
|<span data-ttu-id="d40d0-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="d40d0-131">Element</span></span>|<span data-ttu-id="d40d0-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="d40d0-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d40d0-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="d40d0-133">\<filter></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="d40d0-134">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="d40d0-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="d40d0-135">Parent Elements</span></span>  
  
|<span data-ttu-id="d40d0-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="d40d0-136">Element</span></span>|<span data-ttu-id="d40d0-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="d40d0-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="d40d0-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="d40d0-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="d40d0-139">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="d40d0-140">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="d40d0-141">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d40d0-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="d40d0-142">Especifica los agentes de escucha que recopilarán, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="d40d0-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d40d0-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d40d0-143">Remarks</span></span>  
 <span data-ttu-id="d40d0-144">Las clases de agente de escucha incluidas en .NET Framework se derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="d40d0-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="d40d0-145">Si no especifica la `name` atributo del agente de escucha de seguimiento, el <xref:System.Diagnostics.TraceListener.Name%2A> el valor predeterminado es propiedad del agente de escucha de seguimiento en una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="d40d0-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="d40d0-146">Si la aplicación tiene sólo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="d40d0-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="d40d0-147">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que permite identificar y administrar los agentes de escucha de seguimiento individuales en el <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> colección.</span><span class="sxs-lookup"><span data-stu-id="d40d0-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d40d0-148">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado del agente de escucha de solo seguimiento de ese tipo y nombre que se va a agregar a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="d40d0-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="d40d0-149">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a los `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="d40d0-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="d40d0-150">El valor de la `initializeData` atributo depende del tipo de agente de escucha que cree.</span><span class="sxs-lookup"><span data-stu-id="d40d0-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="d40d0-151">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="d40d0-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d40d0-152">Cuando se usa el `initializeData` atributo, es posible que obtenga el compilador advertencia "no se declara el atributo 'initializeData'".</span><span class="sxs-lookup"><span data-stu-id="d40d0-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="d40d0-153">Esta advertencia se produce porque se validan los valores de configuración con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="d40d0-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="d40d0-154">Por lo general, puede omitir esta advertencia para las implementaciones de agente de escucha de seguimiento que tiene un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="d40d0-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="d40d0-155">En la tabla siguiente se muestran los agentes de escucha de seguimiento que se incluyen con .NET Framework y se describe el valor de sus `initializeData` atributos.</span><span class="sxs-lookup"><span data-stu-id="d40d0-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="d40d0-156">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d40d0-156">Trace listener class</span></span>|<span data-ttu-id="d40d0-157">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="d40d0-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-158">El `useErrorStream` valor para el <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="d40d0-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="d40d0-159">Establecer el `initializeData` atributo para "`true`"escribir trace y debug de salida a la secuencia de error estándar; establézcalo en"`false`" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="d40d0-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-160">El nombre del archivo de la <xref:System.Diagnostics.DelimitedListTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="d40d0-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-161">El nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="d40d0-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-162">El nombre del archivo que el <xref:System.Diagnostics.EventSchemaTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="d40d0-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-163">El nombre del archivo que el <xref:System.Diagnostics.TextWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="d40d0-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="d40d0-164">El nombre del archivo que el <xref:System.Diagnostics.XmlWriterTraceListener> escribe en.</span><span class="sxs-lookup"><span data-stu-id="d40d0-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="d40d0-165">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="d40d0-165">Configuration File</span></span>  
 <span data-ttu-id="d40d0-166">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="d40d0-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d40d0-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="d40d0-167">Example</span></span>  
 <span data-ttu-id="d40d0-168">El ejemplo siguiente muestra cómo usar `<add>` elementos para agregar los agentes de escucha `console` y `textListener` a la `Listeners` recopilación para el origen de seguimiento `TraceSourceApp`.</span><span class="sxs-lookup"><span data-stu-id="d40d0-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="d40d0-169">La `textListener` agente de escucha escribe la salida de seguimiento en el archivo myListener.log.</span><span class="sxs-lookup"><span data-stu-id="d40d0-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d40d0-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="d40d0-170">See also</span></span>
- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="d40d0-171">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="d40d0-171">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
- [<span data-ttu-id="d40d0-172">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="d40d0-172">Trace Listeners</span></span>](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
