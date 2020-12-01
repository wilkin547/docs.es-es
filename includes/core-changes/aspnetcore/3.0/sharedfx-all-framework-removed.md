---
ms.openlocfilehash: 959f3959c28c7d0159be7a213986345e2865b9a2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032863"
---
### <a name="shared-framework-removed-microsoftaspnetcoreall"></a><span data-ttu-id="12296-101">Marco compartido: se ha eliminado Microsoft.AspNetCore.All</span><span class="sxs-lookup"><span data-stu-id="12296-101">Shared framework: Removed Microsoft.AspNetCore.All</span></span>

<span data-ttu-id="12296-102">A partir de ASP.NET Core 3.0, ya no se generan el metapaquete `Microsoft.AspNetCore.All` y el marco compartido `Microsoft.AspNetCore.All` correspondiente.</span><span class="sxs-lookup"><span data-stu-id="12296-102">Starting in ASP.NET Core 3.0, the `Microsoft.AspNetCore.All` metapackage and the matching `Microsoft.AspNetCore.All` shared framework are no longer produced.</span></span> <span data-ttu-id="12296-103">Este paquete está disponible en ASP.NET Core 2.2 y seguirá recibiendo actualizaciones de mantenimiento en ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="12296-103">This package is available in ASP.NET Core 2.2 and will continue to receive servicing updates in ASP.NET Core 2.1.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="12296-104">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="12296-104">Version introduced</span></span>

<span data-ttu-id="12296-105">3.0</span><span class="sxs-lookup"><span data-stu-id="12296-105">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="12296-106">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="12296-106">Old behavior</span></span>

<span data-ttu-id="12296-107">Las aplicaciones podían usar el metapaquete `Microsoft.AspNetCore.All` para seleccionar como destino el marco compartido `Microsoft.AspNetCore.All` en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="12296-107">Apps could use the `Microsoft.AspNetCore.All` metapackage to target the `Microsoft.AspNetCore.All` shared framework on .NET Core.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="12296-108">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="12296-108">New behavior</span></span>

<span data-ttu-id="12296-109">En .NET Core 3.0 no se incluye un marco compartido `Microsoft.AspNetCore.All`.</span><span class="sxs-lookup"><span data-stu-id="12296-109">.NET Core 3.0 doesn't include a `Microsoft.AspNetCore.All` shared framework.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="12296-110">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="12296-110">Reason for change</span></span>

<span data-ttu-id="12296-111">En el metapaquete `Microsoft.AspNetCore.All` se incluía un gran número de dependencias externas.</span><span class="sxs-lookup"><span data-stu-id="12296-111">The `Microsoft.AspNetCore.All` metapackage included a large number of external dependencies.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="12296-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="12296-112">Recommended action</span></span>

<span data-ttu-id="12296-113">Migre el proyecto para usar el marco `Microsoft.AspNetCore.App`.</span><span class="sxs-lookup"><span data-stu-id="12296-113">Migrate your project to use the `Microsoft.AspNetCore.App` framework.</span></span> <span data-ttu-id="12296-114">Los componentes que anteriormente estaban disponibles en `Microsoft.AspNetCore.All` lo siguen estando en NuGet.</span><span class="sxs-lookup"><span data-stu-id="12296-114">Components that were previously available in `Microsoft.AspNetCore.All` are still available on NuGet.</span></span> <span data-ttu-id="12296-115">Ahora esos componentes se implementan con la aplicación en lugar de incluirse en el marco compartido.</span><span class="sxs-lookup"><span data-stu-id="12296-115">Those components are now deployed with your app instead of being included in the shared framework.</span></span>

#### <a name="category"></a><span data-ttu-id="12296-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="12296-116">Category</span></span>

<span data-ttu-id="12296-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="12296-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="12296-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="12296-118">Affected APIs</span></span>

<span data-ttu-id="12296-119">None</span><span class="sxs-lookup"><span data-stu-id="12296-119">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
