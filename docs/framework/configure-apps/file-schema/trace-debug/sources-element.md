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
ms.openlocfilehash: 670fb359f892d83feac56c849361c4b980d9a922
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173814"
---
# <a name="sources-element"></a><span data-ttu-id="4b808-102">\<sources> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="4b808-102">\<sources> Element</span></span>

<span data-ttu-id="4b808-103">Especifica los orígenes de seguimiento que inician los mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4b808-103">Specifies trace sources that initiate tracing messages.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<sources>**

## <a name="syntax"></a><span data-ttu-id="4b808-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b808-104">Syntax</span></span>  
  
```xml  
<sources>  
   <source>...</source>  
</sources>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4b808-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="4b808-105">Attributes and Elements</span></span>  

 <span data-ttu-id="4b808-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="4b808-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4b808-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="4b808-107">Attributes</span></span>  

 <span data-ttu-id="4b808-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="4b808-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="4b808-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="4b808-109">Child Elements</span></span>  
  
|<span data-ttu-id="4b808-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b808-110">Element</span></span>|<span data-ttu-id="4b808-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b808-111">Description</span></span>|  
|-------------|-----------------|  
|[\<source>](source-element.md)|<span data-ttu-id="4b808-112">Elemento necesario.</span><span class="sxs-lookup"><span data-stu-id="4b808-112">Required element.</span></span><br /><br /> <span data-ttu-id="4b808-113">Contiene un origen de seguimiento que inicia mensajes de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4b808-113">Specifies a trace source that initiates tracing messages.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4b808-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="4b808-114">Parent Elements</span></span>  
  
|<span data-ttu-id="4b808-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="4b808-115">Element</span></span>|<span data-ttu-id="4b808-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b808-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="4b808-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b808-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="4b808-118">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="4b808-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b808-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b808-119">Remarks</span></span>  

 <span data-ttu-id="4b808-120">Este elemento se puede usar en el archivo de configuración del equipo (Machine.config) y en el archivo de configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4b808-120">This element can be used in the machine configuration file (Machine.config) and the application configuration file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b808-121">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4b808-121">Example</span></span>  

 <span data-ttu-id="4b808-122">En el ejemplo siguiente se muestra cómo utilizar el `<sources>` elemento para agregar el origen de seguimiento `mySource` y establecer el nivel para el modificador de origen denominado `sourceSwitch` .</span><span class="sxs-lookup"><span data-stu-id="4b808-122">The following example shows how to use the `<sources>` element to add the trace source `mySource` and to set the level for the source switch named `sourceSwitch`.</span></span> <span data-ttu-id="4b808-123">Se agrega un agente de escucha de seguimiento de consola que escribe información de seguimiento en la consola.</span><span class="sxs-lookup"><span data-stu-id="4b808-123">A console trace listener is added that writes trace information to the console.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4b808-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4b808-124">See also</span></span>

- <xref:System.Diagnostics.TraceListener>
- <xref:System.Diagnostics.DefaultTraceListener>
- <xref:System.Diagnostics.TextWriterTraceListener>
- <xref:System.Diagnostics.ConsoleTraceListener>
- <xref:System.Diagnostics.EventLogTraceListener>
- <xref:System.Diagnostics.XmlWriterTraceListener>
- [<span data-ttu-id="4b808-125">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="4b808-125">Trace and Debug Settings Schema</span></span>](index.md)
- [\<source>](source-element.md)
