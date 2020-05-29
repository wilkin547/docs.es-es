---
title: Depuración de la configuración de la generación de perfiles
description: Obtenga información sobre los valores del entorno de ejecución que configuran la depuración y la generación de perfiles para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 5efd0f776da4b7ce6ff7f3bdfda24feec6e00f79
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83761998"
---
# <a name="run-time-configuration-options-for-debugging-and-profiling"></a>Opciones de configuración del ejecución para la depuración y la generación de perfiles

## <a name="enable-diagnostics"></a>Habilitación de diagnósticos

- Configura si el depurador, el generador de perfiles y los diagnósticos de EventPipe están habilitados o deshabilitados.
- Si se omite esta configuración, se habilitan los diagnósticos. Esto es equivalente a establecer el valor en `1`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_EnableDiagnostics` | `1`: habilitado.<br/>`0`: deshabilitado. |

## <a name="enable-profiling"></a>Habilitación de la generación de perfiles

- Configura si la generación de perfiles está habilitada para el proceso que se ejecuta actualmente.
- Si se omite esta configuración, la generación de perfiles está deshabilitada. Esto es equivalente a establecer el valor en `0`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `CORECLR_ENABLE_PROFILING` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="profiler-guid"></a>GUID de generador de perfiles

- Especifica el GUID del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `CORECLR_PROFILER` | *string-guid* |

## <a name="profiler-location"></a>Ubicación del generador de perfiles

- Especifica la ruta de acceso a la biblioteca de vínculos dinámicos del generador de perfiles que se va a cargar en el proceso que se ejecuta actualmente (proceso de 32 bits o de 64 bits).
- Si se establece más de una variable, las variables concretas de valor de bits tienen prioridad. Especifican el valor de bits del generador de perfiles que se va a cargar.
- Para obtener más información, vea [Búsqueda de la biblioteca del generador de perfiles](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/profiling/Profiler%20Loading.md).

| | Nombre de valor | Valores |
| - | - | - |
| **Variable del entorno** | `CORECLR_PROFILER_PATH` | *string-path* |
| **Variable del entorno** | `CORECLR_PROFILER_PATH_32` | *string-path* |
| **Variable del entorno** | `CORECLR_PROFILER_PATH_64` | *string-path* |

## <a name="write-perf-map"></a>Escritura del mapa de rendimiento

- Habilita o deshabilita la escritura de */tmp/perf-$pid.map* en los sistemas Linux.
- Si se omite esta configuración, la escritura del mapa de rendimiento está deshabilitada. Esto es equivalente a establecer el valor en `0`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_PerfMapEnabled` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="perf-log-markers"></a>Marcadores del registro de rendimiento

- Habilita o deshabilita la señal especificada que se va a aceptar y omitir como marcador en los registros de rendimiento.
- Si se omite este valor, la señal especificada no se pasa por alto. Esto es equivalente a establecer el valor en `0`.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_PerfMapIgnoreSignal` | `0`: deshabilitado.<br/>`1`: habilitado. |

> [!NOTE]
> Este valor se omite si se omite [COMPlus_PerfMapEnabled](#write-perf-map) o se establece en `0` (es decir, deshabilitado).
