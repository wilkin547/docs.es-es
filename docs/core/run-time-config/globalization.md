---
title: Valores de configuración de globalización
description: Obtenga información sobre los valores del entorno de ejecución que configuran aspectos de globalización de una aplicación de .NET Core, por ejemplo, el procedimiento para analizar las fechas japonesas.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: 56228e9a6cb6dbab6a22bdc00d11212e1019776b
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761972"
---
# <a name="run-time-configuration-options-for-globalization"></a><span data-ttu-id="d48cb-103">Opciones de configuración del entorno de ejecución para globalización</span><span class="sxs-lookup"><span data-stu-id="d48cb-103">Run-time configuration options for globalization</span></span>

## <a name="invariant-mode"></a><span data-ttu-id="d48cb-104">Modo invariable</span><span class="sxs-lookup"><span data-stu-id="d48cb-104">Invariant mode</span></span>

- <span data-ttu-id="d48cb-105">Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="d48cb-105">Determines whether a .NET Core app runs in globalization-invariant mode without access to culture-specific data and behavior.</span></span>
- <span data-ttu-id="d48cb-106">Si se omite esta configuración, la aplicación se ejecuta con acceso a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="d48cb-106">If you omit this setting, the app runs with access to cultural data.</span></span> <span data-ttu-id="d48cb-107">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="d48cb-107">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="d48cb-108">Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span><span class="sxs-lookup"><span data-stu-id="d48cb-108">For more information, see [.NET Core globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span>

| | <span data-ttu-id="d48cb-109">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="d48cb-109">Setting name</span></span> | <span data-ttu-id="d48cb-110">Valores</span><span class="sxs-lookup"><span data-stu-id="d48cb-110">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d48cb-111">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d48cb-111">**runtimeconfig.json**</span></span> | `System.Globalization.Invariant` | <span data-ttu-id="d48cb-112">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="d48cb-112">`false` - access to cultural data</span></span><br/><span data-ttu-id="d48cb-113">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="d48cb-113">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="d48cb-114">**Propiedad de MSBuild**</span><span class="sxs-lookup"><span data-stu-id="d48cb-114">**MSBuild property**</span></span> | `InvariantGlobalization` | <span data-ttu-id="d48cb-115">`false`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="d48cb-115">`false` - access to cultural data</span></span><br/><span data-ttu-id="d48cb-116">`true`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="d48cb-116">`true` - run in invariant mode</span></span> |
| <span data-ttu-id="d48cb-117">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="d48cb-117">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | <span data-ttu-id="d48cb-118">`0`: acceder a los datos culturales.</span><span class="sxs-lookup"><span data-stu-id="d48cb-118">`0` - access to cultural data</span></span><br/><span data-ttu-id="d48cb-119">`1`: ejecutar en modo invariable.</span><span class="sxs-lookup"><span data-stu-id="d48cb-119">`1` - run in invariant mode</span></span> |

### <a name="examples"></a><span data-ttu-id="d48cb-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d48cb-120">Examples</span></span>

<span data-ttu-id="d48cb-121">Archivo *runtimeconfig.json*:</span><span class="sxs-lookup"><span data-stu-id="d48cb-121">*runtimeconfig.json* file:</span></span>

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

<span data-ttu-id="d48cb-122">Archivo del proyecto:</span><span class="sxs-lookup"><span data-stu-id="d48cb-122">Project file:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a><span data-ttu-id="d48cb-123">Rangos de años de la era</span><span class="sxs-lookup"><span data-stu-id="d48cb-123">Era year ranges</span></span>

- <span data-ttu-id="d48cb-124">Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="d48cb-124">Determines whether range checks for calendars that support multiple eras are relaxed or whether dates that overflow an era's date range throw an <xref:System.ArgumentOutOfRangeException>.</span></span>
- <span data-ttu-id="d48cb-125">Si se omite este valor, las comprobaciones de intervalo son distendidas.</span><span class="sxs-lookup"><span data-stu-id="d48cb-125">If you omit this setting, range checks are relaxed.</span></span> <span data-ttu-id="d48cb-126">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="d48cb-126">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="d48cb-127">Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span><span class="sxs-lookup"><span data-stu-id="d48cb-127">For more information, see [Calendars, eras, and date ranges: Relaxed range checks](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).</span></span>

| | <span data-ttu-id="d48cb-128">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="d48cb-128">Setting name</span></span> | <span data-ttu-id="d48cb-129">Valores</span><span class="sxs-lookup"><span data-stu-id="d48cb-129">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d48cb-130">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d48cb-130">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | <span data-ttu-id="d48cb-131">`false`: comprobaciones de intervalos relajadas.</span><span class="sxs-lookup"><span data-stu-id="d48cb-131">`false` - relaxed range checks</span></span><br/><span data-ttu-id="d48cb-132">`true`: los desbordamientos causan una excepción.</span><span class="sxs-lookup"><span data-stu-id="d48cb-132">`true` - overflows cause an exception</span></span> |
| <span data-ttu-id="d48cb-133">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="d48cb-133">**Environment variable**</span></span> | <span data-ttu-id="d48cb-134">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-134">N/A</span></span> | <span data-ttu-id="d48cb-135">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-135">N/A</span></span> |

## <a name="japanese-date-parsing"></a><span data-ttu-id="d48cb-136">Análisis de fechas japonesas</span><span class="sxs-lookup"><span data-stu-id="d48cb-136">Japanese date parsing</span></span>

- <span data-ttu-id="d48cb-137">Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="d48cb-137">Determines whether a string that contains either "1" or "Gannen" as the year parses successfully or whether only "1" is supported.</span></span>
- <span data-ttu-id="d48cb-138">Si se omite este valor, las cadenas que contienen "1" o "Gannen" como año se analizan correctamente.</span><span class="sxs-lookup"><span data-stu-id="d48cb-138">If you omit this setting, strings that contain either "1" or "Gannen" as the year parse successfully.</span></span> <span data-ttu-id="d48cb-139">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="d48cb-139">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="d48cb-140">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="d48cb-140">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="d48cb-141">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="d48cb-141">Setting name</span></span> | <span data-ttu-id="d48cb-142">Valores</span><span class="sxs-lookup"><span data-stu-id="d48cb-142">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d48cb-143">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d48cb-143">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | <span data-ttu-id="d48cb-144">`false`: se admite "Gannen" o "1".</span><span class="sxs-lookup"><span data-stu-id="d48cb-144">`false` - "Gannen" or "1" is supported</span></span><br/><span data-ttu-id="d48cb-145">`true`: solo se admite "1".</span><span class="sxs-lookup"><span data-stu-id="d48cb-145">`true` - only "1" is supported</span></span> |
| <span data-ttu-id="d48cb-146">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="d48cb-146">**Environment variable**</span></span> | <span data-ttu-id="d48cb-147">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-147">N/A</span></span> | <span data-ttu-id="d48cb-148">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-148">N/A</span></span> |

## <a name="japanese-year-format"></a><span data-ttu-id="d48cb-149">Formato de año japonés</span><span class="sxs-lookup"><span data-stu-id="d48cb-149">Japanese year format</span></span>

- <span data-ttu-id="d48cb-150">Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.</span><span class="sxs-lookup"><span data-stu-id="d48cb-150">Determines whether the first year of a Japanese calendar era is formatted as "Gannen" or as a number.</span></span>
- <span data-ttu-id="d48cb-151">Si se omite esta configuración, el primer año tiene formato "Gannen".</span><span class="sxs-lookup"><span data-stu-id="d48cb-151">If you omit this setting, the first year is formatted as "Gannen".</span></span> <span data-ttu-id="d48cb-152">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="d48cb-152">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="d48cb-153">Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span><span class="sxs-lookup"><span data-stu-id="d48cb-153">For more information, see [Represent dates in calendars with multiple eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).</span></span>

| | <span data-ttu-id="d48cb-154">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="d48cb-154">Setting name</span></span> | <span data-ttu-id="d48cb-155">Valores</span><span class="sxs-lookup"><span data-stu-id="d48cb-155">Values</span></span> |
| - | - | - |
| <span data-ttu-id="d48cb-156">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d48cb-156">**runtimeconfig.json**</span></span> | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | <span data-ttu-id="d48cb-157">`false`: dar formato como "Gannen".</span><span class="sxs-lookup"><span data-stu-id="d48cb-157">`false` - format as "Gannen"</span></span><br/><span data-ttu-id="d48cb-158">`true`: dar formato como número.</span><span class="sxs-lookup"><span data-stu-id="d48cb-158">`true` - format as number</span></span> |
| <span data-ttu-id="d48cb-159">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="d48cb-159">**Environment variable**</span></span> | <span data-ttu-id="d48cb-160">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-160">N/A</span></span> | <span data-ttu-id="d48cb-161">N/D</span><span class="sxs-lookup"><span data-stu-id="d48cb-161">N/A</span></span> |

## <a name="nls"></a><span data-ttu-id="d48cb-162">NLS</span><span class="sxs-lookup"><span data-stu-id="d48cb-162">NLS</span></span>

- <span data-ttu-id="d48cb-163">Determina si .NET usa las API de globalización de compatibilidad con el idioma nacional (NLS) o componentes internacionales para Unicode (ICU) para aplicaciones de Windows.</span><span class="sxs-lookup"><span data-stu-id="d48cb-163">Determines whether .NET uses National Language Support (NLS) or International Components for Unicode (ICU) globalization APIs for Windows apps.</span></span> <span data-ttu-id="d48cb-164">.NET 5.0 y versiones posteriores usan las API de globalización de ICU de forma predeterminada en la actualización de mayo de 2019 de Windows 10 o versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d48cb-164">.NET 5.0 and later versions use ICU globalization APIs by default on Windows 10 May 2019 Update and later versions.</span></span>
- <span data-ttu-id="d48cb-165">Si se omite esta configuración, .NET usa las API de globalización de ICU forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="d48cb-165">If you omit this setting, .NET uses ICU globalization APIs by default.</span></span> <span data-ttu-id="d48cb-166">Esto es equivalente a establecer el valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="d48cb-166">This is equivalent to setting the value to `false`.</span></span>
- <span data-ttu-id="d48cb-167">Para obtener más información, consulte [Las API de globalización usan bibliotecas ICU en Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span><span class="sxs-lookup"><span data-stu-id="d48cb-167">For more information, see [Globalization APIs use ICU libraries on Windows](../compatibility/3.1-5.0.md#globalization-apis-use-icu-libraries-on-windows).</span></span>

| | <span data-ttu-id="d48cb-168">Nombre de valor</span><span class="sxs-lookup"><span data-stu-id="d48cb-168">Setting name</span></span> | <span data-ttu-id="d48cb-169">Valores</span><span class="sxs-lookup"><span data-stu-id="d48cb-169">Values</span></span> | <span data-ttu-id="d48cb-170">Inclusión</span><span class="sxs-lookup"><span data-stu-id="d48cb-170">Introduced</span></span> |
| - | - | - | - |
| <span data-ttu-id="d48cb-171">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="d48cb-171">**runtimeconfig.json**</span></span> | `System.Globalization.UseNls` | <span data-ttu-id="d48cb-172">`false` -Uso de API de globalización de ICU</span><span class="sxs-lookup"><span data-stu-id="d48cb-172">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="d48cb-173">`true` -Uso de API de globalización de NLS</span><span class="sxs-lookup"><span data-stu-id="d48cb-173">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="d48cb-174">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d48cb-174">.NET 5.0</span></span> |
| <span data-ttu-id="d48cb-175">**Variable del entorno**</span><span class="sxs-lookup"><span data-stu-id="d48cb-175">**Environment variable**</span></span> | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | <span data-ttu-id="d48cb-176">`false` -Uso de API de globalización de ICU</span><span class="sxs-lookup"><span data-stu-id="d48cb-176">`false` - Use ICU globalization APIs</span></span><br/><span data-ttu-id="d48cb-177">`true` -Uso de API de globalización de NLS</span><span class="sxs-lookup"><span data-stu-id="d48cb-177">`true` - Use NLS globalization APIs</span></span> | <span data-ttu-id="d48cb-178">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d48cb-178">.NET 5.0</span></span> |
