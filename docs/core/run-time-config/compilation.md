---
title: Valores de configuración de la compilación
description: Obtenga información sobre los valores del entorno de ejecución que configuran cómo funciona el compilador JIT para las aplicaciones de .NET Core.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998880"
---
# <a name="run-time-configuration-options-for-compilation"></a>Opciones de configuración del entorno de ejecución para compilación

## <a name="tiered-compilation"></a>Compilación en niveles

- Configura si el compilador JIT utiliza la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).
- En la versión 3.0 de .NET Core y posteriores, la compilación en niveles está habilitada de forma predeterminada.
- En las versiones 2.1 y 2.2 de .NET Core, la compilación en niveles está deshabilitada de forma predeterminada.

| | Nombre del valor | Valores |
| - | - | - |
| **runtimeconfig.json** | `System.Runtime.TieredCompilation` | `true`: habilitado.<br/>`false`: deshabilitado. |
| **Variable del entorno** | `COMPlus_TieredCompilation` | `1`: habilitado.<br/>`0`: deshabilitado. |
