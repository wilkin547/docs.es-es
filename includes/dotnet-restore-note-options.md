---
ms.openlocfilehash: 47811d3fab2e4fa531d383dfe818e3cac5613eb3
ms.sourcegitcommit: dfd612ba454ce775a766bcc6fe93bc1d43dfda47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/09/2019
ms.locfileid: "72179977"
---
> [!NOTE]
> A partir de .NET Core 2.0, no es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que requieren que se produzca una restauración, como `dotnet build` y `dotnet run`. Sigue siendo un comando válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente la hora a la que se produce la restauración.
>
> Este comando también admite las opciones `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`). No se admiten las opciones de formato corto, como `-s`.
