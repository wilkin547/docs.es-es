---
title: Depuración de la configuración de la generación de perfiles
description: Obtenga información sobre los valores del entorno de ejecución que configuran la depuración y la generación de perfiles para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: c57cfa7233f48def890ded3c9d589b7f268147df
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998862"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Opciones de configuración del ejecución para la depuración y la generación de perfiles

## <a name="enable-diagnostics"></a>Habilitación de diagnósticos

- Configura si el depurador, el generador de perfiles y los diagnósticos de EventPipe están habilitados o deshabilitados.
- Predeterminado: habilitado (`1`).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_EnableDiagnostics` | `1`: habilitado.<br/>`0`: deshabilitado. |

## <a name="enable-profiling"></a>Habilitación de la generación de perfiles

- Configura si la generación de perfiles está habilitada para el proceso que se ejecuta actualmente.
- Predeterminado: deshabilitado (`0`).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `CORECLR_ENABLE_PROFILING` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="profiler-guid"></a>GUID de generador de perfiles

- Especifica el GUID del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente.

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `CORECLR_PROFILER` | *string-guid* |

## <a name="profiler-location"></a>Ubicación del generador de perfiles

- Especifica la ruta de acceso a la biblioteca de vínculos dinámicos del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente (proceso de 32 bits o de 64 bits).
- Si se establece más de una variable, las variables concretas de valor de bits tienen prioridad. Especifican el valor de bits del generador de perfiles que se va a cargar.
- Para obtener más información, vea [Búsqueda de la biblioteca del generador de perfiles](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).

| | Nombre del valor | Valores |
| - | - | - |
| **Variable del entorno** | `CORECLR_PROFILER_PATH` | *string-path* |
| **Variable del entorno** | `CORECLR_PROFILER_PATH_32` | *string-path* |
| **Variable del entorno** | `CORECLR_PROFILER_PATH_64` | *string-path* |

## <a name="write-perf-map"></a>Escritura del mapa de rendimiento

- Habilita o deshabilita la escritura de */tmp/perf-$pid.map* en los sistemas Linux.
- Predeterminado: deshabilitado (`0`).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_PerfMapEnabled` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="perf-log-markers"></a>Marcadores del registro de rendimiento

- Cuando `COMPlus_PerfMapEnabled` se establece en `1`, habilita o deshabilita la señal especificada que se va a aceptar y omitir como marcador en los registros de rendimiento.
- Predeterminado: deshabilitado (`0`).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_PerfMapIgnoreSignal` | `0`: deshabilitado.<br/>`1`: habilitado. |
