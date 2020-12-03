---
title: 'Cambio importante: Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de .NET donde las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII ahora se analizan correctamente en plataformas Unix.
ms.date: 11/01/2020
ms.openlocfilehash: 94de4e0eb94a11153d873871d4003422a4286a0c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760112"
---
# <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="e6932-103">Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX</span><span class="sxs-lookup"><span data-stu-id="e6932-103">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="e6932-104">Se ha corregido un error de la clase <xref:System.Uri?displayProperty=fullName>, de modo que las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII ahora se analizan correctamente en plataformas UNIX.</span><span class="sxs-lookup"><span data-stu-id="e6932-104">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="e6932-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="e6932-105">Change description</span></span>

<span data-ttu-id="e6932-106">En versiones anteriores de .NET, las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII se analizan incorrectamente en plataformas UNIX y los segmentos de la ruta de acceso están duplicados.</span><span class="sxs-lookup"><span data-stu-id="e6932-106">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="e6932-107">(Las rutas de acceso absolutas son las que empiezan por "/"). El problema de análisis se ha solucionado para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="e6932-107">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="e6932-108">Si pasa de una versión anterior de .NET a .NET 5.0 u otra posterior, obtendrá valores diferentes generados por <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType> y otros miembros de <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="e6932-108">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="e6932-109">Tenga en cuenta el resultado de este código cuando se ejecute en UNIX.</span><span class="sxs-lookup"><span data-stu-id="e6932-109">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="e6932-110">Resultado en la versión anterior de .NET:</span><span class="sxs-lookup"><span data-stu-id="e6932-110">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="e6932-111">Resultado en .NET 5.0 u otra versión posterior:</span><span class="sxs-lookup"><span data-stu-id="e6932-111">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

## <a name="version-introduced"></a><span data-ttu-id="e6932-112">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="e6932-112">Version introduced</span></span>

<span data-ttu-id="e6932-113">5.0</span><span class="sxs-lookup"><span data-stu-id="e6932-113">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="e6932-114">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="e6932-114">Recommended action</span></span>

<span data-ttu-id="e6932-115">Si tiene código que espera segmentos de ruta de acceso duplicados y los tiene en cuenta, puede quitar ese código.</span><span class="sxs-lookup"><span data-stu-id="e6932-115">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="e6932-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e6932-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
