---
ms.openlocfilehash: d21b2e092d460fdfc367d0f490228ed44ad5c6cc
ms.sourcegitcommit: 63bb83322814f5e5e5c5b69939b14a3139a6ca7e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2020
ms.locfileid: "85365664"
---
### <a name="built-in-support-for-winrt-is-removed-from-net"></a><span data-ttu-id="d9b88-101">.NET deja de tener compatibilidad integrada con WinRT</span><span class="sxs-lookup"><span data-stu-id="d9b88-101">Built-in support for WinRT is removed from .NET</span></span>

<span data-ttu-id="d9b88-102">Se ha quitado la compatibilidad integrada para el consumo de las API [Windows en tiempo de ejecución (WinRT)](/uwp/winrt-cref/winrt-type-system) en .NET.</span><span class="sxs-lookup"><span data-stu-id="d9b88-102">Built-in support for consumption of [Windows runtime (WinRT)](/uwp/winrt-cref/winrt-type-system) APIs in .NET is removed.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="d9b88-103">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d9b88-103">Version introduced</span></span>

<span data-ttu-id="d9b88-104">5.0 (versión preliminar 6)</span><span class="sxs-lookup"><span data-stu-id="d9b88-104">5.0 Preview 6</span></span>

#### <a name="change-description"></a><span data-ttu-id="d9b88-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d9b88-105">Change description</span></span>

<span data-ttu-id="d9b88-106">Anteriormente, CoreCLR podía consumir [archivos de metadatos de Windows (WinMD)](/uwp/winrt-cref/winmd-files) con el fin de activar y consumir tipos de WinRT.</span><span class="sxs-lookup"><span data-stu-id="d9b88-106">Previously, CoreCLR could consume [Windows metadata (WinMD) files](/uwp/winrt-cref/winmd-files) to active and consume WinRT types.</span></span> <span data-ttu-id="d9b88-107">A partir de la versión .NET 5.0, CoreCLR ya no puede consumir archivos WinMD directamente.</span><span class="sxs-lookup"><span data-stu-id="d9b88-107">Starting in .NET 5.0, CoreCLR can no longer consume WinMD files directly.</span></span>

<span data-ttu-id="d9b88-108">Si se intenta hacer referencia a un ensamblado no admitido, se obtendrá <xref:System.IO.FileNotFoundException>,</span><span class="sxs-lookup"><span data-stu-id="d9b88-108">If you attempt to reference an unsupported assembly, you'll get a <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="d9b88-109">mientras que, si se activa una clase WinRT, se obtendrá <xref:System.PlatformNotSupportedException>.</span><span class="sxs-lookup"><span data-stu-id="d9b88-109">If you activate a WinRT class, you'll get a <xref:System.PlatformNotSupportedException>.</span></span>

<span data-ttu-id="d9b88-110">Este cambio importante se ha realizado por los siguientes motivos:</span><span class="sxs-lookup"><span data-stu-id="d9b88-110">This breaking change was made for the following reasons:</span></span>

- <span data-ttu-id="d9b88-111">Para que WinRT se pueda desarrollar y mejorar por separado del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="d9b88-111">So WinRT can be developed and improved separately from the .NET runtime.</span></span>
- <span data-ttu-id="d9b88-112">Para favorecer la simetría con sistemas de interoperabilidad proporcionados para otros sistemas operativos, como iOS y Android.</span><span class="sxs-lookup"><span data-stu-id="d9b88-112">For symmetry with interop systems provided for other operating systems, such as iOS and Android.</span></span>
- <span data-ttu-id="d9b88-113">Para aprovechar las ventajas de otras características de .NET, como las características de C#, la vinculación de lenguaje intermedio (IL) y la compilación de antemano (AOT).</span><span class="sxs-lookup"><span data-stu-id="d9b88-113">To take advantage of other .NET features, such as C# features, intermediate language (IL) linking, and ahead-of-time (AOT) compilation.</span></span>
- <span data-ttu-id="d9b88-114">Para simplificar el código base del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="d9b88-114">To simplify the .NET runtime codebase.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="d9b88-115">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d9b88-115">Recommended action</span></span>

- <span data-ttu-id="d9b88-116">Quite las referencias al [paquete Microsoft.Windows.SDK.Contracts](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) y reemplácelas por referencias al [paquete Microsoft.Windows.SDK.NET](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span><span class="sxs-lookup"><span data-stu-id="d9b88-116">Remove references to the [Microsoft.Windows.SDK.Contracts package](https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts) and replace them with references to the [Microsoft.Windows.SDK.NET package](https://www.nuget.org/packages/microsoft.windows.sdk.net).</span></span>

- <span data-ttu-id="d9b88-117">Use la cadena de herramientas de [C#/WinRT](/windows/uwp/csharp-winrt/) para generar o personalizar los tipos y las API de WinRT en .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="d9b88-117">Use the [C#/WinRT](/windows/uwp/csharp-winrt/) tool chain to generate or customize WinRT APIs and types in .NET 5.0 and later versions.</span></span>

#### <a name="category"></a><span data-ttu-id="d9b88-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="d9b88-118">Category</span></span>

<span data-ttu-id="d9b88-119">Interop</span><span class="sxs-lookup"><span data-stu-id="d9b88-119">Interop</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="d9b88-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d9b88-120">Affected APIs</span></span>

- <xref:System.IO.WindowsRuntimeStorageExtensions?displayProperty=fullName>
- <xref:System.IO.WindowsRuntimeStreamExtensions?displayProperty=fullName>
- <xref:System.Runtime.InteropServices.WindowsRuntime?displayProperty=fullName>
- <xref:System.WindowsRuntimeSystemExtensions?displayProperty=fullName>
- <xref:Windows.Foundation.Point?displayProperty=fullName>
- <xref:Windows.Foundation.Size?displayProperty=fullName>
- <xref:Windows.UI.Color?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.IO.WindowsRuntimeStorageExtensions`
- `T: System.IO.WindowsRuntimeStreamExtensions`
- `N:System.Runtime.InteropServices.WindowsRuntime`
- `T:System.WindowsRuntimeSystemExtensions`
- `T:Windows.Foundation.Point`
- `T:Windows.Foundation.Size`
- `T:Windows.UI.Color`

-->
