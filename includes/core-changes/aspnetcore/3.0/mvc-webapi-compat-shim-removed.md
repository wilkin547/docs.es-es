---
ms.openlocfilehash: 75945e7ff26c1c6db891d12cef4c16ed210da6af
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032842"
---
### <a name="mvc-web-api-compatibility-shim-removed"></a><span data-ttu-id="1b5e7-101">MVC: se han quitado las correcciones de compatibilidad (shim) con la API web</span><span class="sxs-lookup"><span data-stu-id="1b5e7-101">MVC: Web API compatibility shim removed</span></span>

<span data-ttu-id="1b5e7-102">A partir de ASP.NET Core 3.0, el paquete `Microsoft.AspNetCore.Mvc.WebApiCompatShim` ya no está disponible.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-102">Starting with ASP.NET Core 3.0, the `Microsoft.AspNetCore.Mvc.WebApiCompatShim` package is no longer available.</span></span>

#### <a name="change-description"></a><span data-ttu-id="1b5e7-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="1b5e7-103">Change description</span></span>

<span data-ttu-id="1b5e7-104">El paquete `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) proporciona compatibilidad parcial en ASP.NET Core con ASP.NET 4.x Web API 2 para simplificar la migración de implementaciones existentes de API web a ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-104">The `Microsoft.AspNetCore.Mvc.WebApiCompatShim` (WebApiCompatShim) package provides partial compatibility in ASP.NET Core with ASP.NET 4.x Web API 2 to simplify migrating existing Web API implementations to ASP.NET Core.</span></span> <span data-ttu-id="1b5e7-105">Pero las aplicaciones que usan WebApiCompatShim no se benefician de las características relacionadas con la API que se distribuyen en versiones recientes de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-105">However, apps using the WebApiCompatShim don't benefit from the API-related features shipping in recent ASP.NET Core releases.</span></span> <span data-ttu-id="1b5e7-106">Estas características incluyen la generación mejorada de especificaciones de Open API, el control de errores estandarizado y la generación de código de cliente.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-106">Such features include improved Open API specification generation, standardized error handling, and client code generation.</span></span> <span data-ttu-id="1b5e7-107">Para centrar mejor los esfuerzos de API en la versión 3.0, se ha quitado WebApiCompatShim.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-107">To better focus the API efforts in 3.0, WebApiCompatShim was removed.</span></span> <span data-ttu-id="1b5e7-108">Las aplicaciones existentes en las que se usa WebApiCompatShim se deben migrar al modelo de `[ApiController]` más reciente.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-108">Existing apps using the WebApiCompatShim should migrate to the newer `[ApiController]` model.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="1b5e7-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1b5e7-109">Version introduced</span></span>

<span data-ttu-id="1b5e7-110">3.0</span><span class="sxs-lookup"><span data-stu-id="1b5e7-110">3.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="1b5e7-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="1b5e7-111">Reason for change</span></span>

<span data-ttu-id="1b5e7-112">La corrección de compatibilidad (shim) de la API web era una herramienta de migración.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-112">The Web API compatibility shim was a migration tool.</span></span> <span data-ttu-id="1b5e7-113">Restringe el acceso de los usuarios a la nueva funcionalidad agregada en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-113">It restricts user access to new functionality added in ASP.NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1b5e7-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1b5e7-114">Recommended action</span></span>

<span data-ttu-id="1b5e7-115">Quite el uso de esta corrección de compatibilidad y migre directamente a la funcionalidad similar en ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="1b5e7-115">Remove usage of this shim and migrate directly to the similar functionality in ASP.NET Core itself.</span></span>

#### <a name="category"></a><span data-ttu-id="1b5e7-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="1b5e7-116">Category</span></span>

<span data-ttu-id="1b5e7-117">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="1b5e7-117">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1b5e7-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1b5e7-118">Affected APIs</span></span>

<xref:Microsoft.AspNetCore.Mvc.WebApiCompatShim?displayProperty=fullName>

<!--

#### Affected APIs

N:Microsoft.AspNetCore.Mvc.WebApiCompatShim

-->
