---
ms.openlocfilehash: 497ac09e5c9a10470d3ae1932d7e3dc114d121dd
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632016"
---
> [!NOTE]
> A partir de .NET Core 2.0, no es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque se ejecuta implícitamente por todos los comandos, como `dotnet build` y `dotnet run`, que requieren que se produzca una restauración. Sigue siendo un comando válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente la hora a la que se produce la restauración.
>
> Este comando también admite las opciones `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`). No se admiten las opciones de formato corto, como `-s`.
