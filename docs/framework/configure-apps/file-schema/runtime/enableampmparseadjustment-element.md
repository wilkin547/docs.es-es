---
title: '&lt;EnableAmPmParseAdjustment&gt; elemento'
ms.date: 03/30/2017
ms.assetid: fda998a5-f538-4f8b-a18c-ee7f35e16938
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b17f521be31fa4082d9418c7dad734e37994bbb5
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
ms.locfileid: "32752824"
---
# <a name="ltenableampmparseadjustmentgt-element"></a><span data-ttu-id="ca4aa-102">&lt;EnableAmPmParseAdjustment&gt; elemento</span><span class="sxs-lookup"><span data-stu-id="ca4aa-102">&lt;EnableAmPmParseAdjustment&gt; Element</span></span>
<span data-ttu-id="ca4aa-103">Determina si la fecha y hora en métodos de análisis usan un conjunto de reglas ajustado para analizar cadenas de fecha que contienen un día, el mes, la hora y el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-103">Determines whether date and time parsing methods use an adjusted set of rules to parse date strings that contain a day, month, hour, and AM/PM designator.</span></span>  
  
 <span data-ttu-id="ca4aa-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="ca4aa-104">\<configuration></span></span>  
 <span data-ttu-id="ca4aa-105">\<en tiempo de ejecución ></span><span class="sxs-lookup"><span data-stu-id="ca4aa-105">\<runtime></span></span>  
<span data-ttu-id="ca4aa-106">\<EnableAmPmParseAdjustment ></span><span class="sxs-lookup"><span data-stu-id="ca4aa-106">\<EnableAmPmParseAdjustment></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca4aa-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ca4aa-107">Syntax</span></span>  
  
```xml  
<EnableAmPmParseAdjustment enabled="0"|"1" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="ca4aa-108">Atributos y elementos</span><span class="sxs-lookup"><span data-stu-id="ca4aa-108">Attributes and Elements</span></span>  
 <span data-ttu-id="ca4aa-109">En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="ca4aa-110">Atributos</span><span class="sxs-lookup"><span data-stu-id="ca4aa-110">Attributes</span></span>  
  
|<span data-ttu-id="ca4aa-111">Atributo</span><span class="sxs-lookup"><span data-stu-id="ca4aa-111">Attribute</span></span>|<span data-ttu-id="ca4aa-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca4aa-112">Description</span></span>|  
|---------------|-----------------|  
|`enabled`|<span data-ttu-id="ca4aa-113">Atributo necesario.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-113">Required attribute.</span></span><br /><br /> <span data-ttu-id="ca4aa-114">Especifica si la fecha y hora en métodos de análisis utilizan un conjunto de reglas ajustado para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-114">Specifies whether date and time parsing methods use an adjusted set of rules to parse date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="enabled-attribute"></a><span data-ttu-id="ca4aa-115">Atributo enabled</span><span class="sxs-lookup"><span data-stu-id="ca4aa-115">enabled Attribute</span></span>  
  
|<span data-ttu-id="ca4aa-116">Valor</span><span class="sxs-lookup"><span data-stu-id="ca4aa-116">Value</span></span>|<span data-ttu-id="ca4aa-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca4aa-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="ca4aa-118">0</span><span class="sxs-lookup"><span data-stu-id="ca4aa-118">0</span></span>|<span data-ttu-id="ca4aa-119">Fecha y hora en métodos de análisis no utilizan reglas ajustadas para analizar cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-119">Date and time parsing methods do not use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
|<span data-ttu-id="ca4aa-120">1</span><span class="sxs-lookup"><span data-stu-id="ca4aa-120">1</span></span>|<span data-ttu-id="ca4aa-121">Fecha y hora en métodos de análisis usan reglas ajustadas para analizar las cadenas de fecha que contienen solo un día, mes, hora y designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-121">Date and time parsing methods use adjusted rules for parsing date strings that contain only a day, month, hour, and AM/PM designator.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="ca4aa-122">Elementos secundarios</span><span class="sxs-lookup"><span data-stu-id="ca4aa-122">Child Elements</span></span>  
 <span data-ttu-id="ca4aa-123">Ninguno.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="ca4aa-124">Elementos primarios</span><span class="sxs-lookup"><span data-stu-id="ca4aa-124">Parent Elements</span></span>  
  
|<span data-ttu-id="ca4aa-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="ca4aa-125">Element</span></span>|<span data-ttu-id="ca4aa-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca4aa-126">Description</span></span>|  
|-------------|-----------------|  
|`configuration`|<span data-ttu-id="ca4aa-127">Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-127">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span>|  
|`runtime`|<span data-ttu-id="ca4aa-128">Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-128">Contains information about runtime initialization options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca4aa-129">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ca4aa-129">Remarks</span></span>  
 <span data-ttu-id="ca4aa-130">El `<EnableAmPmParseAdjustment>` elemento controla cómo los métodos siguientes para analizar una cadena de fecha que contiene un número de día y mes seguido de una hora y un designador AM/PM (por ejemplo, "4/10 6 A.M."):</span><span class="sxs-lookup"><span data-stu-id="ca4aa-130">The `<EnableAmPmParseAdjustment>` element controls how the following methods parse a date string that contains a numeric day and month followed by an hour and an AM/PM designator (such as "4/10 6 AM"):</span></span>  
  
-   <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.Parse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTime.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.DateTimeOffset.TryParse%2A?displayProperty=nameWithType>  
  
-   <xref:System.Convert.ToDateTime%2A?displayProperty=nameWithType>  
  
 <span data-ttu-id="ca4aa-131">Otros patrones que no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-131">No other patterns are affected.</span></span>  
  
 <span data-ttu-id="ca4aa-132">El `<EnableAmPmParseAdjustment>` elemento no tiene ningún efecto el <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, y <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> métodos.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-132">The `<EnableAmPmParseAdjustment>` element has no effect on the  <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>,  <xref:System.DateTime.TryParseExact%2A?displayProperty=nameWithType>, <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>, and <xref:System.DateTimeOffset.TryParseExact%2A?displayProperty=nameWithType> methods.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ca4aa-133">En .NET Core y .NET Native, las reglas de análisis de AM/PM ajustadas están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-133">In .NET Core and .NET Native, the adjusted AM/PM parsing rules are enabled by default.</span></span>  
  
 <span data-ttu-id="ca4aa-134">Si no está habilitada la regla de ajuste de análisis, el primer dígito de la cadena se interpreta como la hora del reloj de 12 horas, y se omite el resto de la cadena excepto el designador AM/PM.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-134">If the parsing adjustment rule is not enabled, the first digit of the string is interpreted as the hour of the 12-hour clock, and the remainder of the string except for the AM/PM designator is ignored.</span></span> <span data-ttu-id="ca4aa-135">La fecha y hora devuelto por el método de análisis consta de la fecha actual y la hora del día que se extrae de la cadena de fecha.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-135">The date and time returned by the parsing method consists of the current date and the hour of the day extracted from the date string.</span></span>  
  
 <span data-ttu-id="ca4aa-136">Si está habilitada la regla de ajuste de análisis, en el método de análisis interpretar el día y el mes como pertenecientes al año actual e interpretar al tiempo que la hora del reloj de 12 horas.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-136">If the parsing adjustment rule is enabled, parsing method interpret the day and month as belonging to the current year, and interpret the time as the hour of the 12-hour clock.</span></span>  
  
 <span data-ttu-id="ca4aa-137">En la tabla siguiente se ilustra la diferencia entre el <xref:System.DateTime> valor cuando la <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> método se utiliza para analizar la cadena "" 4/10 6 AM"con el `<EnableAmPmParseAdjustment>` del elemento `enabled` propiedad establecida en"0"o"1".</span><span class="sxs-lookup"><span data-stu-id="ca4aa-137">The following table illustrates the difference in the <xref:System.DateTime> value when the <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> method is used to parse the string ""4/10 6 AM" with the `<EnableAmPmParseAdjustment>` element's `enabled` property  set to "0" or "1".</span></span> <span data-ttu-id="ca4aa-138">Se supone que la fecha actual es el 5 de enero de 2017 y muestra la fecha como si se da formato con la cadena de formato "G" de la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-138">It assumes that today's date is January 5, 2017, and displays the date as if it is formatted using the specified culture's "G" format string.</span></span>  
  
|<span data-ttu-id="ca4aa-139">Nombre de referencia cultural</span><span class="sxs-lookup"><span data-stu-id="ca4aa-139">Culture name</span></span>|<span data-ttu-id="ca4aa-140">habilitada = "0"</span><span class="sxs-lookup"><span data-stu-id="ca4aa-140">enabled="0"</span></span>|<span data-ttu-id="ca4aa-141">habilitada = "1"</span><span class="sxs-lookup"><span data-stu-id="ca4aa-141">enabled="1"</span></span>|  
|------------------|------------------|------------------|  
|<span data-ttu-id="ca4aa-142">en-US</span><span class="sxs-lookup"><span data-stu-id="ca4aa-142">en-US</span></span>|<span data-ttu-id="ca4aa-143">1/5/2017 4:00:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-143">1/5/2017 4:00:00 AM</span></span>|<span data-ttu-id="ca4aa-144">4/10/2017 6:00:00 A.M.</span><span class="sxs-lookup"><span data-stu-id="ca4aa-144">4/10/2017 6:00:00 AM</span></span>|  
|<span data-ttu-id="ca4aa-145">en-GB</span><span class="sxs-lookup"><span data-stu-id="ca4aa-145">en-GB</span></span>|<span data-ttu-id="ca4aa-146">5/1/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ca4aa-146">5/1/2017 6:00:00</span></span>|<span data-ttu-id="ca4aa-147">10/4/2017 6:00:00</span><span class="sxs-lookup"><span data-stu-id="ca4aa-147">10/4/2017 6:00:00</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ca4aa-148">Vea también</span><span class="sxs-lookup"><span data-stu-id="ca4aa-148">See Also</span></span>  
 [<span data-ttu-id="ca4aa-149">\<en tiempo de ejecución > elemento</span><span class="sxs-lookup"><span data-stu-id="ca4aa-149">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)  
 [<span data-ttu-id="ca4aa-150">Elemento \<configuration></span><span class="sxs-lookup"><span data-stu-id="ca4aa-150">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)
