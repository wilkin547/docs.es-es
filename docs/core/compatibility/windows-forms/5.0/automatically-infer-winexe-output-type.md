---
title: 'Cambio importante: OutputType establecido en WinExe para aplicaciones de WPF y WinForms'
description: Obtenga información sobre el cambio importante en el SDK 5.0.100 de .NET, donde OutputType se establece automáticamente en WinExe para las aplicaciones Windows Forms.
ms.date: 09/18/2020
ms.openlocfilehash: 0b56db57d5242f2fb001c4de339a7f696c088dfc
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633862"
---
# <a name="outputtype-set-to-winexe-for-wpf-and-winforms-apps"></a><span data-ttu-id="f7874-103">OutputType establecido en WinExe para aplicaciones de WPF y WinForms</span><span class="sxs-lookup"><span data-stu-id="f7874-103">OutputType set to WinExe for WPF and WinForms apps</span></span>

<span data-ttu-id="f7874-104">`OutputType` se establece de forma automática en `WinExe` para aplicaciones de Windows Presentation Foundation (WPF) y Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7874-104">`OutputType` is automatically set to `WinExe` for Windows Presentation Foundation (WPF) and Windows Forms apps.</span></span> <span data-ttu-id="f7874-105">Cuando `OutputType` se establece en `WinExe`, no se abre una ventana de la consola al ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f7874-105">When `OutputType` is set to `WinExe`, a console window doesn't open when the app is executed.</span></span>

## <a name="change-description"></a><span data-ttu-id="f7874-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="f7874-106">Change description</span></span>

<span data-ttu-id="f7874-107">En versiones anteriores del SDK de .NET, se usa el valor especificado para `OutputType` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7874-107">In previous versions of the .NET SDK, the value that's specified for `OutputType` in the project file is used.</span></span> <span data-ttu-id="f7874-108">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7874-108">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="f7874-109">A partir de la versión 5.0.100 del SDK de .NET, `OutputType` se establece automáticamente en `WinExe` para WPF y las aplicaciones de Windows Forms que tienen como destino cualquier versión de Framework, incluido .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f7874-109">Starting in the 5.0.100 version of the .NET SDK, `OutputType` is automatically set to `WinExe` for WPF and Windows Forms apps that target any framework version, including .NET Framework.</span></span> <span data-ttu-id="f7874-110">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f7874-110">For example:</span></span>

```xml
<PropertyGroup>
  <OutputType>WinExe</OutputType>
</PropertyGroup>
```

## <a name="reason-for-change"></a><span data-ttu-id="f7874-111">Motivo del cambio</span><span class="sxs-lookup"><span data-stu-id="f7874-111">Reason for change</span></span>

<span data-ttu-id="f7874-112">Se supone que la mayoría de los usuarios no quieren que se abra una ventana de consola cuando se ejecuta una aplicación de WPF o Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f7874-112">It's assumed that most users don't want a console window to open when a WPF or Windows Forms app is executed.</span></span> <span data-ttu-id="f7874-113">Además, [ahora que estos tipos de aplicación usan el SDK de .NET](sdk-and-target-framework-change.md) en lugar del SDK de Escritorio de Windows, se establecerá el valor predeterminado correcto.</span><span class="sxs-lookup"><span data-stu-id="f7874-113">In addition, [now that these application types use the .NET SDK](sdk-and-target-framework-change.md) instead of the Windows Desktop SDK, the correct default will be set.</span></span> <span data-ttu-id="f7874-114">Incluso si se agrega compatibilidad para seleccionar iOS y Android como destino, será más fácil seleccionar varias plataformas de destino si todas usan el mismo tipo de salida.</span><span class="sxs-lookup"><span data-stu-id="f7874-114">Further, when support for targeting iOS and Android is added, it will be easier to multi-target between multiple platforms if they all use the same output type.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="f7874-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="f7874-115">Version introduced</span></span>

<span data-ttu-id="f7874-116">.NET 5.0.100</span><span class="sxs-lookup"><span data-stu-id="f7874-116">.NET 5.0.100</span></span>

## <a name="recommended-action"></a><span data-ttu-id="f7874-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="f7874-117">Recommended action</span></span>

<span data-ttu-id="f7874-118">No es necesario que realice ninguna acción.</span><span class="sxs-lookup"><span data-stu-id="f7874-118">No action is required in your part.</span></span> <span data-ttu-id="f7874-119">Pero si quiere revertir al comportamiento anterior, establezca la propiedad `DisableWinExeOutputInference` en `true` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="f7874-119">However, if you want to revert to the old behavior, set the `DisableWinExeOutputInference` property to `true` in your project file.</span></span>

```xml
<DisableWinExeOutputInference>true</DisableWinExeOutputInference>
```

## <a name="affected-apis"></a><span data-ttu-id="f7874-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f7874-120">Affected APIs</span></span>

<span data-ttu-id="f7874-121">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="f7874-121">Not detectable via API analysis.</span></span>

<!--

### Affected APIs

Not detectable via API analysis.

### Category

- Windows Forms
- Windows Presentation Framework (WPF)

-->
