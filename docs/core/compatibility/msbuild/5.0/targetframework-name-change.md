---
title: 'Cambio importante: Cambio de TargetFramework de netcoreapp a net'
description: Obtenga información sobre el cambio importante en .NET 5 por el que el valor de la propiedad TargetFramework de MSBuild ha cambiado de netcoreapp3.1 a net5.0.
ms.date: 10/17/2020
ms.openlocfilehash: 88bfe7602c83f61b56f11c4e0336702571369e3c
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256496"
---
# <a name="targetframework-change-from-netcoreapp-to-net"></a><span data-ttu-id="4e26a-103">Cambio de TargetFramework de netcoreapp a net</span><span class="sxs-lookup"><span data-stu-id="4e26a-103">TargetFramework change from netcoreapp to net</span></span>

<span data-ttu-id="4e26a-104">El valor de la propiedad `TargetFramework` de MSBuild ha cambiado de `netcoreapp3.1` a `net5.0`.</span><span class="sxs-lookup"><span data-stu-id="4e26a-104">The value for the MSBuild `TargetFramework` property changed from `netcoreapp3.1` to `net5.0`.</span></span> <span data-ttu-id="4e26a-105">Esto puede interrumpir el código que se basa en el análisis del valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="4e26a-105">This can break code that relies on parsing the value of `TargetFramework`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="4e26a-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="4e26a-106">Version introduced</span></span>

<span data-ttu-id="4e26a-107">5.0</span><span class="sxs-lookup"><span data-stu-id="4e26a-107">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="4e26a-108">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="4e26a-108">Change description</span></span>

<span data-ttu-id="4e26a-109">En .NET Core 1.0-3.1, el valor de la propiedad `TargetFramework` de MSBuild comienza con `netcoreapp`, por ejemplo, `netcoreapp3.1` para las aplicaciones destinadas a .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="4e26a-109">In .NET Core 1.0 - 3.1, the value for the MSBuild `TargetFramework` property starts with `netcoreapp`, for example, `netcoreapp3.1` for apps that target .NET Core 3.1.</span></span> <span data-ttu-id="4e26a-110">A partir de .NET 5, este valor se ha simplificado para que solo empiece por `net`, por ejemplo, `net5.0` para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="4e26a-110">Starting in .NET 5, this value is simplified to just start with `net`, for example, `net5.0` for .NET 5.0.</span></span>

<span data-ttu-id="4e26a-111">Para obtener más información, vea [El futuro de .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) y [Nombres de plataforma de destino en .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span><span class="sxs-lookup"><span data-stu-id="4e26a-111">For more information, see [The future of .NET Standard](https://devblogs.microsoft.com/dotnet/the-future-of-net-standard/) and [Target framework names in .NET 5](https://github.com/dotnet/designs/blob/main/accepted/2020/net5/net5.md).</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="4e26a-112">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="4e26a-112">Reason for change</span></span>

- <span data-ttu-id="4e26a-113">Simplifica el valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="4e26a-113">Simplifies the `TargetFramework` value.</span></span>
- <span data-ttu-id="4e26a-114">Permite a los proyectos incluir un objeto `TargetPlatform` en la propiedad `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="4e26a-114">Enables projects to include a `TargetPlatform` in the `TargetFramework` property.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="4e26a-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="4e26a-115">Recommended action</span></span>

<span data-ttu-id="4e26a-116">Si tiene lógica que analiza el valor de `TargetFramework`, tendrá que actualizarla.</span><span class="sxs-lookup"><span data-stu-id="4e26a-116">If you have logic that parses the value of `TargetFramework`, you'll need to update it.</span></span> <span data-ttu-id="4e26a-117">Por ejemplo, la siguiente condición de MSBuild se basa en el valor de `TargetFramework`.</span><span class="sxs-lookup"><span data-stu-id="4e26a-117">For example, the following MSBuild condition relies on the value of `TargetFramework`.</span></span>

```xml
<PropertyGroup Condition="$(TargetFramework.StartsWith('netcoreapp'))">
```

<span data-ttu-id="4e26a-118">Para este requisito, puede actualizar el código a fin de comparar el identificador de la plataforma de destino.</span><span class="sxs-lookup"><span data-stu-id="4e26a-118">For this requirement, you can update the code to compare the target framework identifier instead.</span></span>

```xml
<PropertyGroup Condition="'$([MSBuild]::GetTargetFrameworkIdentifier('$(TargetFramework)'))' == '.NETCoreApp'">
```

## <a name="affected-apis"></a><span data-ttu-id="4e26a-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="4e26a-119">Affected APIs</span></span>

<span data-ttu-id="4e26a-120">N/D</span><span class="sxs-lookup"><span data-stu-id="4e26a-120">N/A</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

MSBuild

-->
