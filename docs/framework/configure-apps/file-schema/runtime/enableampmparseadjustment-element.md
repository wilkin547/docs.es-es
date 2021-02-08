---
description: 'Más información acerca de: <EnableAmPmParseAdjustment> elemento'
title: <EnableAmPmParseAdjustment> (Elemento)
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
ms.openlocfilehash: 86fd04ab536f44f0cffdb5a37f4718fc03698485
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787063"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="9ee62-103">\<EnableAmPmParseAdjustment> (Elemento)</span><span class="sxs-lookup"><span data-stu-id="9ee62-103">\<EnableAmPmParseAdjustment> Element</span></span>

<span data-ttu-id="9ee62-104">Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9ee62-104">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<EnableAmPmParseAdjustment>**  
  
## <a name="syntax"></a><span data-ttu-id="9ee62-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ee62-105">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9ee62-106">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="9ee62-106">Attributes and Elements</span></span>  

 <span data-ttu-id="9ee62-107">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="9ee62-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9ee62-108">Atributos</span><span class="sxs-lookup"><span data-stu-id="9ee62-108">Attributes</span></span>  
  
|<span data-ttu-id="9ee62-109">Atributo</span><span class="sxs-lookup"><span data-stu-id="9ee62-109">Attribute</span></span>|<span data-ttu-id="9ee62-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee62-110">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="9ee62-111">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="9ee62-111">Required attribute.</span></span><br /><br /> <span data-ttu-id="9ee62-112">Especifica si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9ee62-112">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="9ee62-113">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="9ee62-113">enabled Attribute</span></span>  
  
|<span data-ttu-id="9ee62-114">Value</span><span class="sxs-lookup"><span data-stu-id="9ee62-114">Value</span></span>|<span data-ttu-id="9ee62-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee62-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ee62-116">0</span><span class="sxs-lookup"><span data-stu-id="9ee62-116">0</span></span>|<span data-ttu-id="9ee62-117">Los métodos de análisis de fecha y hora no usan reglas ajustadas para analizar cadenas de fecha que contengan solo un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9ee62-117">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="9ee62-118">1</span><span class="sxs-lookup"><span data-stu-id="9ee62-118">1</span></span>|<span data-ttu-id="9ee62-119">Los métodos de análisis de fecha y hora usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9ee62-119">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9ee62-120">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="9ee62-120">Child Elements</span></span>  

 <span data-ttu-id="9ee62-121">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="9ee62-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9ee62-122">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="9ee62-122">Parent Elements</span></span>  
  
|<span data-ttu-id="9ee62-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="9ee62-123">Element</span></span>|<span data-ttu-id="9ee62-124">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ee62-124">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="9ee62-125">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="9ee62-125">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="9ee62-126">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9ee62-126">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ee62-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9ee62-127">Remarks</span></span>  

 <span data-ttu-id="9ee62-128">El `<EnableAmPmParseAdjustment>` elemento controla el modo en que los siguientes métodos analizan una cadena de fecha que contiene un día y un mes numéricos seguidos de una hora y un designador AM/PM (por ejemplo, "4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="9ee62-128">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="9ee62-129">No se ven afectados otros patrones.</span><span class="sxs-lookup"><span data-stu-id="9ee62-129">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="9ee62-130">El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto en  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> los  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType> métodos,, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType> y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="9ee62-130">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="9ee62-131">En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="9ee62-131">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="9ee62-132">Si la regla de ajuste de análisis no está habilitada, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas y se omite el resto de la cadena excepto el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="9ee62-132">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="9ee62-133">La fecha y hora devueltas por el método de análisis consta de la fecha actual y la hora del día extraída de la cadena de fecha.</span><span class="sxs-lookup"><span data-stu-id="9ee62-133">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="9ee62-134">Si está habilitada la regla de ajuste de análisis, el método de análisis interpreta el día y el mes como pertenecientes al año actual e interpreta la hora como la hora del reloj de 12 horas.</span><span class="sxs-lookup"><span data-stu-id="9ee62-134">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="9ee62-135">En la tabla siguiente se muestra la diferencia en el <xref:System.DateTime> valor cuando el <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 AM "con la `<EnableAmPmParseAdjustment>` propiedad del elemento `enabled` establecida en" 0 "o" 1 ".</span><span class="sxs-lookup"><span data-stu-id="9ee62-135">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="9ee62-136">Supone que la fecha de hoy es el 5 de enero de 2017 y muestra la fecha como si estuviera formateada con la cadena de formato "G" de la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="9ee62-136">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="9ee62-137">Nombre de referencia cultural</span><span class="sxs-lookup"><span data-stu-id="9ee62-137">Culture name</span></span>|<span data-ttu-id="9ee62-138">habilitado = "0"</span><span class="sxs-lookup"><span data-stu-id="9ee62-138">enabled="0"</span></span>|<span data-ttu-id="9ee62-139">habilitado = "1"</span><span class="sxs-lookup"><span data-stu-id="9ee62-139">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="9ee62-140">es-ES</span><span class="sxs-lookup"><span data-stu-id="9ee62-140">en-US</span></span>|<span data-ttu-id="9ee62-141">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="9ee62-141">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="9ee62-142">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="9ee62-142">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="9ee62-143">en-GB</span><span class="sxs-lookup"><span data-stu-id="9ee62-143">en-GB</span></span>|<span data-ttu-id="9ee62-144">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="9ee62-144">5/1/2017 6:00:00</span></span>|<span data-ttu-id="9ee62-145">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="9ee62-145">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="9ee62-146">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ee62-146">See also</span></span>

- [<span data-ttu-id="9ee62-147">Elemento \<runtime></span><span class="sxs-lookup"><span data-stu-id="9ee62-147">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="9ee62-148">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="9ee62-148">\<configuration> Element</span></span>](../configuration-element.md)
