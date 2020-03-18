---
ms.openlocfilehash: 4d99d0b6e99a7a9b976cf11832b33ad3bdc6d299
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "75902015"
---
### <a name="hosting-objectpoolprovider-removed-from-webhostbuilder-dependencies"></a><span data-ttu-id="13e4e-101">Hospedaje: se ha quitado ObjectPoolProvider de las dependencias de WebHostBuilder</span><span class="sxs-lookup"><span data-stu-id="13e4e-101">Hosting: ObjectPoolProvider removed from WebHostBuilder dependencies</span></span>

<span data-ttu-id="13e4e-102">Para aumentar la naturaleza de pago por uso de ASP.NET Core, se ha quitado `ObjectPoolProvider` del conjunto principal de dependencias.</span><span class="sxs-lookup"><span data-stu-id="13e4e-102">As part of making ASP.NET Core more pay for play, the `ObjectPoolProvider` was removed from the main set of dependencies.</span></span> <span data-ttu-id="13e4e-103">Ahora componentes específicos que dependen de `ObjectPoolProvider` lo agregan por sí mismos.</span><span class="sxs-lookup"><span data-stu-id="13e4e-103">Specific components relying on `ObjectPoolProvider` now add it themselves.</span></span>

<span data-ttu-id="13e4e-104">Para obtener información, vea [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span><span class="sxs-lookup"><span data-stu-id="13e4e-104">For discussion, see [dotnet/aspnetcore#5944](https://github.com/dotnet/aspnetcore/issues/5944).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="13e4e-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="13e4e-105">Version introduced</span></span>

<span data-ttu-id="13e4e-106">3.0</span><span class="sxs-lookup"><span data-stu-id="13e4e-106">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="13e4e-107">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="13e4e-107">Old behavior</span></span>

<span data-ttu-id="13e4e-108">`WebHostBuilder` proporciona `ObjectPoolProvider` de forma predeterminada en el contenedor de DI.</span><span class="sxs-lookup"><span data-stu-id="13e4e-108">`WebHostBuilder` provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="13e4e-109">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="13e4e-109">New behavior</span></span>

<span data-ttu-id="13e4e-110">`WebHostBuilder` ya no proporciona `ObjectPoolProvider` de forma predeterminada en el contenedor de DI.</span><span class="sxs-lookup"><span data-stu-id="13e4e-110">`WebHostBuilder` no longer provides `ObjectPoolProvider` by default in the DI container.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="13e4e-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="13e4e-111">Reason for change</span></span>

<span data-ttu-id="13e4e-112">Este cambio se ha realizado para aumentar la naturaleza de pago por uso de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="13e4e-112">This change was made to make ASP.NET Core more pay for play.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="13e4e-113">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="13e4e-113">Recommended action</span></span>

<span data-ttu-id="13e4e-114">Si el componente requiere `ObjectPoolProvider`, tendrá que agregarlo a las dependencias mediante `IServiceCollection`.</span><span class="sxs-lookup"><span data-stu-id="13e4e-114">If your component requires `ObjectPoolProvider`, it needs to be added to your dependencies via the `IServiceCollection`.</span></span>

#### <a name="category"></a><span data-ttu-id="13e4e-115">Categoría</span><span class="sxs-lookup"><span data-stu-id="13e4e-115">Category</span></span>

<span data-ttu-id="13e4e-116">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="13e4e-116">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="13e4e-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="13e4e-117">Affected APIs</span></span>

<span data-ttu-id="13e4e-118">None</span><span class="sxs-lookup"><span data-stu-id="13e4e-118">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
