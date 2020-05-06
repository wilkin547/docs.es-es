---
title: Valores de configuración de globalización
description: Obtenga información sobre los valores del entorno de ejecución que configuran aspectos de globalización de una aplicación de .NET Core, por ejemplo, el procedimiento para analizar las fechas japonesas.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 7668c345181d7c08cfca9c5cb76b8addd76223ec
ms.sourcegitcommit: 1cb64b53eb1f253e6a3f53ca9510ef0be1fd06fe
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/29/2020
ms.locfileid: "82506810"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="c4735-103">Opciones de configuración del entorno de ejecución para globalización</span><span class="sxs-lookup"><span data-stu-id="c4735-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="c4735-104">Modo invariable</span><span class="sxs-lookup"><span data-stu-id="c4735-104">Invariant mode</span></span>

- <span data-ttu-id="c4735-105">Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="c4735-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="c4735-106">Predeterminado: ejecutar la aplicación con acceso a los datos culturales (`false`).</span><span class="sxs-lookup"><span data-stu-id="c4735-106">Default: Run the app with access to cultural data (`false`).</span></span>
- <span data-ttu-id="c4735-107">Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="c4735-107">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="c4735-108">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="c4735-108">Setting name</span></span> | <span data-ttu-id="c4735-109">Valores</span><span class="sxs-lookup"><span data-stu-id="c4735-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c4735-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c4735-110">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="c4735-111">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="c4735-111">`false` - access to cultural data</span></span><br/><span data-ttu-id="c4735-112">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="c4735-112">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="c4735-113">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="c4735-113">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="c4735-114">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="c4735-114">`false` - access to cultural data</span></span><br/><span data-ttu-id="c4735-115">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="c4735-115">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="c4735-116">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="c4735-116">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="c4735-117">`0`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="c4735-117">`0` - access to cultural data</span></span><br/><span data-ttu-id="c4735-118">`1`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="c4735-118">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="c4735-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c4735-119">Examples</span></span>

<span data-ttu-id="c4735-120">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="c4735-120">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="c4735-121">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="c4735-121">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="c4735-122">Rangos de años de la era</span><span class="sxs-lookup"><span data-stu-id="c4735-122">Era year ranges</span></span>

- <span data-ttu-id="c4735-123">Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="c4735-123">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="c4735-124">Predeterminado: las comprobaciones de intervalo son relajadas (`false`).</span><span class="sxs-lookup"><span data-stu-id="c4735-124">Default: Range checks are relaxed (`false`).</span></span>
- <span data-ttu-id="c4735-125">Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="c4735-125">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="c4735-126">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="c4735-126">Setting name</span></span> | <span data-ttu-id="c4735-127">Valores</span><span class="sxs-lookup"><span data-stu-id="c4735-127">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c4735-128">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c4735-128">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="c4735-129">`false`: comprobaciones de intervalos relajadas.</span><span class="sxs-lookup"><span data-stu-id="c4735-129">`false` - relaxed range checks</span></span><br/><span data-ttu-id="c4735-130">`true`: los desbordamientos causan una excepción.</span><span class="sxs-lookup"><span data-stu-id="c4735-130">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="c4735-131">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="c4735-131">**Environment variable**</span></span> | <span data-ttu-id="c4735-132">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-132">N/A</span></span> | <span data-ttu-id="c4735-133">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-133">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="c4735-134">Análisis de fechas japonesas</span><span class="sxs-lookup"><span data-stu-id="c4735-134">Japanese date parsing</span></span>

- <span data-ttu-id="c4735-135">Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="c4735-135">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="c4735-136">Predeterminado: analizar cadenas que contengan "1" o "Gannen" como año (`false`).</span><span class="sxs-lookup"><span data-stu-id="c4735-136">Default: Parse strings that contain either "1" or "Gannen" as the year (`false`).</span></span>
- <span data-ttu-id="c4735-137">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="c4735-137">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="c4735-138">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="c4735-138">Setting name</span></span> | <span data-ttu-id="c4735-139">Valores</span><span class="sxs-lookup"><span data-stu-id="c4735-139">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c4735-140">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c4735-140">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="c4735-141">`false`: se admite "Gannen" o "1".</span><span class="sxs-lookup"><span data-stu-id="c4735-141">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="c4735-142">`true`: solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="c4735-142">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="c4735-143">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="c4735-143">**Environment variable**</span></span> | <span data-ttu-id="c4735-144">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-144">N/A</span></span> | <span data-ttu-id="c4735-145">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-145">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="c4735-146">Formato de año japonés</span><span class="sxs-lookup"><span data-stu-id="c4735-146">Japanese year format</span></span>

- <span data-ttu-id="c4735-147">Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.</span><span class="sxs-lookup"><span data-stu-id="c4735-147">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="c4735-148">Predeterminado: dar formato al primer año como "Gannen" (`false`).</span><span class="sxs-lookup"><span data-stu-id="c4735-148">Default: Format the first year as "Gannen" (`false`).</span></span>
- <span data-ttu-id="c4735-149">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="c4735-149">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="c4735-150">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="c4735-150">Setting name</span></span> | <span data-ttu-id="c4735-151">Valores</span><span class="sxs-lookup"><span data-stu-id="c4735-151">Values</span></span> |
| - | - | - |
| <span data-ttu-id="c4735-152">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="c4735-152">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="c4735-153">`false`: dar formato como "Gannen".</span><span class="sxs-lookup"><span data-stu-id="c4735-153">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="c4735-154">`true`: dar formato como número.</span><span class="sxs-lookup"><span data-stu-id="c4735-154">`true` - format as number</span></span> |
| <span data-ttu-id="c4735-155">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="c4735-155">**Environment variable**</span></span> | <span data-ttu-id="c4735-156">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-156">N/A</span></span> | <span data-ttu-id="c4735-157">N/D</span><span class="sxs-lookup"><span data-stu-id="c4735-157">N/A</span></span> |
