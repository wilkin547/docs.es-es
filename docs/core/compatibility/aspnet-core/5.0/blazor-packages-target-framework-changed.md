---
title: 'Cambio importante: Blazor: Plataforma de destino de paquetes NuGet cambiada'
description: 'Obtenga información sobre el cambio importante en ASP.NET Core 5.0 titulado Blazor: Plataforma de destino de paquetes NuGet cambiada'
author: scottaddie
ms.author: scaddie
ms.date: 10/01/2020
ms.openlocfilehash: 5515edc66ff9786f0d8f7e24e5fc28c71502567b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760164"
---
# <a name="blazor-target-framework-of-nuget-packages-changed"></a><span data-ttu-id="5fe3d-103">Blazor: Plataforma de destino de paquetes NuGet cambiada</span><span class="sxs-lookup"><span data-stu-id="5fe3d-103">Blazor: Target framework of NuGet packages changed</span></span>

<span data-ttu-id="5fe3d-104">Los proyectos WebAssembly de Blazor 3.2 se han compilado para tener como destino .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="5fe3d-104">Blazor 3.2 WebAssembly projects were compiled to target .NET Standard 2.1 (`<TargetFramework>netstandard2.1</TargetFramework>`).</span></span> <span data-ttu-id="5fe3d-105">En ASP.NET Core 5.0, los proyectos de Blazor Server y Blazor WebAssembly tienen como destino .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span><span class="sxs-lookup"><span data-stu-id="5fe3d-105">In ASP.NET Core 5.0, both Blazor Server and Blazor WebAssembly projects target .NET 5.0 (`<TargetFramework>net5.0</TargetFramework>`).</span></span> <span data-ttu-id="5fe3d-106">Para alinearse mejor con el cambio de la plataforma de destino, los siguientes paquetes de Blazor ya no tienen como destino .NET Standard 2.1:</span><span class="sxs-lookup"><span data-stu-id="5fe3d-106">To better align with the target framework change, the following Blazor packages no longer target .NET Standard 2.1:</span></span>

* [<span data-ttu-id="5fe3d-107">Microsoft.AspNetCore.Components</span><span class="sxs-lookup"><span data-stu-id="5fe3d-107">Microsoft.AspNetCore.Components</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components)
* [<span data-ttu-id="5fe3d-108">Microsoft.AspNetCore.Components.Authorization</span><span class="sxs-lookup"><span data-stu-id="5fe3d-108">Microsoft.AspNetCore.Components.Authorization</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Authorization)
* [<span data-ttu-id="5fe3d-109">Microsoft.AspNetCore.Components.Forms</span><span class="sxs-lookup"><span data-stu-id="5fe3d-109">Microsoft.AspNetCore.Components.Forms</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Forms)
* [<span data-ttu-id="5fe3d-110">Microsoft.AspNetCore.Components.Web</span><span class="sxs-lookup"><span data-stu-id="5fe3d-110">Microsoft.AspNetCore.Components.Web</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.Web)
* [<span data-ttu-id="5fe3d-111">Microsoft.AspNetCore.Components.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="5fe3d-111">Microsoft.AspNetCore.Components.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly)
* [<span data-ttu-id="5fe3d-112">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span><span class="sxs-lookup"><span data-stu-id="5fe3d-112">Microsoft.AspNetCore.Components.WebAssembly.Authentication</span></span>](https://www.nuget.org/packages/Microsoft.AspNetCore.Components.WebAssembly.Authentication)
* [<span data-ttu-id="5fe3d-113">Microsoft.JSInterop</span><span class="sxs-lookup"><span data-stu-id="5fe3d-113">Microsoft.JSInterop</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop)
* [<span data-ttu-id="5fe3d-114">Microsoft.JSInterop.WebAssembly</span><span class="sxs-lookup"><span data-stu-id="5fe3d-114">Microsoft.JSInterop.WebAssembly</span></span>](https://www.nuget.org/packages/Microsoft.JSInterop.WebAssembly)
* [<span data-ttu-id="5fe3d-115">Microsoft.Authentication.WebAssembly.Msal</span><span class="sxs-lookup"><span data-stu-id="5fe3d-115">Microsoft.Authentication.WebAssembly.Msal</span></span>](https://www.nuget.org/packages/Microsoft.Authentication.WebAssembly.Msal)

<span data-ttu-id="5fe3d-116">Para obtener información, vea la incidencia de GitHub [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span><span class="sxs-lookup"><span data-stu-id="5fe3d-116">For discussion, see GitHub issue [dotnet/aspnetcore#23424](https://github.com/dotnet/aspnetcore/issues/23424).</span></span>

## <a name="version-introduced"></a><span data-ttu-id="5fe3d-117">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5fe3d-117">Version introduced</span></span>

<span data-ttu-id="5fe3d-118">5.0 (versión preliminar 7)</span><span class="sxs-lookup"><span data-stu-id="5fe3d-118">5.0 Preview 7</span></span>

## <a name="old-behavior"></a><span data-ttu-id="5fe3d-119">Comportamiento anterior</span><span class="sxs-lookup"><span data-stu-id="5fe3d-119">Old behavior</span></span>

<span data-ttu-id="5fe3d-120">En Blazor 3.1 y 3.2, los paquetes tienen como destino .NET Standard 2.1 y .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="5fe3d-120">In Blazor 3.1 and 3.2, packages target .NET Standard 2.1 and .NET Core 3.1.</span></span>

## <a name="new-behavior"></a><span data-ttu-id="5fe3d-121">Comportamiento nuevo</span><span class="sxs-lookup"><span data-stu-id="5fe3d-121">New behavior</span></span>

<span data-ttu-id="5fe3d-122">En ASP.NET Core 5.0, los paquetes tienen como destino .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="5fe3d-122">In ASP.NET Core 5.0, packages target .NET 5.0.</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="5fe3d-123">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="5fe3d-123">Reason for change</span></span>

<span data-ttu-id="5fe3d-124">El cambio se ha realizado para una mejor alineación con los requisitos de plataforma de destino de .NET.</span><span class="sxs-lookup"><span data-stu-id="5fe3d-124">The change was made to better align with .NET target framework requirements.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="5fe3d-125">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="5fe3d-125">Recommended action</span></span>

<span data-ttu-id="5fe3d-126">Los proyectos WebAssembly de Blazor 3.2 deben tener como destino .NET 5.0 como parte de la actualización de las referencias de paquete a 5.x.x.</span><span class="sxs-lookup"><span data-stu-id="5fe3d-126">Blazor 3.2 WebAssembly projects should target .NET 5.0 as part of updating their package references to 5.x.x.</span></span> <span data-ttu-id="5fe3d-127">Las bibliotecas que hacen referencia a uno de estos paquetes pueden tener como destino .NET 5.0 o varios destinos, en función de sus requisitos.</span><span class="sxs-lookup"><span data-stu-id="5fe3d-127">Libraries that reference one of these packages can either target .NET 5.0 or multi-target depending on their requirements.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="5fe3d-128">API afectadas</span><span class="sxs-lookup"><span data-stu-id="5fe3d-128">Affected APIs</span></span>

<span data-ttu-id="5fe3d-129">None</span><span class="sxs-lookup"><span data-stu-id="5fe3d-129">None</span></span>

<!--

### Category

ASP.NET Core

### Affected APIs

Not detectable via API analysis

-->
