---
ms.openlocfilehash: f22ee4accf9ff00814fa540adce4b9ecc6686da4
ms.sourcegitcommit: 456b3cd82a87b453fa737b4661295070d1b6d684
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "90537746"
---
<span data-ttu-id="53114-101">No es necesario ejecutar [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) porque lo ejecutan implícitamente todos los comandos que necesitan que se produzca una restauración, como `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish` y `dotnet pack`.</span><span class="sxs-lookup"><span data-stu-id="53114-101">You don't have to run [`dotnet restore`](~/docs/core/tools/dotnet-restore.md) because it's run implicitly by all commands that require a restore to occur, such as `dotnet new`, `dotnet build`, `dotnet run`, `dotnet test`, `dotnet publish`, and `dotnet pack`.</span></span> <span data-ttu-id="53114-102">Para deshabilitar la restauración implícita, use la opción `--no-restore`.</span><span class="sxs-lookup"><span data-stu-id="53114-102">To disable implicit restore, use the `--no-restore` option.</span></span>

<span data-ttu-id="53114-103">El comando `dotnet restore` sigue siendo válido en algunos escenarios donde tiene sentido realizar una restauración explícita, como las [compilaciones de integración continua en Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) o en los sistemas de compilación que necesitan controlar explícitamente cuándo se produce la restauración.</span><span class="sxs-lookup"><span data-stu-id="53114-103">The `dotnet restore` command is still useful in certain scenarios where explicitly restoring makes sense, such as [continuous integration builds in Azure DevOps Services](/azure/devops/build-release/apps/aspnet/build-aspnet-core) or in build systems that need to explicitly control when the restore occurs.</span></span>

<span data-ttu-id="53114-104">Para obtener información sobre cómo administrar fuentes de NuGet, vea la [documentación de `dotnet restore`](../docs/core/tools/dotnet-restore.md).</span><span class="sxs-lookup"><span data-stu-id="53114-104">For information about how to manage NuGet feeds, see the [`dotnet restore` documentation](../docs/core/tools/dotnet-restore.md).</span></span>
