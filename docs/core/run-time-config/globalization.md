---
title: Valores de configuración de globalización
description: Obtenga información sobre los valores del entorno de ejecución que configuran aspectos de globalización de una aplicación de .NET Core, por ejemplo, el procedimiento para analizar las fechas japonesas.
ms.date: 05/18/2020
ms.topic: reference
ms.openlocfilehash: e8179a7e1421a3ff0ceacf07a2843c1b77af6143
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873554"
---
# <a name="run-time-configuration-options-for-globalization"></a>Opciones de configuración del entorno de ejecución para globalización

## <a name="invariant-mode"></a>Modo invariable

- Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural.
- Si se omite esta configuración, la aplicación se ejecuta con acceso a los datos culturales. Esto es equivalente a establecer el valor en `false`.
- Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/runtime/blob/main/docs/design/features/globalization-invariant-mode.md).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false`: acceder a los datos culturales.<br/>`true`: ejecutar en modo invariable. |
| **Propiedad de MSBuild** | `InvariantGlobalization` | `false`: acceder a los datos culturales.<br/>`true`: ejecutar en modo invariable. |
| **Variable del entorno** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0`: acceder a los datos culturales.<br/>`1`: ejecutar en modo invariable. |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Globalization.Invariant": true
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <InvariantGlobalization>true</InvariantGlobalization>
  </PropertyGroup>

</Project>
```

## <a name="era-year-ranges"></a>Rangos de años de la era

- Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.
- Si se omite este valor, las comprobaciones de intervalo son distendidas. Esto es equivalente a establecer el valor en `false`.
- Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false`: comprobaciones de intervalos relajadas.<br/>`true`: los desbordamientos causan una excepción. |
| **Variable del entorno** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Análisis de fechas japonesas

- Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".
- Si se omite este valor, las cadenas que contienen "1" o "Gannen" como año se analizan correctamente. Esto es equivalente a establecer el valor en `false`.
- Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`: se admite "Gannen" o "1".<br/>`true`: solo se admite "1". |
| **Variable del entorno** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato de año japonés

- Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.
- Si se omite esta configuración, el primer año tiene formato "Gannen". Esto es equivalente a establecer el valor en `false`.
- Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`: dar formato como "Gannen".<br/>`true`: dar formato como número. |
| **Variable del entorno** | N/D | N/D |

## <a name="nls"></a>NLS

- Determina si .NET usa las API de globalización de compatibilidad con el idioma nacional (NLS) o componentes internacionales para Unicode (ICU) para aplicaciones de Windows. .NET 5.0 y versiones posteriores usan las API de globalización de ICU de forma predeterminada en la actualización de mayo de 2019 de Windows 10 o versiones posteriores.
- Si se omite esta configuración, .NET usa las API de globalización de ICU forma predeterminada. Esto es equivalente a establecer el valor en `false`.
- Para obtener más información, consulte [Las API de globalización usan bibliotecas ICU en Windows](../compatibility/globalization/5.0/icu-globalization-api.md).

| | Nombre de valor | Valores | Inclusión |
| - | - | - | - |
| **runtimeconfig.json** | `System.Globalization.UseNls` | `false` -Uso de API de globalización de ICU<br/>`true` -Uso de API de globalización de NLS | .NET 5.0 |
| **Variable del entorno** | `DOTNET_SYSTEM_GLOBALIZATION_USENLS` | `false` -Uso de API de globalización de ICU<br/>`true` -Uso de API de globalización de NLS | .NET 5.0 |
