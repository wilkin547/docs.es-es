---
ms.openlocfilehash: f22ee4accf9ff00814fa540adce4b9ecc6686da4
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "90537746"
---
No es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que necesitan que se produzca una restauración, como `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` y `dotnet pack`. Para deshabilitar la restauración implícita, use la opción `--no-restore`.

El comando `dotnet restore` sigue siendo válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente cuándo se produce la restauración.

Para obtener información sobre cómo administrar fuentes de NuGet, vea la [documentación de `dotnet restore`](../docs/core/tools/dotnet-restore.md).
