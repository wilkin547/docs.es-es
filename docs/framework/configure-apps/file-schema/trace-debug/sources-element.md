---
description: 'Más información acerca de: <sources> elemento'
title: <sources> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/sources
- http://schemas.microsoft.com/.NetConfiguration/v2.0#sources
helpviewer_keywords:
- sources element
- trace sources
- <sources> element
ms.assetid: c727b2e2-423a-4463-a223-013f40ff16a3
ms.openlocfilehash: 8e5bf2af74d80cf7766de0992623d4792f17bf37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750551"
---
# <a name="sources-element"></a><span data-ttu-id="a3a22-103">\<sources> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="a3a22-103">\<sources> Element</span></span>

<span data-ttu-id="a3a22-104">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a3a22-104">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="a3a22-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3a22-105">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3a22-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="a3a22-106">Attributes and Elements</span></span>  

 <span data-ttu-id="a3a22-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="a3a22-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3a22-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="a3a22-108">Attributes</span></span>  

 <span data-ttu-id="a3a22-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="a3a22-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a3a22-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="a3a22-110">Child Elements</span></span>  
  
|<span data-ttu-id="a3a22-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3a22-111">Element</span></span>|<span data-ttu-id="a3a22-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3a22-112">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="a3a22-113">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="a3a22-113">Required element.</span></span><br /><br /> <span data-ttu-id="a3a22-114">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a3a22-114">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a3a22-115">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="a3a22-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a3a22-116">Elemento</span><span class="sxs-lookup"><span data-stu-id="a3a22-116">Element</span></span>|<span data-ttu-id="a3a22-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3a22-117">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="a3a22-118">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a3a22-118">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="a3a22-119">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="a3a22-119">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3a22-120">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3a22-120">Remarks</span></span>  

 <span data-ttu-id="a3a22-121">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a3a22-121">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a3a22-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a3a22-122">Example</span></span>  

 <span data-ttu-id="a3a22-123">En el ejemplo siguiente se muestra cómo utilizar el `<sources>` elemento para agregar el origen de seguimiento `mySource` y establecer el nivel para el modificador de origen denominado `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="a3a22-123">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="a3a22-124">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="a3a22-124">A console trace listener is added that writes trace information to the console.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <sources>  
         <source name="mySource" switchName="sourceSwitch"
            switchType="System.Diagnostics.SourceSwitch"  >  
            <listeners>  
               <add name="console"
                  type="System.Diagnostics.ConsoleTraceListener" >  
                  <filter type="System.Diagnostics.EventTypeFilter"
                     initializeData="Error" />  
               </add>  
               <remove name="Default" />  
            </listeners>  
         </source>  
      </sources>  
      <switches>  
         <add name="sourceSwitch" value="Warning" />  
      </switches>
   </system.diagnostics>
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a3a22-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3a22-125">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="a3a22-126">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="a3a22-126">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
