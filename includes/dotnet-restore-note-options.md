---
ms.openlocfilehash: 6c04437c2a211b244e6c5eda0893b267c59668e9
ms.sourcegitcommit: 73aa9653547a1cd70ee6586221f79cc29b588ebd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2020
ms.locfileid: "82102779"
---
<span data-ttu-id="dc8be-101">No es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que necesitan que se produzca una restauración, como `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` y `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="dc8be-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="dc8be-102">Para deshabilitar la restauración implícita, use la opción `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="dc8be-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="dc8be-103">El comando `dotnet restore` sigue siendo válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente cuándo se produce la restauración.</span><span class="sxs-lookup"><span data-stu-id="dc8be-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](https://docs.microsoft.com/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="dc8be-104">Para obtener información sobre cómo administrar fuentes de NuGet, vea la [documentación de `dotnet restore`](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="dc8be-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>

<span data-ttu-id="dc8be-105">Este comando admite las opciones de `dotnet restore` cuando se pasan con el formato largo (por ejemplo, `--source`).</span><span class="sxs-lookup"><span data-stu-id="dc8be-105">This command supports the `dotnet restore` options when passed in the long form (for example, `--source`).</span></span> <span data-ttu-id="dc8be-106">No se admiten las opciones de formato corto, como `-s`.</span><span class="sxs-lookup"><span data-stu-id="dc8be-106">Short form options, such as `-s`, are not supported.</span></span>
