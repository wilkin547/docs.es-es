---
title: <add>(Elemento <listeners> ) para<trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/add
helpviewer_keywords:
- initializeData attribute
- <add> element for <listeners>
- add element for <listeners>
ms.assetid: 81e804a3-ef11-4d39-bbde-bfa012c179e2
ms.openlocfilehash: c64673908dc9afe67d97c08f93e5b9d9533bd34d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153677"
---
# <a name="add-element-for-listeners-for-trace"></a><span data-ttu-id="0075c-102">\<add>(Elemento \<listeners> ) para\<trace></span><span class="sxs-lookup"><span data-stu-id="0075c-102">\<add> Element for \<listeners> for \<trace></span></span>
<span data-ttu-id="0075c-103">Agrega un agente de escucha a la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="0075c-103">Adds a listener to the **Listeners** collection.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<listeners>**](listeners-element-for-trace.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="0075c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0075c-104">Syntax</span></span>  
  
```xml  
<add name="name"
     type="trace listener class name, Version, Culture, PublicKeyToken"  
     initializeData="data"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0075c-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="0075c-105">Attributes and Elements</span></span>  
 <span data-ttu-id="0075c-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="0075c-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0075c-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="0075c-107">Attributes</span></span>  
  
|<span data-ttu-id="0075c-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="0075c-108">Attribute</span></span>|<span data-ttu-id="0075c-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="0075c-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0075c-110">**type**</span><span class="sxs-lookup"><span data-stu-id="0075c-110">**type**</span></span>|<span data-ttu-id="0075c-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="0075c-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="0075c-112">Especifica el tipo del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="0075c-112">Specifies the type of the listener.</span></span> <span data-ttu-id="0075c-113">Debe utilizar una cadena que cumpla los requisitos especificados en [especificar nombres de tipo completos](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span><span class="sxs-lookup"><span data-stu-id="0075c-113">You must use a string that meets the requirements specified in [Specifying Fully Qualified Type Names](../../../reflection-and-codedom/specifying-fully-qualified-type-names.md).</span></span>|  
|<span data-ttu-id="0075c-114">**initializeData**</span><span class="sxs-lookup"><span data-stu-id="0075c-114">**initializeData**</span></span>|<span data-ttu-id="0075c-115">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0075c-115">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0075c-116">Cadena pasada al constructor de la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="0075c-116">The string passed to the constructor for the specified class.</span></span>|  
|<span data-ttu-id="0075c-117">**name**</span><span class="sxs-lookup"><span data-stu-id="0075c-117">**name**</span></span>|<span data-ttu-id="0075c-118">Atributo opcional.</span><span class="sxs-lookup"><span data-stu-id="0075c-118">Optional attribute.</span></span><br /><br /> <span data-ttu-id="0075c-119">Especifica el nombre del agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="0075c-119">Specifies the name of the listener.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0075c-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="0075c-120">Child Elements</span></span>  
  
|<span data-ttu-id="0075c-121">Elemento</span><span class="sxs-lookup"><span data-stu-id="0075c-121">Element</span></span>|<span data-ttu-id="0075c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="0075c-122">Description</span></span>|  
|-------------|-----------------|  
|[\<filter>](filter-element-for-add-for-listeners-for-trace.md)|<span data-ttu-id="0075c-123">Agrega un filtro a un agente de escucha de la `Listeners` colección para un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0075c-123">Adds a filter to a listener in the `Listeners` collection for a trace.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0075c-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="0075c-124">Parent Elements</span></span>  
  
|<span data-ttu-id="0075c-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="0075c-125">Element</span></span>|<span data-ttu-id="0075c-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="0075c-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="0075c-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0075c-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`listeners`|<span data-ttu-id="0075c-128">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="0075c-128">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="0075c-129">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="0075c-129">Listeners direct the tracing output to an appropriate target.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="0075c-130">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="0075c-130">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="0075c-131">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0075c-131">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0075c-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0075c-132">Remarks</span></span>  
 <span data-ttu-id="0075c-133">Las <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> clases y comparten la misma colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="0075c-133">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="0075c-134">Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase utiliza el mismo agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="0075c-134">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="0075c-135">Las clases de agente de escucha derivan de <xref:System.Diagnostics.TraceListener> .</span><span class="sxs-lookup"><span data-stu-id="0075c-135">The listener classes derive from the <xref:System.Diagnostics.TraceListener>.</span></span>  
  
 <span data-ttu-id="0075c-136">Si no se especifica el `name` atributo del agente de escucha de seguimiento, el <xref:System.Diagnostics.TraceListener.Name%2A> del agente de escucha de seguimiento tiene como valor predeterminado una cadena vacía ("").</span><span class="sxs-lookup"><span data-stu-id="0075c-136">If you do not specify the `name` attribute of the trace listener, the <xref:System.Diagnostics.TraceListener.Name%2A> of the trace listener defaults to an empty string ("").</span></span> <span data-ttu-id="0075c-137">Si la aplicación tiene solo un agente de escucha, puede agregarlo sin especificar un nombre y quitarlo especificando una cadena vacía para el nombre.</span><span class="sxs-lookup"><span data-stu-id="0075c-137">If your application has only one listener, you can add it without specifying a name, and remove it by specifying an empty string for the name.</span></span> <span data-ttu-id="0075c-138">Sin embargo, si la aplicación tiene más de un agente de escucha, debe especificar nombres únicos para cada agente de escucha de seguimiento, lo que le permite identificar y administrar agentes de escucha de seguimiento individuales dentro de las <xref:System.Diagnostics.Debug.Listeners%2A> <xref:System.Diagnostics.Trace.Listeners%2A> colecciones y.</span><span class="sxs-lookup"><span data-stu-id="0075c-138">However, if your application has more than one listener, you should specify unique names for each trace listener, which allows you to identify and manage individual trace listeners within the <xref:System.Diagnostics.Debug.Listeners%2A> and <xref:System.Diagnostics.Trace.Listeners%2A> collections.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0075c-139">Agregar más de un agente de escucha de seguimiento del mismo tipo y con el mismo nombre da como resultado que solo se agregue a la colección un agente de escucha de seguimiento de ese tipo y nombre `Listeners` .</span><span class="sxs-lookup"><span data-stu-id="0075c-139">Adding more than one trace listener of the same type and with the same name results in only one trace listener of that type and name being added to the `Listeners` collection.</span></span> <span data-ttu-id="0075c-140">Sin embargo, puede agregar mediante programación varios agentes de escucha idénticos a la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="0075c-140">However, you can programmatically add multiple identical listeners to the `Listeners` collection.</span></span>  
  
 <span data-ttu-id="0075c-141">El valor del atributo **initializeData** depende del tipo de agente de escucha que se cree.</span><span class="sxs-lookup"><span data-stu-id="0075c-141">The value for the **initializeData** attribute depends on the type of listener you create.</span></span> <span data-ttu-id="0075c-142">No todos los agentes de escucha de seguimiento requieren que se especifique **initializeData**.</span><span class="sxs-lookup"><span data-stu-id="0075c-142">Not all trace listeners require that you specify **initializeData**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0075c-143">Al usar el `initializeData` atributo, puede obtener la advertencia del compilador "el atributo ' initializeData ' no se ha declarado".</span><span class="sxs-lookup"><span data-stu-id="0075c-143">When you use the `initializeData` attribute, you may get the compiler warning "The 'initializeData' attribute is not declared."</span></span> <span data-ttu-id="0075c-144">Esta advertencia se produce porque la configuración se valida con respecto a la clase base abstracta <xref:System.Diagnostics.TraceListener> , que no reconoce el `initializeData` atributo.</span><span class="sxs-lookup"><span data-stu-id="0075c-144">This warning occurs because the configuration settings are validated against the abstract base class <xref:System.Diagnostics.TraceListener>, which does not recognize the `initializeData` attribute.</span></span> <span data-ttu-id="0075c-145">Normalmente, puede omitir esta advertencia para las implementaciones del agente de escucha de seguimiento que tienen un constructor que toma un parámetro.</span><span class="sxs-lookup"><span data-stu-id="0075c-145">Typically, you can ignore this warning for trace listener implementations that have a constructor that takes a parameter.</span></span>  
  
 <span data-ttu-id="0075c-146">En la tabla siguiente se muestran los agentes de escucha de seguimiento incluidos en el .NET Framework y se describe el valor de sus atributos **initializeData** .</span><span class="sxs-lookup"><span data-stu-id="0075c-146">The following table shows the trace listeners that are included with the .NET Framework and describes the value of their **initializeData** attributes.</span></span>  
  
|<span data-ttu-id="0075c-147">Clase de agente de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0075c-147">Trace listener class</span></span>|<span data-ttu-id="0075c-148">valor del atributo initializeData</span><span class="sxs-lookup"><span data-stu-id="0075c-148">initializeData attribute value</span></span>|  
|--------------------------|------------------------------------|  
|<xref:System.Diagnostics.ConsoleTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-149">`useErrorStream`Valor del <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span><span class="sxs-lookup"><span data-stu-id="0075c-149">The `useErrorStream` value for the <xref:System.Diagnostics.ConsoleTraceListener.%23ctor%2A> constructor.</span></span>  <span data-ttu-id="0075c-150">Establezca el `initializeData` atributo en " `true` " para escribir el resultado de seguimiento y de depuración en <xref:System.Console.Error%2A?displayProperty=nameWithType> ; " `false` " para escribir en <xref:System.Console.Out%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="0075c-150">Set the `initializeData` attribute to "`true`" to write trace and debug output to <xref:System.Console.Error%2A?displayProperty=nameWithType>; "`false`" to write to <xref:System.Console.Out%2A?displayProperty=nameWithType>.</span></span>|  
|<xref:System.Diagnostics.DelimitedListTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-151">Nombre del archivo en el que <xref:System.Diagnostics.DelimitedListTraceListener> va a escribir.</span><span class="sxs-lookup"><span data-stu-id="0075c-151">The name of the file the <xref:System.Diagnostics.DelimitedListTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.EventLogTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-152">Nombre del nombre de un origen de registro de eventos existente.</span><span class="sxs-lookup"><span data-stu-id="0075c-152">The name of the name of an existing event log source.</span></span>|  
|<xref:System.Diagnostics.EventSchemaTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-153">Nombre del archivo en el que <xref:System.Diagnostics.EventSchemaTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="0075c-153">The name of the file that the <xref:System.Diagnostics.EventSchemaTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.TextWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-154">Nombre del archivo en el que <xref:System.Diagnostics.TextWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="0075c-154">The name of the file that the <xref:System.Diagnostics.TextWriterTraceListener> writes to.</span></span>|  
|<xref:System.Diagnostics.XmlWriterTraceListener?displayProperty=nameWithType>|<span data-ttu-id="0075c-155">Nombre del archivo en el que <xref:System.Diagnostics.XmlWriterTraceListener> escribe.</span><span class="sxs-lookup"><span data-stu-id="0075c-155">The name of the file that the <xref:System.Diagnostics.XmlWriterTraceListener> writes to.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0075c-156">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="0075c-156">Example</span></span>  
 <span data-ttu-id="0075c-157">En el ejemplo siguiente se muestra cómo usar **\<add>** los elementos para agregar los agentes de escucha `MyListener` y `MyEventListener` la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="0075c-157">The following example shows how to use **\<add>** elements to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="0075c-158">`MyListener`crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="0075c-158">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="0075c-159">`MyEventListener`crea una entrada en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="0075c-159">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <trace autoflush="true" indentsize="0">  
         <listeners>  
            <add name="myListener" type="System.Diagnostics.TextWriterTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" initializeData="c:\myListener.log" />  
            <add name="MyEventListener"  
                 type="System.Diagnostics.EventLogTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"                 initializeData="MyConfigEventLog"/>  
            <add name="configConsoleListener"  
                 type="System.Diagnostics.ConsoleTraceListener, system, version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"/>  
         </listeners>  
      </trace>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0075c-160">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0075c-160">See also</span></span>

- <xref:System.Diagnostics.Trace>
- <xref:System.Diagnostics.Debug>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- [<span data-ttu-id="0075c-161">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="0075c-161">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="0075c-162">Agentes de escucha de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0075c-162">Trace Listeners</span></span>](../../../debug-trace-profile/trace-listeners.md)
