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
ms.openlocfilehash: 15cc9680d7a20341eb5d1d1df302c1e034e70e02
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "79153235"
---
# <a name="switches-element"></a><span data-ttu-id="c1367-102">\<switches> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="c1367-102">\<switches> Element</span></span>
<span data-ttu-id="c1367-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="c1367-103">Contains trace switches and the level where the trace switches are set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**

## <a name="syntax"></a><span data-ttu-id="c1367-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1367-104">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1367-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="c1367-105">Attributes and Elements</span></span>  
 <span data-ttu-id="c1367-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="c1367-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1367-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="c1367-107">Attributes</span></span>  
 <span data-ttu-id="c1367-108">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="c1367-108">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="c1367-109">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="c1367-109">Child Elements</span></span>  
  
|<span data-ttu-id="c1367-110">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1367-110">Element</span></span>|<span data-ttu-id="c1367-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1367-111">Description</span></span>|  
|-------------|-----------------|  
|[\<add>](add-element-for-switches.md)|<span data-ttu-id="c1367-112">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c1367-112">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="c1367-113">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="c1367-113">Parent Elements</span></span>  
  
|<span data-ttu-id="c1367-114">Elemento</span><span class="sxs-lookup"><span data-stu-id="c1367-114">Element</span></span>|<span data-ttu-id="c1367-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="c1367-115">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="c1367-116">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c1367-116">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="c1367-117">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="c1367-117">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1367-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c1367-118">Remarks</span></span>  
 <span data-ttu-id="c1367-119">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="c1367-119">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="c1367-120">Si el modificador es <xref:System.Diagnostics.BooleanSwitch> , puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="c1367-120">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="c1367-121">Si el modificador es un <xref:System.Diagnostics.TraceSwitch> , puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c1367-121">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1367-122">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c1367-122">Example</span></span>  
 <span data-ttu-id="c1367-123">En el ejemplo siguiente se muestra cómo utilizar el **\<switch>** elemento para establecer el `General` modificador de seguimiento en el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="c1367-123">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="c1367-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c1367-124">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="c1367-125">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="c1367-125">Trace and Debug Settings Schema</span></span>](index.md)
