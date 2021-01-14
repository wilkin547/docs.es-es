---
title: 'Cambio importante: Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF'
description: Obtenga información sobre el cambio importante en .NET 5.0 donde las aplicaciones Windows Forms y Windows Presentation Framework ahora usan el SDK de .NET en lugar del SDK para WinForms y WPF de .NET Core.
ms.date: 09/18/2020
ms.openlocfilehash: 5eafed03fbf034f6a6457217a8527a877214e239
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633824"
---
# <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="f7a1c-103">Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF</span><span class="sxs-lookup"><span data-stu-id="f7a1c-103">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="f7a1c-104">Las aplicaciones de Windows Forms y Windows Presentation Framework (WPF) ahora usan el SDK de .NET (`Microsoft.NET.Sdk`) en lugar del SDK para WinForms y WPF de .NET Core (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="f7a1c-104">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

## <a name="change-description"></a><span data-ttu-id="f7a1c-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f7a1c-105">Change description</span></span>

<span data-ttu-id="f7a1c-106">En versiones anteriores de .NET Core, las aplicaciones de WinForms y WPF usaban un [SDK de proyecto](../../../project-sdk/overview.md) independiente (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="f7a1c-106">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="f7a1c-107">A partir de .NET 5.0, el SDK de WinForms y WPF se ha unificado con el SDK de .NET (`Microsoft.NET.Sdk`).</span><span class="sxs-lookup"><span data-stu-id="f7a1c-107">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="f7a1c-108">Además, los nuevos [monikers de la plataforma de destino (TFM)](../../../../standard/frameworks.md) reemplazan a `netcoreapp` y `netstandard` en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-108">In addition, new [target framework monikers (TFM)](../../../../standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="f7a1c-109">En el ejemplo siguiente se muestran los cambios que se deben realizar en un archivo de proyecto de WPF al redestinarlo a .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-109">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="f7a1c-110">En versiones anteriores de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="f7a1c-110">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="f7a1c-111">En .NET 5.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="f7a1c-111">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

## <a name="version-introduced"></a><span data-ttu-id="f7a1c-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f7a1c-112">Version introduced</span></span>

<span data-ttu-id="f7a1c-113">SDK 5.0.100 de .NET</span><span class="sxs-lookup"><span data-stu-id="f7a1c-113">.NET SDK 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f7a1c-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f7a1c-114">Recommended action</span></span>

<span data-ttu-id="f7a1c-115">En el archivo del proyecto de WPF o Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="f7a1c-115">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="f7a1c-116">Actualice el atributo `Sdk` a `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-116">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="f7a1c-117">Actualice la propiedad `TargetFramework` a `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-117">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="f7a1c-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f7a1c-118">Affected APIs</span></span>

<span data-ttu-id="f7a1c-119">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="f7a1c-119">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
