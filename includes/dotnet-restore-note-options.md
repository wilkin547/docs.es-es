---
ms.openlocfilehash: 19002cce40fdc929716a761a5e01303be4decb35
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90537838"
---
No es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que necesitan que se produzca una restauración, como `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` y `dotnet pack`. Para deshabilitar la restauración implícita, use la opción `--no-restore`.

El comando `dotnet restore` sigue siendo válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente cuándo se produce la restauración.

Para obtener información sobre cómo administrar fuentes de NuGet, vea la [documentación de `dotnet restore`](../docs/core/tools/dotnet-restore.md).

Este comando admite las opciones de `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`). No se admiten las opciones de formato corto, como `-s`.
