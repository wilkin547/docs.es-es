---
title: <EnableAmPmParseAdjustment> (Elemento)
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46cf37ee800c05eb7fe12e8491ad3b2130c3a04d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69920819"
---
# <a name="enableampmparseadjustment-element"></a><span data-ttu-id="1a17b-102">\<EnableAmPmParseAdjustment >, elemento</span><span class="sxs-lookup"><span data-stu-id="1a17b-102">\<EnableAmPmParseAdjustment> Element</span></span>
<span data-ttu-id="1a17b-103">Determina si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="1a17b-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="1a17b-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="1a17b-104">\<configuration></span></span>  
 <span data-ttu-id="1a17b-105">\<> en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1a17b-105">\<runtime></span></span>  
<span data-ttu-id="1a17b-106">\<EnableAmPmParseAdjustment></span><span class="sxs-lookup"><span data-stu-id="1a17b-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a17b-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1a17b-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1a17b-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="1a17b-108">Attributes and Elements</span></span>  
 <span data-ttu-id="1a17b-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="1a17b-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1a17b-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="1a17b-110">Attributes</span></span>  
  
|<span data-ttu-id="1a17b-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="1a17b-111">Attribute</span></span>|<span data-ttu-id="1a17b-112">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1a17b-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="1a17b-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="1a17b-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="1a17b-114">Especifica si los métodos de análisis de fecha y hora usan un conjunto ajustado de reglas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="1a17b-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="1a17b-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="1a17b-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="1a17b-116">Valor</span><span class="sxs-lookup"><span data-stu-id="1a17b-116">Value</span></span>|<span data-ttu-id="1a17b-117">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1a17b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1a17b-118">0</span><span class="sxs-lookup"><span data-stu-id="1a17b-118">0</span></span>|<span data-ttu-id="1a17b-119">Los métodos de análisis de fecha y hora no usan reglas ajustadas para analizar cadenas de fecha que contengan solo un día, un mes, una hora y un designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="1a17b-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="1a17b-120">1</span><span class="sxs-lookup"><span data-stu-id="1a17b-120">1</span></span>|<span data-ttu-id="1a17b-121">Los métodos de análisis de fecha y hora usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, un mes, una hora y el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="1a17b-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1a17b-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="1a17b-122">Child Elements</span></span>  
 <span data-ttu-id="1a17b-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="1a17b-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1a17b-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="1a17b-124">Parent Elements</span></span>  
  
|<span data-ttu-id="1a17b-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="1a17b-125">Element</span></span>|<span data-ttu-id="1a17b-126">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="1a17b-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="1a17b-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="1a17b-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="1a17b-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1a17b-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1a17b-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1a17b-129">Remarks</span></span>  
 <span data-ttu-id="1a17b-130">El `<EnableAmPmParseAdjustment>` elemento controla el modo en que los siguientes métodos analizan una cadena de fecha que contiene un día y un mes numéricos seguidos de una hora y un designador AM/PM (por ejemplo, "4/10 6 AM"):</span><span class="sxs-lookup"><span data-stu-id="1a17b-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
- <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
- <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="1a17b-131">No se ven afectados otros patrones.</span><span class="sxs-lookup"><span data-stu-id="1a17b-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="1a17b-132">El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto en <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>los <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>métodos <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>,, <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> y.</span><span class="sxs-lookup"><span data-stu-id="1a17b-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="1a17b-133">En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="1a17b-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="1a17b-134">Si la regla de ajuste de análisis no está habilitada, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas y se omite el resto de la cadena excepto el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="1a17b-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="1a17b-135">La fecha y hora devueltas por el método de análisis consta de la fecha actual y la hora del día extraída de la cadena de fecha.</span><span class="sxs-lookup"><span data-stu-id="1a17b-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="1a17b-136">Si está habilitada la regla de ajuste de análisis, el método de análisis interpreta el día y el mes como pertenecientes al año actual e interpreta la hora como la hora del reloj de 12 horas.</span><span class="sxs-lookup"><span data-stu-id="1a17b-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="1a17b-137">En la tabla siguiente se muestra la diferencia en <xref:System.DateTime> el valor cuando <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> el método se utiliza para analizar la cadena "" 4/10 6 AM "con `<EnableAmPmParseAdjustment>` la propiedad `enabled` del elemento establecida en" 0 "o" 1 ".</span><span class="sxs-lookup"><span data-stu-id="1a17b-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="1a17b-138">Supone que la fecha de hoy es el 5 de enero de 2017 y muestra la fecha como si estuviera formateada con la cadena de formato "G" de la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="1a17b-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="1a17b-139">Nombre de referencia cultural</span><span class="sxs-lookup"><span data-stu-id="1a17b-139">Culture name</span></span>|<span data-ttu-id="1a17b-140">enabled="0"</span><span class="sxs-lookup"><span data-stu-id="1a17b-140">enabled="0"</span></span>|<span data-ttu-id="1a17b-141">habilitado = "1"</span><span class="sxs-lookup"><span data-stu-id="1a17b-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="1a17b-142">en-US</span><span class="sxs-lookup"><span data-stu-id="1a17b-142">en-US</span></span>|<span data-ttu-id="1a17b-143">1/5/2017 4:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="1a17b-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="1a17b-144">4/10/2017 6:00:00 AM</span><span class="sxs-lookup"><span data-stu-id="1a17b-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="1a17b-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="1a17b-145">en-GB</span></span>|<span data-ttu-id="1a17b-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="1a17b-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="1a17b-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="1a17b-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1a17b-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a17b-148">See also</span></span>

- [<span data-ttu-id="1a17b-149">\<Elemento > en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="1a17b-149">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="1a17b-150">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="1a17b-150">\<configuration> Element</span></span>](../configuration-element.md)
