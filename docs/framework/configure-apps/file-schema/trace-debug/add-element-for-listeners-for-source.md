---
title: <add> elemento de <listeners> para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: c32205310f9fc451a5a55a943f925ee52f65c8a8
ms.sourcegitcommit: 7f8eeef060ddeb2cabfa52843776faf652c5a1f5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/14/2019
ms.locfileid: "74089001"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="fa751-102">\<agregar > elemento para \<agentes de escucha > para \<origen ></span><span class="sxs-lookup"><span data-stu-id="fa751-102">\<add> Element for \<listeners> for \<source></span></span>
<span data-ttu-id="fa751-103">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-103">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

<span data-ttu-id="fa751-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa751-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa751-105">&nbsp;&nbsp;[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa751-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="fa751-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<orígenes**](sources-element.md) ></span><span class="sxs-lookup"><span data-stu-id="fa751-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)</span></span>\
<span data-ttu-id="fa751-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**origen**](source-element.md) ></span><span class="sxs-lookup"><span data-stu-id="fa751-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)</span></span>\
<span data-ttu-id="fa751-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<[**agentes de escucha**](listeners-element-for-source.md) ></span><span class="sxs-lookup"><span data-stu-id="fa751-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)</span></span>\
<span data-ttu-id="fa751-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**agregar >**</span><span class="sxs-lookup"><span data-stu-id="fa751-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>

## <a name="syntax"></a><span data-ttu-id="fa751-110">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fa751-110">Syntax</span></span>  
  
```xml  
<add name="name"   
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa751-111">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="fa751-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa751-112">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="fa751-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa751-113">Atributos</span><span class="sxs-lookup"><span data-stu-id="fa751-113">Attributes</span></span>  
  
|<span data-ttu-id="fa751-114">Atributo</span><span class="sxs-lookup"><span data-stu-id="fa751-114">Attribute</span></span>|<span data-ttu-id="fa751-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa751-115">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="fa751-116">Atributo required, a menos que haga referencia a un agente de escucha en la colección de `sharedListeners`, en cuyo caso solo necesita hacer referencia a él por su nombre (vea el [ejemplo](#example)).</span><span class="sxs-lookup"><span data-stu-id="fa751-116">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="fa751-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fa751-117">Specifies the type of the listener.</span></span> <span data-ttu-id="fa751-118">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="fa751-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="fa751-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fa751-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fa751-120">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="fa751-120">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="fa751-121">Se produce una <xref:System.Configuration.ConfigurationException> si la clase no tiene un constructor que toma una cadena.</span><span class="sxs-lookup"><span data-stu-id="fa751-121">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="fa751-122">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fa751-122">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fa751-123">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fa751-123">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="fa751-124">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="fa751-124">Optional attribute.</span></span><br /><br /> <span data-ttu-id="fa751-125">Especifica el valor de propiedad <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-125">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="fa751-126">[atributos personalizados]</span><span class="sxs-lookup"><span data-stu-id="fa751-126">[custom attributes]</span></span>|<span data-ttu-id="fa751-127">Atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="fa751-127">Optional attributes.</span></span><br /><br /> <span data-ttu-id="fa751-128">Especifica el valor de los atributos específicos del agente de escucha identificados por el método <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="fa751-128">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="fa751-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> es un ejemplo de un atributo adicional que es único para la clase <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-129"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa751-130">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="fa751-130">Child Elements</span></span>  
  
|<span data-ttu-id="fa751-131">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa751-131">Element</span></span>|<span data-ttu-id="fa751-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa751-132">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa751-133">\<filter></span><span class="sxs-lookup"><span data-stu-id="fa751-133">\<filter></span></span>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="fa751-134">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-134">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="fa751-135">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="fa751-135">Parent Elements</span></span>  
  
|<span data-ttu-id="fa751-136">Elemento</span><span class="sxs-lookup"><span data-stu-id="fa751-136">Element</span></span>|<span data-ttu-id="fa751-137">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa751-137">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="fa751-138">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="fa751-138">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="fa751-139">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-139">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="fa751-140">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-140">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="fa751-141">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-141">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="fa751-142">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="fa751-142">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa751-143">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fa751-143">Remarks</span></span>  
 <span data-ttu-id="fa751-144">Las clases de agente de escucha incluidas con el .NET Framework derivan de la clase <xref:System.Diagnostics.TraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-144">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="fa751-145">Si no especifica el atributo `name` del agente de escucha de seguimiento, la propiedad <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="fa751-145">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="fa751-146">Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo si especifica una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="fa751-146">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="fa751-147">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la colección de <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fa751-147">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa751-148">Al agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre, solo se agrega un agente de escucha de seguimiento de ese tipo y nombre a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="fa751-148">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="fa751-149">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la colección de `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="fa751-149">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="fa751-150">El valor del atributo `initializeData` depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="fa751-150">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="fa751-151">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fa751-151">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fa751-152">Al usar el atributo `initializeData`, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="fa751-152">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="fa751-153">Esta advertencia se produce porque los valores de configuración se validan con la clase base abstracta <xref:System.Diagnostics.TraceListener>, que no reconoce el atributo `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fa751-153">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="fa751-154">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="fa751-154">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="fa751-155">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos `initializeData`.</span><span class="sxs-lookup"><span data-stu-id="fa751-155">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="fa751-156">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fa751-156">Trace listener class</span></span>|<span data-ttu-id="fa751-157">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="fa751-157">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-158">El valor `useErrorStream` del constructor de <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A>.</span><span class="sxs-lookup"><span data-stu-id="fa751-158">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="fa751-159">Establezca el atributo `initializeData` en "`true`" para escribir el resultado de seguimiento y de depuración en la secuencia de error estándar. establézcalo en "`false`" para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="fa751-159">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-160">Nombre del archivo en el que se escribe el <xref:System.Diagnostics.DelimitedListTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-160">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-161">Nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="fa751-161">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-162">Nombre del archivo en el que escribe el <xref:System.Diagnostics.EventSchemaTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-162">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-163">Nombre del archivo en el que escribe el <xref:System.Diagnostics.TextWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-163">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="fa751-164">Nombre del archivo en el que escribe el <xref:System.Diagnostics.XmlWriterTraceListener>.</span><span class="sxs-lookup"><span data-stu-id="fa751-164">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="fa751-165">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="fa751-165">Configuration File</span></span>  
 <span data-ttu-id="fa751-166">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="fa751-166">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa751-167">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fa751-167">Example</span></span>  
 <span data-ttu-id="fa751-168">En el ejemplo siguiente se muestra cómo utilizar los elementos `<add>` para agregar los agentes de escucha `console` y `textListener` a la colección de `Listeners` para la `TraceSourceApp`de origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="fa751-168">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="fa751-169">El agente de escucha de `textListener` escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="fa751-169">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fa751-170">Vea también</span><span class="sxs-lookup"><span data-stu-id="fa751-170">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="fa751-171">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="fa751-171">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="fa751-172">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="fa751-172">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
