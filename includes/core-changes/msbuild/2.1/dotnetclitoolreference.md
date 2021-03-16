---
ms.openlocfilehash: d9489df1ba096109e60d663e3a3f4442d30b2bb1
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105477"
---
### <a name="project-tools-now-included-in-sdk"></a><span data-ttu-id="49f58-101">Herramientas de proyecto ahora incluidas en el SDK</span><span class="sxs-lookup"><span data-stu-id="49f58-101">Project tools now included in SDK</span></span>

<span data-ttu-id="49f58-102">El SDK de .NET Core 2.1 ahora incluye herramientas comunes de la CLI y ya no es necesario hacer referencia a estas herramientas desde el proyecto.</span><span class="sxs-lookup"><span data-stu-id="49f58-102">The .NET Core 2.1 SDK now includes common CLI tooling, and you no longer need to reference these tools from the project.</span></span>

#### <a name="change-description"></a><span data-ttu-id="49f58-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="49f58-103">Change description</span></span>

<span data-ttu-id="49f58-104">En .NET Core 2.0, los proyectos hacen referencia a herramientas de .NET externas con la opción de configuración `<DotNetCliToolReference>` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="49f58-104">In .NET Core 2.0, projects reference external .NET tools with the `<DotNetCliToolReference>` project setting.</span></span> <span data-ttu-id="49f58-105">En .NET Core 2.1, algunas de estas herramientas se incluyen en el SDK de .NET Core y esa configuración ya no es necesaria.</span><span class="sxs-lookup"><span data-stu-id="49f58-105">In .NET Core 2.1, some of these tools are included with the .NET Core SDK, and the setting is no longer needed.</span></span> <span data-ttu-id="49f58-106">Si incluye referencias a estas herramientas en el proyecto, recibirá un error parecido al siguiente: **La herramienta "Microsoft.EntityFrameworkCore.Tools.DotNet" se incluye ahora en el SDK de .NET Core**.</span><span class="sxs-lookup"><span data-stu-id="49f58-106">If you include references to these tools in your project, you'll receive an error similar to the following: **The tool 'Microsoft.EntityFrameworkCore.Tools.DotNet' is now included in the .NET Core SDK.**</span></span>

<span data-ttu-id="49f58-107">Herramientas ahora incluidas en el SDK de .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="49f58-107">Tools now included in .NET Core 2.1 SDK:</span></span>

| <span data-ttu-id="49f58-108">Valor de \<DotNetCliToolReference></span><span class="sxs-lookup"><span data-stu-id="49f58-108">\<DotNetCliToolReference> value</span></span>                   | <span data-ttu-id="49f58-109">Herramienta</span><span class="sxs-lookup"><span data-stu-id="49f58-109">Tool</span></span>                                                                                                            |
|------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `Microsoft.DotNet.Watcher.Tools`               | [<span data-ttu-id="49f58-110">dotnet-watch</span><span class="sxs-lookup"><span data-stu-id="49f58-110">dotnet-watch</span></span>](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-watch/README.md)               |
| `Microsoft.Extensions.SecretManager.Tools`     | [<span data-ttu-id="49f58-111">dotnet-user-secrets</span><span class="sxs-lookup"><span data-stu-id="49f58-111">dotnet-user-secrets</span></span>](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-user-secrets/README.md) |
| `Microsoft.Extensions.Caching.SqlConfig.Tools` | [<span data-ttu-id="49f58-112">dotnet-sql-cache</span><span class="sxs-lookup"><span data-stu-id="49f58-112">dotnet-sql-cache</span></span>](https://github.com/dotnet/aspnetcore/blob/master/src/Tools/dotnet-sql-cache/README.md)       |
| `Microsoft.EntityFrameworkCore.Tools.DotNet`   | [<span data-ttu-id="49f58-113">dotnet-ef</span><span class="sxs-lookup"><span data-stu-id="49f58-113">dotnet-ef</span></span>](/ef/core/miscellaneous/cli/dotnet)                                                                  |

#### <a name="version-introduced"></a><span data-ttu-id="49f58-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="49f58-114">Version introduced</span></span>

<span data-ttu-id="49f58-115">SDK de .NET Core 2.1.300</span><span class="sxs-lookup"><span data-stu-id="49f58-115">.NET Core SDK 2.1.300</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="49f58-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="49f58-116">Recommended action</span></span>

<span data-ttu-id="49f58-117">Quite la configuración `<DotNetCliToolReference>` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="49f58-117">Remove the `<DotNetCliToolReference>` setting from your project.</span></span>

#### <a name="category"></a><span data-ttu-id="49f58-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="49f58-118">Category</span></span>

<span data-ttu-id="49f58-119">MSBuild</span><span class="sxs-lookup"><span data-stu-id="49f58-119">MSBuild</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="49f58-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="49f58-120">Affected APIs</span></span>

<span data-ttu-id="49f58-121">N/D</span><span class="sxs-lookup"><span data-stu-id="49f58-121">N/A</span></span>
