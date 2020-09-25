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
ms.openlocfilehash: f0ede5f9dc19e9589afc888e7fcd01785bc1840c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91174035"
---
# <a name="add-element-for-sharedlisteners"></a><span data-ttu-id="ba347-102">Elemento \<add> para \<sharedListeners></span><span class="sxs-lookup"><span data-stu-id="ba347-102">\<add> Element for \<sharedListeners></span></span>

<span data-ttu-id="ba347-103">Agrega un agente de escucha a la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ba347-103">Adds a listener to the `sharedListeners` collection.</span></span> <span data-ttu-id="ba347-104">`sharedListeners` es una colección de agentes de escucha a los que [\<source>](source-element.md) [\<trace>](trace-element.md) puede hacer referencia cualquier o.</span><span class="sxs-lookup"><span data-stu-id="ba347-104">`sharedListeners` is a collection of listeners that any [\<source>](source-element.md) or [\<trace>](trace-element.md) can reference.</span></span>  <span data-ttu-id="ba347-105">De forma predeterminada, los agentes de escucha de la `sharedListeners` colección no se colocan en una `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="ba347-105">By default, listeners in the `sharedListeners` collection are not placed in a `Listeners` collection.</span></span> <span data-ttu-id="ba347-106">Se deben agregar por nombre a [\<source>](source-element.md) o [\<trace>](trace-element.md) .</span><span class="sxs-lookup"><span data-stu-id="ba347-106">They must be added by name to the [\<source>](source-element.md) or [\<trace>](trace-element.md).</span></span> <span data-ttu-id="ba347-107">No es posible obtener los agentes de escucha de la `sharedListeners` colección en el código en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ba347-107">It is not possible to get the listeners in the `sharedListeners` collection in code at run time.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<sharedListeners>**](sharedlisteners-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="ba347-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ba347-108">Syntax</span></span>  
  
```xml  
<add name="name"
  type="TraceListenerClassName, Version, Culture, PublicKeyToken"  
  initializeData="data"
  traceOutputOptions = "None"
/>  
```
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ba347-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ba347-109">Attributes and Elements</span></span>  

 <span data-ttu-id="ba347-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ba347-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ba347-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="ba347-111">Attributes</span></span>  
  
|<span data-ttu-id="ba347-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="ba347-112">Attribute</span></span>|<span data-ttu-id="ba347-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba347-113">Description</span></span>|  
|---------------|-----------------|  
|`name`|<span data-ttu-id="ba347-114">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ba347-114">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba347-115">Especifica el nombre del agente de escucha que se usa para agregar el agente de escucha compartido a una `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="ba347-115">Specifies the name of the listener that is used to add the shared listener to a `Listeners` collection.</span></span>|  
|`type`|<span data-ttu-id="ba347-116">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ba347-116">Required attribute.</span></span><br /><br /> <span data-ttu-id="ba347-117">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="ba347-117">Specifies the type of the listener.</span></span> <span data-ttu-id="ba347-118">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="ba347-118">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|`initializeData`|<span data-ttu-id="ba347-119">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ba347-119">Optional attribute.</span></span><br /><br /> <span data-ttu-id="ba347-120">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="ba347-120">The string passed to the constructor for the specified class.</span></span>|  
|`traceOutputOptions`|<span data-ttu-id="ba347-121">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="ba347-121">Optional attribute.</span></span><br/><br/><span data-ttu-id="ba347-122">Representación de cadena de uno o más <xref:System.Diagnostics.TraceOptions> miembros de la enumeración que indica los datos que se van a escribir en el resultado del seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba347-122">The string representation of one or more <xref:System.Diagnostics.TraceOptions> enumeration members that indicates the data to be written to the trace output.</span></span> <span data-ttu-id="ba347-123">Varios elementos se separan mediante comas.</span><span class="sxs-lookup"><span data-stu-id="ba347-123">Multiple items are separated by commas.</span></span> <span data-ttu-id="ba347-124">El valor predeterminado es "none".</span><span class="sxs-lookup"><span data-stu-id="ba347-124">The default value is "None".</span></span>|

### <a name="child-elements"></a><span data-ttu-id="ba347-125">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ba347-125">Child Elements</span></span>  
  
|<span data-ttu-id="ba347-126">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba347-126">Element</span></span>|<span data-ttu-id="ba347-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba347-127">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-sharedlisteners.md)|<span data-ttu-id="ba347-128">Agrega un filtro a un agente de escucha en la colección `sharedListeners`.</span><span class="sxs-lookup"><span data-stu-id="ba347-128">Adds a filter to a listener in the `sharedListeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="ba347-129">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ba347-129">Parent Elements</span></span>  
  
|<span data-ttu-id="ba347-130">Elemento</span><span class="sxs-lookup"><span data-stu-id="ba347-130">Element</span></span>|<span data-ttu-id="ba347-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="ba347-131">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ba347-132">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ba347-132">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="ba347-133">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba347-133">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
|`sharedListeners`|<span data-ttu-id="ba347-134">Colección de agentes de escucha a los que puede hacer referencia cualquier origen o elemento de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba347-134">A collection of listeners that any source or trace element can reference.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ba347-135">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ba347-135">Remarks</span></span>  

 <span data-ttu-id="ba347-136">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="ba347-136">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span> <span data-ttu-id="ba347-137">El valor del `name` atributo se usa para agregar el agente de escucha compartido a una `Listeners` colección para un seguimiento o un origen de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ba347-137">The value for the `name` attribute is used to add the shared listener to a `Listeners` collection for either a trace or a trace source.</span></span> <span data-ttu-id="ba347-138">El valor del `initializeData` atributo depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="ba347-138">The value for the `initializeData` attribute depends on the type of listener you create.</span></span> <span data-ttu-id="ba347-139">No todos los agentes de escucha de seguimiento requieren que se especifique `initializeData` .</span><span class="sxs-lookup"><span data-stu-id="ba347-139">Not all trace listeners require that you specify `initializeData`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ba347-140">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="ba347-140">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="ba347-141">Esta advertencia se produce porque la configuración se valida con respecto a la clase base abstracta <xref:System.Diagnostics.TraceListener> , que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="ba347-141">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="ba347-142">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="ba347-142">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="ba347-143">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus `initializeData` atributos.</span><span class="sxs-lookup"><span data-stu-id="ba347-143">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their `initializeData` attributes.</span></span>  
  
|<span data-ttu-id="ba347-144">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ba347-144">Trace listener class</span></span>|<span data-ttu-id="ba347-145">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="ba347-145">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener>|<span data-ttu-id="ba347-146">`useErrorStream`Valor del <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="ba347-146">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="ba347-147">Establezca el `initializeData` atributo en " `true` " para escribir el resultado de seguimiento y depuración en la secuencia de error estándar; establézcalo en " `false` " para escribir en el flujo de salida estándar.</span><span class="sxs-lookup"><span data-stu-id="ba347-147">Set the `initializeData` attribute to "`true`" to write trace and debug output to the standard error stream; set it to "`false`" to write to the standard output stream.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener>|<span data-ttu-id="ba347-148">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="ba347-148">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba347-149">Nombre de un origen existente del registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="ba347-149">The name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba347-150">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="ba347-150">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="ba347-151">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="ba347-151">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener>|<span data-ttu-id="ba347-152">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="ba347-152">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="configuration-file"></a><span data-ttu-id="ba347-153">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="ba347-153">Configuration File</span></span>  

 <span data-ttu-id="ba347-154">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ba347-154">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ba347-155">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ba347-155">Example</span></span>  

 <span data-ttu-id="ba347-156">En el ejemplo siguiente se muestra cómo utilizar `<add>` los elementos para agregar <xref:System.Diagnostics.TextWriterTraceListener> `textListener` a la `sharedListeners` colección.</span><span class="sxs-lookup"><span data-stu-id="ba347-156">The following example shows how to use `<add>` elements to add the <xref:System.Diagnostics.TextWriterTraceListener>`textListener` to the `sharedListeners` collection.</span></span>   <span data-ttu-id="ba347-157">`textListener` se agrega por nombre a la `Listeners` colección para el origen de seguimiento `TraceSourceApp` .</span><span class="sxs-lookup"><span data-stu-id="ba347-157">`textListener` is added by name to the `Listeners` collection for the trace source `TraceSourceApp`.</span></span> <span data-ttu-id="ba347-158">El `textListener` agente de escucha escribe la salida del seguimiento en el archivo myListener. log.</span><span class="sxs-lookup"><span data-stu-id="ba347-158">The `textListener` listener writes trace output to the file myListener.log.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ba347-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ba347-159">See also</span></span>

- <xref:System.Diagnostics.TraceSource>
- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="ba347-160">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="ba347-160">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="ba347-161">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ba347-161">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
