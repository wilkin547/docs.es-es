---
description: 'Más información acerca de: <switches> elemento'
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
ms.openlocfilehash: d0ffdf2bdc4dacd157d09d34c40063b687595e3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99750525"
---
# <a name="switches-element"></a><span data-ttu-id="35b99-103">\<switches> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="35b99-103">\<switches> Element</span></span>

<span data-ttu-id="35b99-104">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="35b99-104">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="35b99-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35b99-105">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35b99-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="35b99-106">Attributes and Elements</span></span>  

 <span data-ttu-id="35b99-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="35b99-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35b99-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="35b99-108">Attributes</span></span>  

 <span data-ttu-id="35b99-109">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="35b99-109">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="35b99-110">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="35b99-110">Child Elements</span></span>  
  
|<span data-ttu-id="35b99-111">Elemento</span><span class="sxs-lookup"><span data-stu-id="35b99-111">Element</span></span>|<span data-ttu-id="35b99-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="35b99-112">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="35b99-113">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="35b99-113">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35b99-114">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="35b99-114">Parent Elements</span></span>  
  
|<span data-ttu-id="35b99-115">Elemento</span><span class="sxs-lookup"><span data-stu-id="35b99-115">Element</span></span>|<span data-ttu-id="35b99-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="35b99-116">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="35b99-117">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="35b99-117">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="35b99-118">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="35b99-118">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35b99-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35b99-119">Remarks</span></span>  

 <span data-ttu-id="35b99-120">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="35b99-120">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="35b99-121">Si el modificador es <xref:System.Diagnostics.BooleanSwitch> , puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="35b99-121">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="35b99-122">Si el modificador es un <xref:System.Diagnostics.TraceSwitch> , puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="35b99-122">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35b99-123">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="35b99-123">Example</span></span>  

 <span data-ttu-id="35b99-124">En el ejemplo siguiente se muestra cómo utilizar el **\<switch>** elemento para establecer el `General` modificador de seguimiento en el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="35b99-124">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="35b99-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="35b99-125">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="35b99-126">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="35b99-126">Trace and Debug Settings Schema</span></span>](index.md)
