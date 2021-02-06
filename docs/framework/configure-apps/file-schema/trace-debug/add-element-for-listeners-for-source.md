---
description: 'Más información sobre: <add> elemento para <listeners> para <source>'
title: <add> (Elemento <listeners> ) para <source>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources/source/listeners/add
helpviewer_keywords:
- initializeData attribute
- add element for <listeners> for <source>
- <add> element for <listeners> for <source>
ms.assetid: 4ce36ac1-81ef-48e8-b8b2-b5a5b0e2adcb
ms.openlocfilehash: cb2145738b81574397a8de13f68d0d4e572f20cd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99639840"
---
# <a name="add-element-for-listeners-for-source"></a><span data-ttu-id="87354-103">\<add> (Elemento \<listeners> ) para \<source></span><span class="sxs-lookup"><span data-stu-id="87354-103">\<add> Element for \<listeners> for \<source></span></span>

<span data-ttu-id="87354-104">Agrega un agente de escucha a la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-104">Adds a listener to the `Listeners` collection for a trace source.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sources>**](sources-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<source>**](source-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-source.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="87354-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="87354-105">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="87354-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="87354-106">Attributes and Elements</span></span>  

 <span data-ttu-id="87354-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="87354-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="87354-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="87354-108">Attributes</span></span>  
  
|<span data-ttu-id="87354-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="87354-109">Attribute</span></span>|<span data-ttu-id="87354-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="87354-110">Description</span></span>|  
|---------------|-----------------|  
|`type`|<span data-ttu-id="87354-111">Atributo required, a menos que haga referencia a un agente de escucha en la `sharedListeners` colección, en cuyo caso solo necesita hacer referencia a él por su nombre (vea el [ejemplo](#example)).</span><span class="sxs-lookup"><span data-stu-id="87354-111">Required attribute, unless you're referencing a listener in the `sharedListeners` collection, in which case you only need to refer to it by name (see the [Example](#example)).</span></span><br /><br /> <span data-ttu-id="87354-112">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="87354-112">Specifies the type of the listener.</span></span> <span data-ttu-id="87354-113">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="87354-113">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="87354-114">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="87354-114">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87354-115">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="87354-115">The string passed to the constructor for the specified class.</span></span> <span data-ttu-id="87354-116"><xref:System.Configuration.ConfigurationException>Se produce una excepción si la clase no tiene un constructor que toma una cadena.</span><span class="sxs-lookup"><span data-stu-id="87354-116">A <xref:System.Configuration.ConfigurationException> is thrown if the class does not have a constructor that takes a string.</span></span>|  
|`name`|<span data-ttu-id="87354-117">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="87354-117">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87354-118">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="87354-118">Specifies the name of the listener.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="87354-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="87354-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="87354-120">Especifica el <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> valor de propiedad para el agente de escucha de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-120">Specifies the <xref:System.Diagnostics.TraceListener.TraceOutputOptions%2A> property value for the trace listener.</span></span>|  
|<span data-ttu-id="87354-121">[atributos personalizados]</span><span class="sxs-lookup"><span data-stu-id="87354-121">[custom attributes]</span></span>|<span data-ttu-id="87354-122">Atributos opcionales.</span><span class="sxs-lookup"><span data-stu-id="87354-122">Optional attributes.</span></span><br /><br /> <span data-ttu-id="87354-123">Especifica el valor para los atributos específicos del agente de escucha identificados por el <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> método para ese agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="87354-123">Specifies the value for listener-specific attributes identified by the <xref:System.Diagnostics.TraceListener.GetSupportedAttributes%2A> method for that listener.</span></span> <span data-ttu-id="87354-124"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> es un ejemplo de un atributo adicional que es único para la <xref:System.Diagnostics.DelimitedListTraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="87354-124"><xref:System.Diagnostics.DelimitedListTraceListener.Delimiter%2A> is an example of an extra attribute unique to the <xref:System.Diagnostics.DelimitedListTraceListener> class.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="87354-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="87354-125">Child Elements</span></span>  
  
|<span data-ttu-id="87354-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="87354-126">Element</span></span>|<span data-ttu-id="87354-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="87354-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-source.md)|<span data-ttu-id="87354-128">Agrega un filtro a un agente de escucha en la colección `Listeners` para un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-128">Adds a filter to a listener in the `Listeners` collection for a trace source.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="87354-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="87354-129">Parent Elements</span></span>  
  
|<span data-ttu-id="87354-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="87354-130">Element</span></span>|<span data-ttu-id="87354-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="87354-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="87354-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="87354-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="87354-133">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sources`|<span data-ttu-id="87354-134">Contiene orígenes de seguimiento que inician mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-134">Contains trace sources that initiate tracing messages.</span></span>|  
|`source`|<span data-ttu-id="87354-135">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="87354-135">Specifies a trace source that initiates tracing messages.</span></span>|  
|`listeners`|<span data-ttu-id="87354-136">Especifica los agentes de escucha que recopilan, almacenan y enrutan los mensajes.</span><span class="sxs-lookup"><span data-stu-id="87354-136">Specifies listeners that collect, store, and route messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="87354-137">Observaciones</span><span class="sxs-lookup"><span data-stu-id="87354-137">Remarks</span></span>  

 <span data-ttu-id="87354-138">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="87354-138">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
 <span data-ttu-id="87354-139">Si no especifica el `name` atributo del agente de escucha de seguimiento, la <xref:System.Diagnostics.TraceListener.Name%2A> propiedad del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="87354-139">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> property of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="87354-140">Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y puede quitarlo si especifica una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="87354-140">If your application has only one listener, you can add it without specifying a name, and you can remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="87354-141">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar un nombre único para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales en la <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> colección.</span><span class="sxs-lookup"><span data-stu-id="87354-141">However, if your application has more than one listener, you should specify a unique name for each trace listener, which allows you to identify and manage individual trace listeners in the <xref:System.Diagnostics.TraceSource.Listeners%2A?displayProperty=nameWithType> collection.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87354-142">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado que solo se agregue a la colección un agente de escucha de seguimiento de ese tipo y nombre `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="87354-142">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="87354-143">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="87354-143">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="87354-144">El valor del `initializeData` atributo depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="87354-144">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="87354-145">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="87354-145">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="87354-146">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="87354-146">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="87354-147">Esta advertencia se produce porque la configuración se valida con respecto a la clase base abstracta <xref:System.Diagnostics.TraceListener> , que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="87354-147">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="87354-148">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="87354-148">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="87354-149">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus `initializeData` atributos.</span><span class="sxs-lookup"><span data-stu-id="87354-149">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="87354-150">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="87354-150">Trace listener class</span></span>|<span data-ttu-id="87354-151">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="87354-151">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-152">`useErrorStream`Valor del <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="87354-152">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="87354-153">Establezca el `initializeData` atributo en " `true` " para escribir el resultado de seguimiento y depuración en la secuencia de error estándar; establézcalo en " `false` " para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="87354-153">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-154">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="87354-154">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-155">Nombre de un origen existente del registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="87354-155">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-156">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="87354-156">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-157">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="87354-157">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="87354-158">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="87354-158">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="87354-159">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="87354-159">Configuration File</span></span>  

 <span data-ttu-id="87354-160">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="87354-160">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87354-161">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="87354-161">Example</span></span>  

 <span data-ttu-id="87354-162">En el ejemplo siguiente se muestra cómo utilizar `<add>` los elementos para agregar los agentes `console` de escucha y `textListener` a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="87354-162">The following example shows how to use `<add>` elements to add the listeners `console` and `textListener` to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="87354-163">El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="87354-163">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="87354-164">Vea también</span><span class="sxs-lookup"><span data-stu-id="87354-164">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="87354-165">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="87354-165">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="87354-166">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="87354-166">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
