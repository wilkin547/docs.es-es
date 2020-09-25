---
title: <switches> (Elemento)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
ms.openlocfilehash: bdd6efdec1e118075495002509c7367c1162baba
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176102"
---
# <a name="switches-element"></a><span data-ttu-id="6db59-102">\<switches> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="6db59-102">\<switches> Element</span></span>

<span data-ttu-id="6db59-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="6db59-103">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="6db59-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6db59-104">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6db59-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="6db59-105">Attributes and Elements</span></span>  

 <span data-ttu-id="6db59-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="6db59-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6db59-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="6db59-107">Attributes</span></span>  

 <span data-ttu-id="6db59-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="6db59-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="6db59-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="6db59-109">Child Elements</span></span>  
  
|<span data-ttu-id="6db59-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="6db59-110">Element</span></span>|<span data-ttu-id="6db59-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="6db59-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="6db59-112">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6db59-112">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="6db59-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="6db59-113">Parent Elements</span></span>  
  
|<span data-ttu-id="6db59-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="6db59-114">Element</span></span>|<span data-ttu-id="6db59-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="6db59-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="6db59-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6db59-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="6db59-117">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="6db59-117">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6db59-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6db59-118">Remarks</span></span>  

 <span data-ttu-id="6db59-119">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="6db59-119">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="6db59-120">Si el modificador es <xref:System.Diagnostics.BooleanSwitch> , puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="6db59-120">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="6db59-121">Si el modificador es un <xref:System.Diagnostics.TraceSwitch> , puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6db59-121">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6db59-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="6db59-122">Example</span></span>  

 <span data-ttu-id="6db59-123">En el ejemplo siguiente se muestra cómo utilizar el **\<switch>** elemento para establecer el `General` modificador de seguimiento en el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="6db59-123">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
```xml  
<configuration>  
   <system.diagnostics>  
      <switches>  
         <add name="General" value="4" />  
         <add name="Data" value="1" />  
      </switches>  
   </system.diagnostics>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6db59-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6db59-124">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="6db59-125">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="6db59-125">Trace and Debug Settings Schema</span></span>](index.md)
