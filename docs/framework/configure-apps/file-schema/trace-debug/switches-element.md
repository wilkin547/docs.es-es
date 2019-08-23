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
ms.openlocfilehash: 92a1c8db43579048945d76082e3ebd2862efd7ed
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920445"
---
# <a name="switches-element"></a><span data-ttu-id="31bff-102">\<cambia > elemento</span><span class="sxs-lookup"><span data-stu-id="31bff-102">\<switches> Element</span></span>
<span data-ttu-id="31bff-103">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="31bff-103">Contains trace switches and the level where the trace switches are set.</span></span>  
  
 <span data-ttu-id="31bff-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="31bff-104">\<configuration></span></span>  
<span data-ttu-id="31bff-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="31bff-105">\<system.diagnostics></span></span>  
<span data-ttu-id="31bff-106">\<modificadores ></span><span class="sxs-lookup"><span data-stu-id="31bff-106">\<switches></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31bff-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31bff-107">Syntax</span></span>  
  
```xml  
      <switches>   
</switches>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="31bff-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="31bff-108">Attributes and Elements</span></span>  
 <span data-ttu-id="31bff-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="31bff-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="31bff-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="31bff-110">Attributes</span></span>  
 <span data-ttu-id="31bff-111">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="31bff-111">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="31bff-112">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="31bff-112">Child Elements</span></span>  
  
|<span data-ttu-id="31bff-113">Elemento</span><span class="sxs-lookup"><span data-stu-id="31bff-113">Element</span></span>|<span data-ttu-id="31bff-114">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="31bff-114">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="31bff-115">\<add></span><span class="sxs-lookup"><span data-stu-id="31bff-115">\<add></span></span>](add-element-for-switches.md)|<span data-ttu-id="31bff-116">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31bff-116">Specifies the level where a trace switch is set.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="31bff-117">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="31bff-117">Parent Elements</span></span>  
  
|<span data-ttu-id="31bff-118">Elemento</span><span class="sxs-lookup"><span data-stu-id="31bff-118">Element</span></span>|<span data-ttu-id="31bff-119">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="31bff-119">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="31bff-120">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="31bff-120">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`System.diagnostics`|<span data-ttu-id="31bff-121">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="31bff-121">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="31bff-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31bff-122">Remarks</span></span>  
 <span data-ttu-id="31bff-123">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="31bff-123">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="31bff-124">Si el modificador es <xref:System.Diagnostics.BooleanSwitch>, puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="31bff-124">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="31bff-125">Si el modificador es <xref:System.Diagnostics.TraceSwitch>un, puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="31bff-125">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="31bff-126">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31bff-126">Example</span></span>  
 <span data-ttu-id="31bff-127">En el ejemplo siguiente se muestra cómo utilizar <xref:System.Diagnostics.TraceLevel> el `Data` `General`  **\<elemento switch >** para establecer el modificador de seguimiento en el nivel y habilitar el modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="31bff-127">The following example shows how to use the **\<switch>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="31bff-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="31bff-128">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="31bff-129">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="31bff-129">Trace and Debug Settings Schema</span></span>](index.md)
