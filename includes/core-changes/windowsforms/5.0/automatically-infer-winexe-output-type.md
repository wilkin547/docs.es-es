---
ms.openlocfilehash: 54bee14f6de409550357194e905b6ee5d8ef8f18
ms.sourcegitcommit: aa6d8a90a4f5d8fe0f6e967980b8c98433f05a44
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "90679009"
---
### <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="a9726-101">OutputType establecido en WinExe para aplicaciones de WPF y WinForms</span><span class="sxs-lookup"><span data-stu-id="a9726-101">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="a9726-102">`OutputType` se establece de forma automática en `WinExe` para aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a9726-102">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="a9726-103">Cuando `OutputType` se establece en `WinExe`, no se abre una ventana de la consola al ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a9726-103">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

#### <a name="change-description"></a><span data-ttu-id="a9726-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="a9726-104">Change description</span></span>

<span data-ttu-id="a9726-105">En versiones anteriores de .NET, se usa el valor especificado para `OutputType` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9726-105">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="a9726-106">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a9726-106">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="a9726-107">A partir de .NET 5.0, `OutputType` se establece de forma automática en `WinExe` para las aplicaciones de WPF y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a9726-107">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="a9726-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a9726-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

#### <a name="reason-for-change"></a><span data-ttu-id="a9726-109">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="a9726-109">Reason for change</span></span>

<span data-ttu-id="a9726-110">Se supone que la mayoría de los usuarios no quieren que se abra una ventana de consola cuando se ejecuta una aplicación de WPF o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a9726-110">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="a9726-111">Además, [ahora que estos tipos de aplicación usan el SDK de .NET](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) en lugar del SDK de Escritorio de Windows, se establecerá el valor predeterminado correcto.</span><span class="sxs-lookup"><span data-stu-id="a9726-111">In addition, [now that these application types use the .NET SDK](../../../../docs/core/compatibility/wpf.md#winforms-and-wpf-apps-use-microsoftnetsdk) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="a9726-112">Incluso si se agrega compatibilidad para seleccionar iOS y Android como destino, será más fácil seleccionar varias plataformas de destino si todas usan el mismo tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="a9726-112">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="a9726-113">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="a9726-113">Version introduced</span></span>

<span data-ttu-id="a9726-114">.NET 5.0 (versión preliminar 8)</span><span class="sxs-lookup"><span data-stu-id="a9726-114">.NET 5.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="a9726-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="a9726-115">Recommended action</span></span>

<span data-ttu-id="a9726-116">No es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="a9726-116">No action is required in your part.</span></span> <span data-ttu-id="a9726-117">Pero si quiere revertir al comportamiento anterior, establezca la propiedad `DisableWinExeOutputInference` en `true` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a9726-117">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

#### <a name="category"></a><span data-ttu-id="a9726-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="a9726-118">Category</span></span>

- <span data-ttu-id="a9726-119">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a9726-119">Windows Forms</span></span>
- <span data-ttu-id="a9726-120">Windows Presentation Framework (WPF)</span><span class="sxs-lookup"><span data-stu-id="a9726-120">Windows Presentation Framework (WPF)</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="a9726-121">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a9726-121">Affected APIs</span></span>

<span data-ttu-id="a9726-122">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="a9726-122">Not detectable via API analysis.</span></span>

<!-- 

#### Affected APIs

Not detectable via API analysis.

-->
