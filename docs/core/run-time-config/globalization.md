---
title: Valores de configuración de globalización
description: Obtenga información sobre los valores del entorno de ejecución que configuran aspectos de globalización de una aplicación de .NET Core, por ejemplo, el procedimiento para analizar las fechas japonesas.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 0571c64eff5b38aafa37026fb2ba7f4aef778beb
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998844"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="df448-103">Opciones de configuración del entorno de ejecución para globalización</span><span class="sxs-lookup"><span data-stu-id="df448-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="df448-104">Modo invariable</span><span class="sxs-lookup"><span data-stu-id="df448-104">Invariant mode</span></span>

- <span data-ttu-id="df448-105">Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural, o bien si tiene acceso a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="df448-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="df448-106">Predeterminado: ejecutar la aplicación con acceso a los datos culturales (`false`).</span><span class="sxs-lookup"><span data-stu-id="df448-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="df448-107">Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="df448-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="df448-108">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="df448-108">Setting name</span></span> | <span data-ttu-id="df448-109">Valores</span><span class="sxs-lookup"><span data-stu-id="df448-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="df448-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="df448-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="df448-111">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="df448-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="df448-112">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="df448-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="df448-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="df448-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="df448-114">`0`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="df448-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="df448-115">`1`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="df448-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="df448-116">Rangos de años de la era</span><span class="sxs-lookup"><span data-stu-id="df448-116">Era year ranges</span></span>

- <span data-ttu-id="df448-117">Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="df448-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="df448-118">Predeterminado: las comprobaciones de intervalo son relajadas (`false`).</span><span class="sxs-lookup"><span data-stu-id="df448-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="df448-119">Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="df448-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="df448-120">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="df448-120">Setting name</span></span> | <span data-ttu-id="df448-121">Valores</span><span class="sxs-lookup"><span data-stu-id="df448-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="df448-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="df448-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="df448-123">`false`: comprobaciones de intervalos relajadas.</span><span class="sxs-lookup"><span data-stu-id="df448-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="df448-124">`true`: los desbordamientos causan una excepción.</span><span class="sxs-lookup"><span data-stu-id="df448-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="df448-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="df448-125">**Environment variable**</span></span> | <span data-ttu-id="df448-126">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-126">N/A</span></span> | <span data-ttu-id="df448-127">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="df448-128">Análisis de fechas japonesas</span><span class="sxs-lookup"><span data-stu-id="df448-128">Japanese date parsing</span></span>

- <span data-ttu-id="df448-129">Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="df448-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="df448-130">Predeterminado: analizar cadenas que contengan "1" o "Gannen" como año (`false`).</span><span class="sxs-lookup"><span data-stu-id="df448-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="df448-131">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="df448-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="df448-132">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="df448-132">Setting name</span></span> | <span data-ttu-id="df448-133">Valores</span><span class="sxs-lookup"><span data-stu-id="df448-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="df448-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="df448-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="df448-135">`false`: se admite "Gannen" o "1".</span><span class="sxs-lookup"><span data-stu-id="df448-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="df448-136">`true`: solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="df448-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="df448-137">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="df448-137">**Environment variable**</span></span> | <span data-ttu-id="df448-138">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-138">N/A</span></span> | <span data-ttu-id="df448-139">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="df448-140">Formato de año japonés</span><span class="sxs-lookup"><span data-stu-id="df448-140">Japanese year format</span></span>

- <span data-ttu-id="df448-141">Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.</span><span class="sxs-lookup"><span data-stu-id="df448-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="df448-142">Predeterminado: dar formato al primer año como "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="df448-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="df448-143">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="df448-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="df448-144">Nombre del valor</span><span class="sxs-lookup"><span data-stu-id="df448-144">Setting name</span></span> | <span data-ttu-id="df448-145">Valores</span><span class="sxs-lookup"><span data-stu-id="df448-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="df448-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="df448-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="df448-147">`false`: dar formato como "Gannen".</span><span class="sxs-lookup"><span data-stu-id="df448-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="df448-148">`true`: dar formato como número.</span><span class="sxs-lookup"><span data-stu-id="df448-148">`true` - format as number</span></span> |
| <span data-ttu-id="df448-149">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="df448-149">**Environment variable**</span></span> | <span data-ttu-id="df448-150">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-150">N/A</span></span> | <span data-ttu-id="df448-151">N/D</span><span class="sxs-lookup"><span data-stu-id="df448-151">N/A</span></span> |
