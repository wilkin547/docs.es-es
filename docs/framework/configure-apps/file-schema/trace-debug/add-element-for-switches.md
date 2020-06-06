---
title: Elemento <add> para <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: db2de681227dfdb7420808963219b9f52381f8fe
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/06/2020
ms.locfileid: "74088957"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="86d25-102">Elemento \<add> para \<switches></span><span class="sxs-lookup"><span data-stu-id="86d25-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="86d25-103">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="86d25-103">Specifies the level where a trace switch is set.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.diagnostics>**](system-diagnostics-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<switches>**](switches-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**

## <a name="syntax"></a><span data-ttu-id="86d25-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86d25-104">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="86d25-105">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="86d25-105">Attributes and Elements</span></span>  
 <span data-ttu-id="86d25-106">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="86d25-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="86d25-107">Atributos</span><span class="sxs-lookup"><span data-stu-id="86d25-107">Attributes</span></span>  
  
|<span data-ttu-id="86d25-108">Atributo</span><span class="sxs-lookup"><span data-stu-id="86d25-108">Attribute</span></span>|<span data-ttu-id="86d25-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="86d25-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="86d25-110">**name**</span><span class="sxs-lookup"><span data-stu-id="86d25-110">**name**</span></span>|<span data-ttu-id="86d25-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="86d25-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="86d25-112">Especifica el nombre del modificador.</span><span class="sxs-lookup"><span data-stu-id="86d25-112">Specifies the name of the switch.</span></span> <span data-ttu-id="86d25-113">El valor de este atributo corresponde al parámetro *displayName* que se pasa al constructor switch.</span><span class="sxs-lookup"><span data-stu-id="86d25-113">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="86d25-114">**value**</span><span class="sxs-lookup"><span data-stu-id="86d25-114">**value**</span></span>|<span data-ttu-id="86d25-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="86d25-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="86d25-116">Especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="86d25-116">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="86d25-117">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="86d25-117">Child Elements</span></span>  
 <span data-ttu-id="86d25-118">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="86d25-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="86d25-119">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="86d25-119">Parent Elements</span></span>  
  
|<span data-ttu-id="86d25-120">Elemento</span><span class="sxs-lookup"><span data-stu-id="86d25-120">Element</span></span>|<span data-ttu-id="86d25-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="86d25-121">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="86d25-122">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="86d25-122">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="86d25-123">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="86d25-123">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="86d25-124">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="86d25-124">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86d25-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86d25-125">Remarks</span></span>  
 <span data-ttu-id="86d25-126">Puede cambiar el nivel de un modificador de seguimiento si lo coloca en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="86d25-126">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="86d25-127">Si el modificador es <xref:System.Diagnostics.BooleanSwitch> , puede activarlo y desactivarlo.</span><span class="sxs-lookup"><span data-stu-id="86d25-127">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="86d25-128">Si el modificador es un <xref:System.Diagnostics.TraceSwitch> , puede asignarle niveles diferentes para especificar los tipos de mensajes de seguimiento o de depuración que genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="86d25-128">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86d25-129">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="86d25-129">Example</span></span>  
 <span data-ttu-id="86d25-130">En el ejemplo siguiente se muestra cómo utilizar el **\<add>** elemento para establecer el `General` modificador de seguimiento en el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="86d25-130">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="86d25-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86d25-131">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="86d25-132">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="86d25-132">Trace and Debug Settings Schema</span></span>](index.md)
