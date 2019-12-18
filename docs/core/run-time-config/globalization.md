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
# <a name="run-time-configuration-options-for-globalization"></a>Opciones de configuración del entorno de ejecución para globalización

## <a name="invariant-mode"></a>Modo invariable

- Determina si una aplicación de .NET Core se ejecuta en modo invariable de globalización sin tener acceso a los datos y el comportamiento concretos de la referencia cultural, o bien si tiene acceso a los datos culturales.
- Predeterminado: ejecutar la aplicación con acceso a los datos culturales (`false`).
- Para obtener más información, vea [Modo invariable de globalización de .NET Core](https://github.com/dotnet/corefx/blob/master/Documentation/architecture/globalization-invariant-mode.md).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Globalization.Invariant` | `false`: acceder a los datos culturales.<br/>`true`: ejecutar en modo invariable. |
| **Variable del entorno** | `DOTNET_SYSTEM_GLOBALIZATION_INVARIANT` | `0`: acceder a los datos culturales.<br/>`1`: ejecutar en modo invariable. |

## <a name="era-year-ranges"></a>Rangos de años de la era

- Determina si las comprobaciones de rango para los calendarios que admiten varias eras son relajadas o si las fechas que desbordan el intervalo de fechas de una era producen un elemento <xref:System.ArgumentOutOfRangeException>.
- Predeterminado: las comprobaciones de intervalo son relajadas (`false`).
- Para obtener más información, vea [Calendarios, eras e intervalos de fechas: comprobaciones de intervalos relajadas](../../standard/datetime/working-with-calendars.md#calendars-eras-and-date-ranges-relaxed-range-checks).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceJapaneseEraYearRanges` | `false`: comprobaciones de intervalos relajadas.<br/>`true`: los desbordamientos causan una excepción. |
| **Variable del entorno** | N/D | N/D |

## <a name="japanese-date-parsing"></a>Análisis de fechas japonesas

- Determina si una cadena cuyo valor del año contiene "1" o "Gannen" se analiza correctamente o si solo se admite "1".
- Predeterminado: analizar cadenas que contengan "1" o "Gannen" como año (`false`).
- Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.EnforceLegacyJapaneseDateParsing` | `false`: se admite "Gannen" o "1".<br/>`true`: solo se admite "1". |
| **Variable del entorno** | N/D | N/D |

## <a name="japanese-year-format"></a>Formato de año japonés

- Determina si el primer año de una era de calendario japonés tiene formato "Gannen" o un número.
- Predeterminado: dar formato al primer año como "Gannen" (`false`).
- Para obtener más información, vea [Representación de fechas en calendarios con varias eras](../../standard/datetime/working-with-calendars.md#represent-dates-in-calendars-with-multiple-eras).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `Switch.System.Globalization.FormatJapaneseFirstYearAsANumber` | `false`: dar formato como "Gannen".<br/>`true`: dar formato como número. |
| **Variable del entorno** | N/D | N/D |
