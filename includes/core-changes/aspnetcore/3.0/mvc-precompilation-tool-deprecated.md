---
ms.openlocfilehash: 8395428e1729a00fc1af72cf53fe689ee95b5fdf
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721085"
---
### <a name="mvc-precompilation-tool-deprecated"></a><span data-ttu-id="02b19-101">MVC: herramienta de precompilación en desuso</span><span class="sxs-lookup"><span data-stu-id="02b19-101">MVC: Precompilation tool deprecated</span></span>

<span data-ttu-id="02b19-102">En ASP.NET Core 1.1, se presentó el paquete `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (herramienta de precompilación MVC) para agregar compatibilidad con la compilación en tiempo de publicación de archivos Razor (archivos *.cshtml*).</span><span class="sxs-lookup"><span data-stu-id="02b19-102">In ASP.NET Core 1.1, the `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` (MVC precompilation tool) package was introduced to add support for publish-time compilation of Razor files (*.cshtml* files).</span></span> <span data-ttu-id="02b19-103">En ASP.NET Core 2.1, se presentó el [SDK de Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) para ampliar las características de la herramienta de precompilación.</span><span class="sxs-lookup"><span data-stu-id="02b19-103">In ASP.NET Core 2.1, the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-2.1) was introduced to expand upon features of the precompilation tool.</span></span> <span data-ttu-id="02b19-104">El SDK de Razor agregaba compatibilidad con los archivos Razor en tiempo de compilación y publicación.</span><span class="sxs-lookup"><span data-stu-id="02b19-104">The Razor SDK added support for build- and publish-time compilation of Razor files.</span></span> <span data-ttu-id="02b19-105">El SDK comprueba la exactitud de los archivos *.cshtml* en tiempo de compilación mientras mejora el tiempo de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02b19-105">The SDK verifies the correctness of *.cshtml* files at build time while improving on app startup time.</span></span> <span data-ttu-id="02b19-106">El SDK de Razor está activado de forma predeterminada y no se requiere ningún gesto para empezar a usarlo.</span><span class="sxs-lookup"><span data-stu-id="02b19-106">The Razor SDK is on by default, and no gesture is required to start using it.</span></span>

<span data-ttu-id="02b19-107">En ASP.NET Core 3.0, se quitó la herramienta de precompilación MVC de ASP.NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="02b19-107">In ASP.NET Core 3.0, the ASP.NET Core 1.1-era MVC precompilation tool was removed.</span></span> <span data-ttu-id="02b19-108">Las versiones anteriores del paquete seguirán recibiendo correcciones de seguridad y de errores importantes en la versión de revisión.</span><span class="sxs-lookup"><span data-stu-id="02b19-108">Earlier package versions will continue receiving important bug and security fixes in the patch release.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="02b19-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="02b19-109">Version introduced</span></span>

<span data-ttu-id="02b19-110">3.0</span><span class="sxs-lookup"><span data-stu-id="02b19-110">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="02b19-111">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="02b19-111">Old behavior</span></span>

<span data-ttu-id="02b19-112">El paquete `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` se usaba para compilar previamente las vistas de Razor de MVC.</span><span class="sxs-lookup"><span data-stu-id="02b19-112">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package was used to pre-compile MVC Razor views.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="02b19-113">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="02b19-113">New behavior</span></span>

<span data-ttu-id="02b19-114">El SDK de Razor es compatible de forma nativa con esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="02b19-114">The Razor SDK natively supports this functionality.</span></span> <span data-ttu-id="02b19-115">El paquete `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` ya no está actualizado.</span><span class="sxs-lookup"><span data-stu-id="02b19-115">The `Microsoft.AspNetCore.Mvc.Razor.ViewCompilation` package is no longer updated.</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="02b19-116">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="02b19-116">Reason for change</span></span>

<span data-ttu-id="02b19-117">El SDK de Razor proporciona más funcionalidad y comprueba la exactitud de los archivos *.cshtml* en tiempo de compilación.</span><span class="sxs-lookup"><span data-stu-id="02b19-117">The Razor SDK provides more functionality and verifies the correctness of *.cshtml* files at build time.</span></span> <span data-ttu-id="02b19-118">El SDK también mejora el tiempo de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="02b19-118">The SDK also improves app startup time.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="02b19-119">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="02b19-119">Recommended action</span></span>

<span data-ttu-id="02b19-120">Para los usuarios de ASP.NET Core 2.1 o versiones posteriores, actualice para usar la compatibilidad nativa con la precompilación en el [SDK de Razor](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="02b19-120">For users of ASP.NET Core 2.1 or later, update to use the native support for precompilation in the [Razor SDK](/aspnet/core/razor-pages/sdk?view=aspnetcore-3.0).</span></span> <span data-ttu-id="02b19-121">Si los errores o las características que faltan impiden la migración al SDK de Razor, abra una incidencia en [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span><span class="sxs-lookup"><span data-stu-id="02b19-121">If bugs or missing features prevent migration to the Razor SDK, open an issue at [dotnet/aspnetcore](https://github.com/dotnet/aspnetcore/issues).</span></span>

#### <a name="category"></a><span data-ttu-id="02b19-122">Categoría</span><span class="sxs-lookup"><span data-stu-id="02b19-122">Category</span></span>

<span data-ttu-id="02b19-123">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="02b19-123">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="02b19-124">API afectadas</span><span class="sxs-lookup"><span data-stu-id="02b19-124">Affected APIs</span></span>

<span data-ttu-id="02b19-125">None</span><span class="sxs-lookup"><span data-stu-id="02b19-125">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
