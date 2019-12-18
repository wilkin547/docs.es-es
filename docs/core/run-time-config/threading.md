---
title: Valores de configuración de los subprocesos
description: Obtenga información sobre los valores del entorno de ejecución que configuran los subprocesos para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: 6a920dbc301830e3f4c95bf637ff3de6d4f464ff
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998832"
---
# <a name="run-time-configuration-options-for-threading"></a>Opciones de configuración del entorno de ejecución para subprocesos

## <a name="cpu-groups"></a>Grupos de CPU

- Configura si los subprocesos se distribuyen automáticamente entre los grupos de CPU.
- Predeterminado: deshabilitado (`0`).

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_Thread_UseAllCpuGroups` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="minimum-threads"></a>Mínimo de subprocesos

- Especifica el número mínimo de subprocesos para el grupo de subprocesos de trabajo.
- Corresponde al método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Entero que representa el número mínimo de subprocesos. |
| **Variable del entorno** | N/D | N/D |

## <a name="maximum-threads"></a>Máximo de subprocesos

- Especifica el número máximo de subprocesos para el grupo de subprocesos de trabajo.
- Corresponde al método <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Entero que representa el número máximo de subprocesos. |
| **Variable del entorno** | N/D | N/D |
