---
title: 'Cambio importante: .NET deja de tener compatibilidad integrada con WinRT'
description: Obtenga información sobre el cambio importante de interoperabilidad en .NET 5 donde se ha quitado de .NET la compatibilidad integrada con WinRT.
ms.date: 10/13/2020
ms.openlocfilehash: 986b810b74c7e7d7514ec2b734bfab45e29b87fa
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256691"
---
# <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="d734d-103">.NET deja de tener compatibilidad integrada con WinRT</span><span class="sxs-lookup"><span data-stu-id="d734d-103">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="d734d-104">Se ha quitado la compatibilidad integrada para el consumo de las API [Windows en tiempo de ejecución (WinRT)](/uwp/winrt-cref/winrt-type-system) en .NET.</span><span class="sxs-lookup"><span data-stu-id="d734d-104">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d734d-105">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d734d-105">Version introduced</span></span>

<span data-ttu-id="d734d-106">5.0</span><span class="sxs-lookup"><span data-stu-id="d734d-106">5.0</span></span>

## <a name="change-description"></a><span data-ttu-id="d734d-107">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d734d-107">Change description</span></span>

<span data-ttu-id="d734d-108">Anteriormente, CoreCLR podía consumir [archivos de metadatos de Windows (WinMD)](/uwp/winrt-cref/winmd-files) con el fin de activar y consumir tipos de WinRT.</span><span class="sxs-lookup"><span data-stu-id="d734d-108">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="d734d-109">A partir de la versión .NET 5, CoreCLR ya no puede consumir archivos WinMD directamente.</span><span class="sxs-lookup"><span data-stu-id="d734d-109">Starting in .NET 5, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="d734d-110">Si se intenta hacer referencia a un ensamblado no admitido, se obtendrá <xref:System.IO.FileNotFoundException>,</span><span class="sxs-lookup"><span data-stu-id="d734d-110">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="d734d-111">mientras que, si se activa una clase WinRT, se obtendrá <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="d734d-111">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="d734d-112">Este cambio importante se ha realizado por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="d734d-112">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="d734d-113">Para que WinRT se pueda desarrollar y mejorar por separado del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="d734d-113">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="d734d-114">Para favorecer la simetría con sistemas de interoperabilidad proporcionados para otros sistemas operativos, como iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="d734d-114">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="d734d-115">Para aprovechar las ventajas de otras características de .NET, como las características de C#, la vinculación de lenguaje intermedio (IL) y la compilación de antemano (AOT).</span><span class="sxs-lookup"><span data-stu-id="d734d-115">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="d734d-116">Para simplificar el código base del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="d734d-116">To simplify the .NET runtime codebase.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d734d-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d734d-117">Recommended action</span></span>

- <span data-ttu-id="d734d-118">Quite las referencias al [paquete Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span><span class="sxs-lookup"><span data-stu-id="d734d-118">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts).</span></span>  <span data-ttu-id="d734d-119">En su lugar, especifique la versión de las API de Windows a las que quiera acceder a través de la propiedad `TargetFramework` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d734d-119">Instead, specify the version of the Windows APIs that you want to access via the `TargetFramework` property of the project.</span></span>  <span data-ttu-id="d734d-120">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="d734d-120">For example:</span></span>

  ```xml
  <TargetFramework>net5.0-windows10.0.19041</TargetFramework>
  ```

- <span data-ttu-id="d734d-121">Use la cadena de herramientas de [C#/WinRT](/windows/uwp/csharp-winrt/) para generar o personalizar los tipos y las API de WinRT en .NET 5 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d734d-121">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types for .NET 5 and later versions.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d734d-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d734d-122">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

### Category

Interop

-->
