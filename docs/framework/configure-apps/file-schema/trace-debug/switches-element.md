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
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153235"
---
# <a name="switches-element"></a><span data-ttu-id="73adb-102">\<interruptores> Element</span><span class="sxs-lookup"><span data-stu-id="73adb-102">\<switches> Element</span></span>
<span data-ttu-id="73adb-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="73adb-103">Contains trace switches and the level where the trace switches are set.</span></span>  

<span data-ttu-id="73adb-104">[**\<configuración>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="73adb-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="73adb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="73adb-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>\
<span data-ttu-id="73adb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<interruptores>**</span><span class="sxs-lookup"><span data-stu-id="73adb-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<switches>**</span></span>

## <a name="syntax"></a><span data-ttu-id="73adb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="73adb-107">Syntax</span></span>  
  
```xml  
      <switches>
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="73adb-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="73adb-108">Attributes and Elements</span></span>  
 <span data-ttu-id="73adb-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="73adb-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="73adb-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="73adb-110">Attributes</span></span>  
 <span data-ttu-id="73adb-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="73adb-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="73adb-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="73adb-112">Child Elements</span></span>  
  
|<span data-ttu-id="73adb-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="73adb-113">Element</span></span>|<span data-ttu-id="73adb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="73adb-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="73adb-115">\<añadir></span><span class="sxs-lookup"><span data-stu-id="73adb-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="73adb-116">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="73adb-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="73adb-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="73adb-117">Parent Elements</span></span>  
  
|<span data-ttu-id="73adb-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="73adb-118">Element</span></span>|<span data-ttu-id="73adb-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="73adb-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="73adb-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="73adb-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="73adb-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="73adb-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73adb-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="73adb-122">Remarks</span></span>  
 <span data-ttu-id="73adb-123">Puede cambiar el nivel de un modificador de seguimiento poniéndolo en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="73adb-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="73adb-124">Si el interruptor <xref:System.Diagnostics.BooleanSwitch>es un , puede encenderlo y apagarlo.</span><span class="sxs-lookup"><span data-stu-id="73adb-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="73adb-125">Si el switch <xref:System.Diagnostics.TraceSwitch>es un , puede asignarle diferentes niveles para especificar los tipos de mensajes de seguimiento o depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="73adb-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="73adb-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="73adb-126">Example</span></span>  
 <span data-ttu-id="73adb-127">En el ejemplo siguiente \*\* \<\*\* se muestra cómo utilizar el <xref:System.Diagnostics.TraceLevel> elemento>switch `Data` para establecer el `General` modificador de seguimiento en el nivel y habilitar el modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="73adb-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="73adb-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="73adb-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="73adb-129">Esquema de configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="73adb-129">Trace and Debug Settings Schema</span></span>](index.md)
