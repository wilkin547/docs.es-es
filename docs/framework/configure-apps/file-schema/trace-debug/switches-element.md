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
ms.openlocfilehash: afd0e955698dfc7ff3d5c843dd8db10f648265b8
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55254670"
---
# <a name="switches-element"></a><span data-ttu-id="48dae-102">\<conmutadores > elemento</span><span class="sxs-lookup"><span data-stu-id="48dae-102">\<switches> Element</span></span>
<span data-ttu-id="48dae-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="48dae-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="48dae-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="48dae-104">\<configuration></span></span>  
<span data-ttu-id="48dae-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="48dae-105">\<system.diagnostics></span></span>  
<span data-ttu-id="48dae-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="48dae-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48dae-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48dae-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48dae-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="48dae-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48dae-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="48dae-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48dae-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="48dae-110">Attributes</span></span>  
 <span data-ttu-id="48dae-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="48dae-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="48dae-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="48dae-112">Child Elements</span></span>  
  
|<span data-ttu-id="48dae-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="48dae-113">Element</span></span>|<span data-ttu-id="48dae-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="48dae-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48dae-115">\<add></span><span class="sxs-lookup"><span data-stu-id="48dae-115">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/add-element-for-switches.md)|<span data-ttu-id="48dae-116">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="48dae-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="48dae-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="48dae-117">Parent Elements</span></span>  
  
|<span data-ttu-id="48dae-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="48dae-118">Element</span></span>|<span data-ttu-id="48dae-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="48dae-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="48dae-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="48dae-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="48dae-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="48dae-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48dae-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="48dae-122">Remarks</span></span>  
 <span data-ttu-id="48dae-123">Puede cambiar el nivel de un modificador de seguimiento colocándola en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="48dae-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="48dae-124">Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, puede activar y desactivar.</span><span class="sxs-lookup"><span data-stu-id="48dae-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="48dae-125">Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, puede asignar distintos niveles para especificar los tipos de seguimiento de mensajes o de depuración genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="48dae-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48dae-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="48dae-126">Example</span></span>  
 <span data-ttu-id="48dae-127">El ejemplo siguiente muestra cómo usar el  **\<cambiar >** elemento va a establecer el `General` modificador de seguimiento para el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="48dae-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="48dae-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="48dae-128">See also</span></span>
- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="48dae-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="48dae-129">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
