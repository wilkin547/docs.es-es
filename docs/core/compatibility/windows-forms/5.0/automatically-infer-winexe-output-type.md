---
title: 'Cambio importante: OutputType establecido en WinExe para aplicaciones de WPF y WinForms'
description: Obtenga información sobre el cambio importante en .NET 5.0, donde OutputType se establece automáticamente en WinExe para las aplicaciones Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 072c5b11c8304eb540e176ce9747930789f28505
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760266"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="33bc5-103">OutputType establecido en WinExe para aplicaciones de WPF y WinForms</span><span class="sxs-lookup"><span data-stu-id="33bc5-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="33bc5-104">`OutputType` se establece de forma automática en `WinExe` para aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="33bc5-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="33bc5-105">Cuando `OutputType` se establece en `WinExe`, no se abre una ventana de la consola al ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="33bc5-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="33bc5-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="33bc5-106">Change description</span></span>

<span data-ttu-id="33bc5-107">En versiones anteriores de .NET, se usa el valor especificado para `OutputType` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="33bc5-107">In previous versions of .NET, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="33bc5-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33bc5-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="33bc5-109">A partir de .NET 5.0, `OutputType` se establece de forma automática en `WinExe` para las aplicaciones de WPF y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="33bc5-109">Starting in .NET 5.0, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps.</span></span> <span data-ttu-id="33bc5-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="33bc5-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="33bc5-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="33bc5-111">Reason for change</span></span>

<span data-ttu-id="33bc5-112">Se supone que la mayoría de los usuarios no quieren que se abra una ventana de consola cuando se ejecuta una aplicación de WPF o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="33bc5-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="33bc5-113">Además, [ahora que estos tipos de aplicación usan el SDK de .NET](sdk-and-target-framework-change.md) en lugar del SDK de Escritorio de Windows, se establecerá el valor predeterminado correcto.</span><span class="sxs-lookup"><span data-stu-id="33bc5-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="33bc5-114">Incluso si se agrega compatibilidad para seleccionar iOS y Android como destino, será más fácil seleccionar varias plataformas de destino si todas usan el mismo tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="33bc5-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="33bc5-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="33bc5-115">Version introduced</span></span>

<span data-ttu-id="33bc5-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="33bc5-116">.NET 5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="33bc5-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="33bc5-117">Recommended action</span></span>

<span data-ttu-id="33bc5-118">No es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="33bc5-118">No action is required in your part.</span></span> <span data-ttu-id="33bc5-119">Pero si quiere revertir al comportamiento anterior, establezca la propiedad `DisableWinExeOutputInference` en `true` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="33bc5-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="33bc5-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="33bc5-120">Affected APIs</span></span>

<span data-ttu-id="33bc5-121">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="33bc5-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
