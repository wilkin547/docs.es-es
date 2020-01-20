---
title: Valores de configuración de globalización
description: Obtenga información sobre los valores del entorno de ejecución que configuran aspectos de globalización de una aplicación de .NET Core, por ejemplo, el procedimiento para analizar las fechas japonesas.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 76cd4a0a0f93f4df3ff243c6024b952576e8e6cb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740543"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="e843b-103">Opciones de configuración del entorno de ejecución para globalización</span><span class="sxs-lookup"><span data-stu-id="e843b-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="e843b-104">Modo invariable</span><span class="sxs-lookup"><span data-stu-id="e843b-104">Invariant mode</span></span>

- <span data-ttu-id="e843b-105">Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural, o bien si tiene acceso a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="e843b-105">Determines whether a .NET Core app runs in globalization invariant mode without access to culture-specific data and behavior or whether it has access to cultural data.</span></span>
- <span data-ttu-id="e843b-106">Predeterminado: ejecutar la aplicación con acceso a los datos culturales (`false`).</span><span class="sxs-lookup"><span data-stu-id="e843b-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="e843b-107">Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="e843b-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="e843b-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="e843b-108">Setting name</span></span> | <span data-ttu-id="e843b-109">Valores</span><span class="sxs-lookup"><span data-stu-id="e843b-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e843b-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e843b-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="e843b-111">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="e843b-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="e843b-112">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="e843b-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="e843b-113">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="e843b-113">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="e843b-114">`0`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="e843b-114">`0` - access to cultural data</span></span><br/><span data-ttu-id="e843b-115">`1`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="e843b-115">`1` - run in invariant mode</span></span> |

## <a name="era-year-ranges"></a><span data-ttu-id="e843b-116">Rangos de años de la era</span><span class="sxs-lookup"><span data-stu-id="e843b-116">Era year ranges</span></span>

- <span data-ttu-id="e843b-117">Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="e843b-117">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="e843b-118">Predeterminado: las comprobaciones de intervalo son relajadas (`false`).</span><span class="sxs-lookup"><span data-stu-id="e843b-118">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="e843b-119">Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="e843b-119">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="e843b-120">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="e843b-120">Setting name</span></span> | <span data-ttu-id="e843b-121">Valores</span><span class="sxs-lookup"><span data-stu-id="e843b-121">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e843b-122">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e843b-122">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="e843b-123">`false`: comprobaciones de intervalos relajadas.</span><span class="sxs-lookup"><span data-stu-id="e843b-123">`false` - relaxed range checks</span></span><br/><span data-ttu-id="e843b-124">`true`: los desbordamientos causan una excepción.</span><span class="sxs-lookup"><span data-stu-id="e843b-124">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="e843b-125">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="e843b-125">**Environment variable**</span></span> | <span data-ttu-id="e843b-126">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-126">N/A</span></span> | <span data-ttu-id="e843b-127">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-127">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="e843b-128">Análisis de fechas japonesas</span><span class="sxs-lookup"><span data-stu-id="e843b-128">Japanese date parsing</span></span>

- <span data-ttu-id="e843b-129">Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="e843b-129">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="e843b-130">Predeterminado: analizar cadenas que contengan "1" o "Gannen" como año (`false`).</span><span class="sxs-lookup"><span data-stu-id="e843b-130">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="e843b-131">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e843b-131">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e843b-132">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="e843b-132">Setting name</span></span> | <span data-ttu-id="e843b-133">Valores</span><span class="sxs-lookup"><span data-stu-id="e843b-133">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e843b-134">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e843b-134">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="e843b-135">`false`: se admite "Gannen" o "1".</span><span class="sxs-lookup"><span data-stu-id="e843b-135">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="e843b-136">`true`: solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="e843b-136">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="e843b-137">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="e843b-137">**Environment variable**</span></span> | <span data-ttu-id="e843b-138">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-138">N/A</span></span> | <span data-ttu-id="e843b-139">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-139">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="e843b-140">Formato de año japonés</span><span class="sxs-lookup"><span data-stu-id="e843b-140">Japanese year format</span></span>

- <span data-ttu-id="e843b-141">Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.</span><span class="sxs-lookup"><span data-stu-id="e843b-141">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="e843b-142">Predeterminado: dar formato al primer año como "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="e843b-142">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="e843b-143">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="e843b-143">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="e843b-144">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="e843b-144">Setting name</span></span> | <span data-ttu-id="e843b-145">Valores</span><span class="sxs-lookup"><span data-stu-id="e843b-145">Values</span></span> |
| - | - | - |
| <span data-ttu-id="e843b-146">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="e843b-146">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="e843b-147">`false`: dar formato como "Gannen".</span><span class="sxs-lookup"><span data-stu-id="e843b-147">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="e843b-148">`true`: dar formato como número.</span><span class="sxs-lookup"><span data-stu-id="e843b-148">`true` - format as number</span></span> |
| <span data-ttu-id="e843b-149">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="e843b-149">**Environment variable**</span></span> | <span data-ttu-id="e843b-150">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-150">N/A</span></span> | <span data-ttu-id="e843b-151">N/D</span><span class="sxs-lookup"><span data-stu-id="e843b-151">N/A</span></span> |
