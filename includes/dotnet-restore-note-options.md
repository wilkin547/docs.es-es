---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "72179977"
---
> [!NOTE]
> A partir de .NET Core 2.0, no es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que requieren que se produzca una restauración, como `dotnet build` y `dotnet run`. Sigue siendo un comando válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente la hora a la que se produce la restauración.
>
> Este comando también admite las opciones `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`). No se admiten las opciones de formato corto, como `-s`.
