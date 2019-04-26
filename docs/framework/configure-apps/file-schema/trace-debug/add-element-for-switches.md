---
title: Elemento <add> para <switches>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/switches/add
helpviewer_keywords:
- <add> element for <switches>
- add element for <switches>
ms.assetid: 712ac3a7-7abf-4a9e-8db4-acd241c2f369
ms.openlocfilehash: d7500620aed1165ff365fee8529230ba252dbc4b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673815"
---
# <a name="add-element-for-switches"></a><span data-ttu-id="29e30-102">\<Agregar > elemento para \<switches ></span><span class="sxs-lookup"><span data-stu-id="29e30-102">\<add> Element for \<switches></span></span>
<span data-ttu-id="29e30-103">Especifica el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29e30-103">Specifies the level where a trace switch is set.</span></span>  
  
 <span data-ttu-id="29e30-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="29e30-104">\<configuration></span></span>  
<span data-ttu-id="29e30-105">\<system.diagnostics></span><span class="sxs-lookup"><span data-stu-id="29e30-105">\<system.diagnostics></span></span>  
<span data-ttu-id="29e30-106">\<switches></span><span class="sxs-lookup"><span data-stu-id="29e30-106">\<switches></span></span>  
<span data-ttu-id="29e30-107">\<add></span><span class="sxs-lookup"><span data-stu-id="29e30-107">\<add></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29e30-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="29e30-108">Syntax</span></span>  
  
```xml  
<add name="switch name"  
     value="value"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="29e30-109">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="29e30-109">Attributes and Elements</span></span>  
 <span data-ttu-id="29e30-110">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="29e30-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="29e30-111">Atributos</span><span class="sxs-lookup"><span data-stu-id="29e30-111">Attributes</span></span>  
  
|<span data-ttu-id="29e30-112">Atributo</span><span class="sxs-lookup"><span data-stu-id="29e30-112">Attribute</span></span>|<span data-ttu-id="29e30-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="29e30-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="29e30-114">**name**</span><span class="sxs-lookup"><span data-stu-id="29e30-114">**name**</span></span>|<span data-ttu-id="29e30-115">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="29e30-115">Required attribute.</span></span><br /><br /> <span data-ttu-id="29e30-116">Especifica el nombre del conmutador.</span><span class="sxs-lookup"><span data-stu-id="29e30-116">Specifies the name of the switch.</span></span> <span data-ttu-id="29e30-117">El valor de este atributo corresponde a la *displayName* parámetro que se pasa al constructor del modificador.</span><span class="sxs-lookup"><span data-stu-id="29e30-117">The value of this attribute corresponds to the *displayName* parameter that is passed to switch constructor.</span></span>|  
|<span data-ttu-id="29e30-118">**value**</span><span class="sxs-lookup"><span data-stu-id="29e30-118">**value**</span></span>|<span data-ttu-id="29e30-119">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="29e30-119">Required attribute.</span></span><br /><br /> <span data-ttu-id="29e30-120">Especifica el nivel del modificador.</span><span class="sxs-lookup"><span data-stu-id="29e30-120">Specifies the level of the switch.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="29e30-121">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="29e30-121">Child Elements</span></span>  
 <span data-ttu-id="29e30-122">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="29e30-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="29e30-123">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="29e30-123">Parent Elements</span></span>  
  
|<span data-ttu-id="29e30-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="29e30-124">Element</span></span>|<span data-ttu-id="29e30-125">Descripción</span><span class="sxs-lookup"><span data-stu-id="29e30-125">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="29e30-126">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="29e30-126">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`switches`|<span data-ttu-id="29e30-127">Contiene modificadores de seguimiento y el nivel en el que están establecidos.</span><span class="sxs-lookup"><span data-stu-id="29e30-127">Contains trace switches and the level where the trace switches are set.</span></span>|  
|`system.diagnostics`|<span data-ttu-id="29e30-128">Especifica los agentes de escucha de seguimiento que recopilan, almacenan y enrutan mensajes, así como el nivel en el que está establecido un modificador de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="29e30-128">Specifies trace listeners that collect, store, and route messages and the level where a trace switch is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="29e30-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="29e30-129">Remarks</span></span>  
 <span data-ttu-id="29e30-130">Puede cambiar el nivel de un modificador de seguimiento colocándola en un archivo de configuración.</span><span class="sxs-lookup"><span data-stu-id="29e30-130">You can change the level of a trace switch by putting it in a configuration file.</span></span> <span data-ttu-id="29e30-131">Si el modificador es un <xref:System.Diagnostics.BooleanSwitch>, puede activar y desactivar.</span><span class="sxs-lookup"><span data-stu-id="29e30-131">If the switch is a <xref:System.Diagnostics.BooleanSwitch>, you can turn it on and off.</span></span> <span data-ttu-id="29e30-132">Si el modificador es un <xref:System.Diagnostics.TraceSwitch>, puede asignar distintos niveles para especificar los tipos de seguimiento de mensajes o de depuración genera la aplicación.</span><span class="sxs-lookup"><span data-stu-id="29e30-132">If the switch is a <xref:System.Diagnostics.TraceSwitch>, you can assign different levels to it to specify the types of trace or debug messages the application outputs.</span></span>  
  
## <a name="example"></a><span data-ttu-id="29e30-133">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="29e30-133">Example</span></span>  
 <span data-ttu-id="29e30-134">El ejemplo siguiente muestra cómo usar el  **\<Agregar >** elemento va a establecer el `General` modificador de seguimiento para el <xref:System.Diagnostics.TraceLevel> nivel y habilitar el `Data` modificador de seguimiento booleano.</span><span class="sxs-lookup"><span data-stu-id="29e30-134">The following example shows how to use the **\<add>** element to set the `General` trace switch to the <xref:System.Diagnostics.TraceLevel> level, and enable the `Data` Boolean trace switch.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="29e30-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="29e30-135">See also</span></span>

- <xref:System.Diagnostics.Switch>
- <xref:System.Diagnostics.TraceSwitch>
- <xref:System.Diagnostics.BooleanSwitch>
- [<span data-ttu-id="29e30-136">Esquema de la configuración de seguimiento y depuración</span><span class="sxs-lookup"><span data-stu-id="29e30-136">Trace and Debug Settings Schema</span></span>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)
