---
title: Elemento <add> para <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: 2edc890049d62913d693ad61d8d814d012c0f482
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71697179"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="9d6e7-102">\<add > elemento para \<switches ></span><span class="sxs-lookup"><span data-stu-id="9d6e7-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="9d6e7-103">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-103">Specifies the level where a trace switch is set.</span></span>  
  
[<span data-ttu-id="9d6e7-104"> **\<configuration>** </span><span class="sxs-lookup"><span data-stu-id="9d6e7-104">**\<configuration>**</span></span>](../configuration-element.md)  
<span data-ttu-id="9d6e7-105">&nbsp; @ no__t-1[ **\<System. diagnostics >** ](system-diagnostics-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d6e7-105">&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)</span></span>  
<span data-ttu-id="9d6e7-106">&nbsp; @ no__t-1 @ no__t-2 @ no__t-3[ **\<switches >** ](switches-element.md)</span><span class="sxs-lookup"><span data-stu-id="9d6e7-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)</span></span>  
<span data-ttu-id="9d6e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Agregar >**</span><span class="sxs-lookup"><span data-stu-id="9d6e7-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d6e7-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d6e7-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9d6e7-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9d6e7-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9d6e7-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9d6e7-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="9d6e7-111">Attributes</span></span>  
  
|<span data-ttu-id="9d6e7-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="9d6e7-112">Attribute</span></span>|<span data-ttu-id="9d6e7-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d6e7-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9d6e7-114">**name**</span><span class="sxs-lookup"><span data-stu-id="9d6e7-114">**name**</span></span>|<span data-ttu-id="9d6e7-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="9d6e7-116">Especifica el nombre del modificador.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-116">Specifies the name of the switch.</span></span> <span data-ttu-id="9d6e7-117">El valor de este atributo corresponde al parámetro *displayName* que se pasa al constructor switch.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="9d6e7-118">**value**</span><span class="sxs-lookup"><span data-stu-id="9d6e7-118">**value**</span></span>|<span data-ttu-id="9d6e7-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="9d6e7-120">Especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9d6e7-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9d6e7-121">Child Elements</span></span>  
 <span data-ttu-id="9d6e7-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9d6e7-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9d6e7-123">Parent Elements</span></span>  
  
|<span data-ttu-id="9d6e7-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="9d6e7-124">Element</span></span>|<span data-ttu-id="9d6e7-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d6e7-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9d6e7-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="9d6e7-127">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="9d6e7-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d6e7-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9d6e7-129">Remarks</span></span>  
 <span data-ttu-id="9d6e7-130">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="9d6e7-131">Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="9d6e7-132">Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9d6e7-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9d6e7-133">Example</span></span>  
 <span data-ttu-id="9d6e7-134">En el ejemplo siguiente se muestra cómo usar el elemento **> \<add** para establecer el modificador de seguimiento @no__t 2 en el nivel <xref:System.Diagnostics.TraceLevel> y habilitar el modificador de seguimiento booleano `Data`.</span><span class="sxs-lookup"><span data-stu-id="9d6e7-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9d6e7-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d6e7-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="9d6e7-136">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="9d6e7-136">Trace and Debug Settings Schema</span></span>](index.md)
