---
title: Valores de configuración de los subprocesos
description: Obtenga información sobre los valores del entorno de ejecución que configuran los subprocesos para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: ed7688d4d8f7178440fe59afc6e2f5e0a11b2a5c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733435"
---
# <a name="run-time-configuration-options-for-threading"></a>Opciones de configuración del entorno de ejecución para subprocesos

## <a name="cpu-groups"></a>Grupos de CPU

- Configura si los subprocesos se distribuyen automáticamente entre los grupos de CPU.
- Predeterminado: deshabilitado (`0`).

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | N/D | N/D |
| **Variable del entorno** | `COMPlus_Thread_UseAllCpuGroups` | `0`: deshabilitado.<br/>`1`: habilitado. |

## <a name="minimum-threads"></a>Mínimo de subprocesos

- Especifica el número mínimo de subprocesos para el grupo de subprocesos de trabajo.
- Corresponde al método <xref:System.Threading.ThreadPool.SetMinThreads%2A?displayProperty=nameWithType>.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MinThreads` | Entero que representa el número mínimo de subprocesos. |
| **Propiedad de MSBuild** | `ThreadPoolMinThreads` | Entero que representa el número mínimo de subprocesos. |
| **Variable del entorno** | N/D | N/D |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MinThreads": 4
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  </PropertyGroup>

</Project>
```

## <a name="maximum-threads"></a>Máximo de subprocesos

- Especifica el número máximo de subprocesos para el grupo de subprocesos de trabajo.
- Corresponde al método <xref:System.Threading.ThreadPool.SetMaxThreads%2A?displayProperty=nameWithType>.

| | Nombre de valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Threading.ThreadPool.MaxThreads` | Entero que representa el número máximo de subprocesos. |
| **Propiedad de MSBuild** | `ThreadPoolMaxThreads` | Entero que representa el número máximo de subprocesos. |
| **Variable del entorno** | N/D | N/D |

### <a name="examples"></a>Ejemplos

Archivo *runtimeconfig.json*:

```json
{
   "runtimeOptions": {
      "configProperties": {
         "System.Threading.ThreadPool.MaxThreads": 20
      }
   }
}
```

Archivo del proyecto:

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
  </PropertyGroup>

</Project>
```
