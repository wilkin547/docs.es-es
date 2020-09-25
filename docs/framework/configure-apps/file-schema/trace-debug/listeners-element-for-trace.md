---
title: Elemento <listeners> para <trace>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners
helpviewer_keywords:
- <listeners> element
- listeners element
ms.assetid: 1394c2c3-6304-46db-87c1-8e8b16f5ad5b
ms.openlocfilehash: 59d078f8dc573a1ce949d225f497dd4500fe808f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173866"
---
# <a name="listeners-element-for-trace"></a><span data-ttu-id="b0c32-102">Elemento \<listeners> para \<trace></span><span class="sxs-lookup"><span data-stu-id="b0c32-102">\<listeners> Element for \<trace></span></span>

<span data-ttu-id="b0c32-103">Especifica un agente de escucha que recopila, almacena y enruta los mensajes.</span><span class="sxs-lookup"><span data-stu-id="b0c32-103">Specifies a listener that collects, stores, and routes messages.</span></span> <span data-ttu-id="b0c32-104">Los agentes de escucha dirigen los resultados del seguimiento a un destino adecuado.</span><span class="sxs-lookup"><span data-stu-id="b0c32-104">Listeners direct the tracing output to an appropriate target.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<trace>**](trace-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<listeners>**

## <a name="syntax"></a><span data-ttu-id="b0c32-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b0c32-105">Syntax</span></span>  
  
```xml  
<listeners>
  <add>...</add>  
  <clear/>  
  <remove ... />  
</listeners>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b0c32-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="b0c32-106">Attributes and Elements</span></span>  

 <span data-ttu-id="b0c32-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="b0c32-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b0c32-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="b0c32-108">Attributes</span></span>  

 <span data-ttu-id="b0c32-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="b0c32-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="b0c32-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="b0c32-110">Child Elements</span></span>  
  
|<span data-ttu-id="b0c32-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0c32-111">Element</span></span>|<span data-ttu-id="b0c32-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0c32-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-listeners-for-trace.md)|<span data-ttu-id="b0c32-113">Agrega un agente de escucha a la colección `Listeners`.</span><span class="sxs-lookup"><span data-stu-id="b0c32-113">Adds a listener to the `Listeners` collection.</span></span>|  
|[\<clear>](clear-element-for-listeners-for-trace.md)|<span data-ttu-id="b0c32-114">Borra la colección `Listeners` de un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0c32-114">Clears the `Listeners` collection for trace.</span></span>|  
|[\<remove>](remove-element-for-listeners-for-trace.md)|<span data-ttu-id="b0c32-115">Quita un agente de escucha de la `Listeners` colección.</span><span class="sxs-lookup"><span data-stu-id="b0c32-115">Removes a listener from the `Listeners` collection.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="b0c32-116">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="b0c32-116">Parent Elements</span></span>  
  
|<span data-ttu-id="b0c32-117">Elemento</span><span class="sxs-lookup"><span data-stu-id="b0c32-117">Element</span></span>|<span data-ttu-id="b0c32-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0c32-118">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="b0c32-119">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0c32-119">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="b0c32-120">Especifica el elemento raíz de la sección de configuración de ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="b0c32-120">Specifies the root element for the ASP.NET configuration section.</span></span>|  
|`trace`|<span data-ttu-id="b0c32-121">Contiene agentes de escucha que recopilan, almacenan y enrutan los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="b0c32-121">Contains listeners that collect, store, and route tracing messages.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0c32-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b0c32-122">Remarks</span></span>  

 <span data-ttu-id="b0c32-123">Las <xref:System.Diagnostics.Debug> <xref:System.Diagnostics.Trace> clases y comparten la misma colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="b0c32-123">The <xref:System.Diagnostics.Debug> and <xref:System.Diagnostics.Trace> classes share the same **Listeners** collection.</span></span> <span data-ttu-id="b0c32-124">Si agrega un objeto de escucha a la colección en una de estas clases, la otra clase utiliza el mismo agente de escucha.</span><span class="sxs-lookup"><span data-stu-id="b0c32-124">If you add a listener object to the collection in one of these classes, the other class uses the same listener.</span></span> <span data-ttu-id="b0c32-125">Las clases de agente de escucha incluidas con el .NET Framework derivan de la <xref:System.Diagnostics.TraceListener> clase.</span><span class="sxs-lookup"><span data-stu-id="b0c32-125">The listener classes shipped with the .NET Framework derive from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
## <a name="configuration-file"></a><span data-ttu-id="b0c32-126">Archivo de configuración</span><span class="sxs-lookup"><span data-stu-id="b0c32-126">Configuration File</span></span>  

 <span data-ttu-id="b0c32-127">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0c32-127">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0c32-128">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="b0c32-128">Example</span></span>  

 <span data-ttu-id="b0c32-129">En el ejemplo siguiente se muestra cómo usar el **\<listeners>** elemento para agregar los agentes de escucha `MyListener` y `MyEventListener` a la colección **Listeners** .</span><span class="sxs-lookup"><span data-stu-id="b0c32-129">The following example shows how to use the **\<listeners>** element to add the listeners `MyListener` and `MyEventListener` to the **Listeners** collection.</span></span> <span data-ttu-id="b0c32-130">`MyListener` crea un archivo denominado `MyListener.log` y escribe el resultado en el archivo.</span><span class="sxs-lookup"><span data-stu-id="b0c32-130">`MyListener` creates a file called `MyListener.log` and writes the output to the file.</span></span> <span data-ttu-id="b0c32-131">`MyEventListener` crea una entrada en el registro de eventos.</span><span class="sxs-lookup"><span data-stu-id="b0c32-131">`MyEventListener` creates an entry in the event log.</span></span>  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="true" indentsize="0">  
      <listeners>  
        <add name="myListener"
          type="System.Diagnostics.TextWriterTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"
          initializeData="c:\myListener.log" />  
        <add name="MyEventListener"  
          type="System.Diagnostics.EventLogTraceListener,
            system, version=1.0.3300.0, Culture=neutral,
            PublicKeyToken=b77a5c561934e089"  
          initializeData="MyConfigEventLog"/>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b0c32-132">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b0c32-132">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- [<span data-ttu-id="b0c32-133">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="b0c32-133">Trace and Debug Settings Schema</span></span>](index.md)
