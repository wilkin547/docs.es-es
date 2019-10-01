---
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
ms.openlocfilehash: 0ca35d9be5e1eaf36a2c9cae99efc2736ef3403d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71699205"
---
# <a name="sources-element"></a><span data-ttu-id="29176-102">\<sources >, elemento</span><span class="sxs-lookup"><span data-stu-id="29176-102">\<sources> Element</span></span>
<span data-ttu-id="29176-103">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29176-103">Specifies trace sources that initiate tracing messages.</span></span>  
  
[<span data-ttu-id="29176-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="29176-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="29176-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="29176-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="29176-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3 **\<sources >**</span><span class="sxs-lookup"><span data-stu-id="29176-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29176-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29176-107">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29176-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29176-108">Attributes and Elements</span></span>  
 <span data-ttu-id="29176-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29176-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29176-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="29176-110">Attributes</span></span>  
 <span data-ttu-id="29176-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29176-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="29176-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29176-112">Child Elements</span></span>  
  
|<span data-ttu-id="29176-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="29176-113">Element</span></span>|<span data-ttu-id="29176-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="29176-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="29176-115">\<source></span><span class="sxs-lookup"><span data-stu-id="29176-115">\<source></span></span>](source-element.md)|<span data-ttu-id="29176-116">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="29176-116">Required element.</span></span><br /><br /> <span data-ttu-id="29176-117">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29176-117">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="29176-118">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29176-118">Parent Elements</span></span>  
  
|<span data-ttu-id="29176-119">Elemento</span><span class="sxs-lookup"><span data-stu-id="29176-119">Element</span></span>|<span data-ttu-id="29176-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="29176-120">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29176-121">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29176-121">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="29176-122">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29176-122">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29176-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29176-123">Remarks</span></span>  
 <span data-ttu-id="29176-124">Este elemento se puede usar en el archivo de configuración del equipo (Machine. config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29176-124">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29176-125">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29176-125">Example</span></span>  
 <span data-ttu-id="29176-126">En el ejemplo siguiente se muestra cómo utilizar el elemento `<sources>` para agregar el origen de seguimiento `mySource` y para establecer el nivel del modificador de origen denominado `sourceSwitch`.</span><span class="sxs-lookup"><span data-stu-id="29176-126">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="29176-127">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="29176-127">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29176-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="29176-128">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="29176-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="29176-129">Trace and Debug Settings Schema</span></span>](index.md)
- [<span data-ttu-id="29176-130">\<source></span><span class="sxs-lookup"><span data-stu-id="29176-130">\<source></span></span>](source-element.md)
