---
title: '&lt;conmutadores&gt; elemento'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches
- http://schemas.microsoft.com/.NetConfiguration/v2.0#switches
helpviewer_keywords:
- <switches> element
- switches element
- trace switches, <switches> element
ms.assetid: 4cf36786-b89a-40e2-a0f1-86bb9b783343
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 6240f8192f2a31faeb81528e54481eb06cc04d04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="ltswitchesgt-element"></a><span data-ttu-id="e26da-102">&lt;conmutadores&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="e26da-102">&lt;switches&gt; Element</span></span>
<span data-ttu-id="e26da-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="e26da-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="e26da-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e26da-104">\<configuration></span></span>  
<span data-ttu-id="e26da-105">\<System.Diagnostics ></span><span class="sxs-lookup"><span data-stu-id="e26da-105">\<system.diagnostics></span></span>  
<span data-ttu-id="e26da-106">\<conmutadores ></span><span class="sxs-lookup"><span data-stu-id="e26da-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e26da-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e26da-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e26da-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="e26da-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e26da-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="e26da-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e26da-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="e26da-110">Attributes</span></span>  
 <span data-ttu-id="e26da-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="e26da-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="e26da-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="e26da-112">Child Elements</span></span>  
  
|<span data-ttu-id="e26da-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="e26da-113">Element</span></span>|<span data-ttu-id="e26da-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="e26da-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e26da-115">\<add></span><span class="sxs-lookup"><span data-stu-id="e26da-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="e26da-116">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e26da-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e26da-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="e26da-117">Parent Elements</span></span>  
  
|<span data-ttu-id="e26da-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="e26da-118">Element</span></span>|<span data-ttu-id="e26da-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="e26da-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="e26da-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e26da-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="e26da-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="e26da-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e26da-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e26da-122">Remarks</span></span>  
 <span data-ttu-id="e26da-123">Puede cambiar el nivel de un modificador de seguimiento colocándola en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="e26da-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="e26da-124">Si el modificador está un <xref:System.Diagnostics.BooleanSwitch>, se puede activar y desactivar.</span><span class="sxs-lookup"><span data-stu-id="e26da-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="e26da-125">Si el modificador está un <xref:System.Diagnostics.TraceSwitch>, puede asignar distintos niveles para especificar los tipos de seguimiento de mensajes o de depuración genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e26da-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e26da-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e26da-126">Example</span></span>  
 <span data-ttu-id="e26da-127">En el ejemplo siguiente se muestra cómo utilizar el  **\<cambiar >** elemento que se va a establecer el `General` modificador de seguimiento para la <xref:System.Diagnostics.TraceLevel> nivel y habilitar la `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="e26da-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e26da-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="e26da-128">See Also</span></span>  
 <xref:System.Diagnostics.Switch>  
 <xref:System.Diagnostics.TraceSwitch>  
 <xref:System.Diagnostics.BooleanSwitch>  
 [<span data-ttu-id="e26da-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="e26da-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
