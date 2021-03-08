---
ms.openlocfilehash: 73bf0ba78e2986da3e0aa66d492f1765df563b27
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102109238"
---
### <a name="target-framework-net-framework-support-dropped"></a><span data-ttu-id="b6f7c-101">Plataforma de destino: se ha quitado la compatibilidad con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="b6f7c-101">Target framework: .NET Framework support dropped</span></span>

<span data-ttu-id="b6f7c-102">A partir de ASP.NET Core 3.0, .NET Framework es un marco de destino que no se admite.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-102">Starting with ASP.NET Core 3.0, .NET Framework is an unsupported target framework.</span></span>

#### <a name="change-description"></a><span data-ttu-id="b6f7c-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="b6f7c-103">Change description</span></span>

<span data-ttu-id="b6f7c-104">.NET Framework 4.8 es la última versión principal de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-104">.NET Framework 4.8 is the last major version of .NET Framework.</span></span> <span data-ttu-id="b6f7c-105">Las nuevas aplicaciones de ASP.NET Core se deben compilar en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-105">New ASP.NET Core apps should be built on .NET Core.</span></span> <span data-ttu-id="b6f7c-106">A partir de NET Core 3.0, puede considerar a ASP.NET Core 3.0 una parte de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-106">Starting with the .NET Core 3.0 release, you can think of ASP.NET Core 3.0 as being part of .NET Core.</span></span>

<span data-ttu-id="b6f7c-107">Los clientes que usen ASP.NET Core con .NET Framework pueden continuar utilizando la [versión 2.1 LTS](https://dotnet.microsoft.com/download/dotnet/2.1) de forma totalmente compatible.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-107">Customers using ASP.NET Core with .NET Framework can continue in a fully supported fashion using the [2.1 LTS release](https://dotnet.microsoft.com/download/dotnet/2.1).</span></span> <span data-ttu-id="b6f7c-108">La compatibilidad y el servicio para la versión 2.1 continuarán hasta el 21 de agosto de 2021.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-108">Support and servicing for 2.1 continues until at least August 21, 2021.</span></span> <span data-ttu-id="b6f7c-109">Esta fecha es tres años posterior a la declaración de la versión LTS de acuerdo a la [Directiva de compatibilidad de .NET](https://dotnet.microsoft.com/platform/support-policy).</span><span class="sxs-lookup"><span data-stu-id="b6f7c-109">This date is three years after declaration of the LTS release per the [.NET Support Policy](https://dotnet.microsoft.com/platform/support-policy).</span></span> <span data-ttu-id="b6f7c-110">La compatibilidad con los paquetes de ASP.NET Core 2.1 **en .NET Framework** se extenderá indefinidamente, de forma similar a la [directiva de servicio para otros marcos de ASP.NET basados en paquetes](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span><span class="sxs-lookup"><span data-stu-id="b6f7c-110">Support for ASP.NET Core 2.1 packages **on .NET Framework** will extend indefinitely, similar to the [servicing policy for other package-based ASP.NET frameworks](https://dotnet.microsoft.com/platform/support/policy/aspnet).</span></span>

<span data-ttu-id="b6f7c-111">Para más información sobre cómo migrar de .NET Framework a .NET Core, vea [Portabilidad a .NET Core](~/docs/core/porting/index.md).</span><span class="sxs-lookup"><span data-stu-id="b6f7c-111">For more information about porting from .NET Framework to .NET Core, see [Porting to .NET Core](~/docs/core/porting/index.md).</span></span>

<span data-ttu-id="b6f7c-112">Los paquetes `Microsoft.Extensions` (como el registro, la inserción de dependencias y la configuración) y Entity Framework Core no se ven afectados.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-112">`Microsoft.Extensions` packages (such as logging, dependency injection, and configuration) and Entity Framework Core aren't affected.</span></span> <span data-ttu-id="b6f7c-113">Seguirán admitiendo .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-113">They'll continue to support .NET Standard.</span></span>

<span data-ttu-id="b6f7c-114">Para más información sobre la motivación de este cambio, vea [la entrada de blog original](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span><span class="sxs-lookup"><span data-stu-id="b6f7c-114">For more information on the motivation for this change, see [the original blog post](https://devblogs.microsoft.com/aspnet/a-first-look-at-changes-coming-in-asp-net-core-3-0/).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="b6f7c-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="b6f7c-115">Version introduced</span></span>

<span data-ttu-id="b6f7c-116">3.0</span><span class="sxs-lookup"><span data-stu-id="b6f7c-116">3.0</span></span>

#### <a name="old-behavior"></a><span data-ttu-id="b6f7c-117">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="b6f7c-117">Old behavior</span></span>

<span data-ttu-id="b6f7c-118">Las aplicaciones ASP.NET Core se podían ejecutar en .NET Core o .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-118">ASP.NET Core apps could run on either .NET Core or .NET Framework.</span></span>

#### <a name="new-behavior"></a><span data-ttu-id="b6f7c-119">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="b6f7c-119">New behavior</span></span>

<span data-ttu-id="b6f7c-120">Las aplicaciones ASP.NET Core solo se pueden ejecutar en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-120">ASP.NET Core apps can only be run on .NET Core.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="b6f7c-121">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="b6f7c-121">Recommended action</span></span>

<span data-ttu-id="b6f7c-122">Para ello, realice las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="b6f7c-122">Take one of the following actions:</span></span>

- <span data-ttu-id="b6f7c-123">Mantenga la aplicación en ASP.NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-123">Keep your app on ASP.NET Core 2.1.</span></span>
- <span data-ttu-id="b6f7c-124">Migre la aplicación y las dependencias a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="b6f7c-124">Migrate your app and dependencies to .NET Core.</span></span>

#### <a name="category"></a><span data-ttu-id="b6f7c-125">Categoría</span><span class="sxs-lookup"><span data-stu-id="b6f7c-125">Category</span></span>

<span data-ttu-id="b6f7c-126">ASP.NET Core</span><span class="sxs-lookup"><span data-stu-id="b6f7c-126">ASP.NET Core</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b6f7c-127">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b6f7c-127">Affected APIs</span></span>

<span data-ttu-id="b6f7c-128">None</span><span class="sxs-lookup"><span data-stu-id="b6f7c-128">None</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
