---
ms.openlocfilehash: 975e331ad3e7bd7e0e8f49b62795c6acc7031ca9
ms.sourcegitcommit: 1e8382d0ce8b5515864f8fbb178b9fd692a7503f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2020
ms.locfileid: "89656355"
---
### <a name="winforms-and-wpf-apps-use-microsoftnetsdk"></a><span data-ttu-id="1f695-101">Uso de Microsoft.NET.Sdk por parte de las aplicaciones de WinForms y WPF</span><span class="sxs-lookup"><span data-stu-id="1f695-101">WinForms and WPF apps use Microsoft.NET.Sdk</span></span>

<span data-ttu-id="1f695-102">Las aplicaciones de Windows Forms y Windows Presentation Framework (WPF) ahora usan el SDK de .NET (`Microsoft.NET.Sdk`) en lugar del SDK para WinForms y WPF de .NET Core (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="1f695-102">Windows Forms and Windows Presentation Framework (WPF) apps now use the .NET SDK (`Microsoft.NET.Sdk`) instead of the .NET Core WinForms and WPF SDK (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span>

#### <a name="change-description"></a><span data-ttu-id="1f695-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="1f695-103">Change description</span></span>

<span data-ttu-id="1f695-104">En versiones anteriores de .NET Core, las aplicaciones de WinForms y WPF usaban un [SDK de proyecto](../../../../docs/core/project-sdk/overview.md) independiente (`Microsoft.NET.Sdk.WindowsDesktop`).</span><span class="sxs-lookup"><span data-stu-id="1f695-104">In previous .NET Core versions, WinForms and WPF apps used a separate [project SDK](../../../../docs/core/project-sdk/overview.md) (`Microsoft.NET.Sdk.WindowsDesktop`).</span></span> <span data-ttu-id="1f695-105">A partir de .NET 5.0, el SDK de WinForms y WPF se ha unificado con el SDK de .NET (`Microsoft.NET.Sdk`).</span><span class="sxs-lookup"><span data-stu-id="1f695-105">Starting in .NET 5.0, the WinForms and WPF SDK has been unified with the .NET SDK (`Microsoft.NET.Sdk`).</span></span> <span data-ttu-id="1f695-106">Además, los nuevos [monikers de la plataforma de destino (TFM)](../../../../docs/standard/frameworks.md) reemplazan a `netcoreapp` y `netstandard` en .NET 5.</span><span class="sxs-lookup"><span data-stu-id="1f695-106">In addition, new [target framework monikers (TFM)](../../../../docs/standard/frameworks.md) replace `netcoreapp` and `netstandard` in .NET 5.</span></span> <span data-ttu-id="1f695-107">En el ejemplo siguiente se muestran los cambios que se deben realizar en un archivo de proyecto de WPF al redestinarlo a .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="1f695-107">The following example shows the changes you'd need to make for a WPF project file when retargeting to .NET 5.0 or later.</span></span>

<span data-ttu-id="1f695-108">En versiones anteriores de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="1f695-108">In previous .NET Core versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>netcoreapp3.1</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="1f695-109">En .NET 5.0 y versiones posteriores:</span><span class="sxs-lookup"><span data-stu-id="1f695-109">In .NET 5.0 and later versions:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>WinExe</OutputType>
    <TargetFramework>net5.0-windows</TargetFramework>
    <UseWPF>true</UseWPF>
  </PropertyGroup>

</Project>
```

#### <a name="version-introduced"></a><span data-ttu-id="1f695-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="1f695-110">Version introduced</span></span>

<span data-ttu-id="1f695-111">.NET 5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="1f695-111">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="1f695-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="1f695-112">Recommended action</span></span>

<span data-ttu-id="1f695-113">En el archivo del proyecto de WPF o Windows Forms:</span><span class="sxs-lookup"><span data-stu-id="1f695-113">In your WPF or Windows Forms project file:</span></span>

- <span data-ttu-id="1f695-114">Actualice el atributo `Sdk` a `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="1f695-114">Update the `Sdk` attribute  to `Microsoft.NET.Sdk`.</span></span>
- <span data-ttu-id="1f695-115">Actualice la propiedad `TargetFramework` a `net5.0-windows`.</span><span class="sxs-lookup"><span data-stu-id="1f695-115">Update the `TargetFramework` property to `net5.0-windows`.</span></span>

#### <a name="category"></a><span data-ttu-id="1f695-116">Categoría</span><span class="sxs-lookup"><span data-stu-id="1f695-116">Category</span></span>

- <span data-ttu-id="1f695-117">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1f695-117">Windows Forms</span></span>
- <span data-ttu-id="1f695-118">Windows Presentation Framework (WPF)</span><span class="sxs-lookup"><span data-stu-id="1f695-118">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="1f695-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1f695-119">Affected APIs</span></span>

<span data-ttu-id="1f695-120">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="1f695-120">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
