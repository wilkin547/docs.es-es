---
ms.openlocfilehash: faf9459ab9002e6149560e2a3452265fa246bf6b
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720216"
---
### <a name="uri-paths-with-non-ascii-characters-parse-correctly-on-unix"></a><span data-ttu-id="7c95b-101">Rutas de acceso de URI con caracteres que no son ASCII se analizan correctamente en UNIX</span><span class="sxs-lookup"><span data-stu-id="7c95b-101">URI paths with non-ASCII characters parse correctly on Unix</span></span>

<span data-ttu-id="7c95b-102">Se ha corregido un error de la clase <xref:System.Uri?displayProperty=fullName>, de modo que las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII ahora se analizan correctamente en plataformas UNIX.</span><span class="sxs-lookup"><span data-stu-id="7c95b-102">A bug was fixed in the <xref:System.Uri?displayProperty=fullName> class such that absolute URI paths that contain non-ASCII characters now parse correctly on Unix platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="7c95b-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="7c95b-103">Change description</span></span>

<span data-ttu-id="7c95b-104">En versiones anteriores de .NET, las rutas de acceso de URI absolutas que contienen caracteres que no son ASCII se analizan incorrectamente en plataformas UNIX y los segmentos de la ruta de acceso están duplicados.</span><span class="sxs-lookup"><span data-stu-id="7c95b-104">In previous versions of .NET, absolute URI paths that contain non-ASCII characters are parsed incorrectly on Unix platforms, and segments of the path are duplicated.</span></span> <span data-ttu-id="7c95b-105">(Las rutas de acceso absolutas son las que empiezan por "/"). El problema de análisis se ha solucionado para .NET 5.0.</span><span class="sxs-lookup"><span data-stu-id="7c95b-105">(Absolute paths are those that start with "/".) The parsing issue has been fixed for .NET 5.0.</span></span> <span data-ttu-id="7c95b-106">Si pasa de una versión anterior de .NET a .NET 5.0 u otra posterior, obtendrá valores diferentes generados por <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType> y otros miembros de <xref:System.Uri>.</span><span class="sxs-lookup"><span data-stu-id="7c95b-106">If you move from a previous version of .NET to .NET 5.0 or later, you'll get different values produced by <xref:System.Uri.AbsoluteUri?displayProperty=nameWithType>, <xref:System.Uri.ToString?displayProperty=nameWithType>, and other <xref:System.Uri> members.</span></span>

<span data-ttu-id="7c95b-107">Tenga en cuenta el resultado de este código cuando se ejecute en UNIX.</span><span class="sxs-lookup"><span data-stu-id="7c95b-107">Consider the output of the following code when run on Unix.</span></span>

```csharp
var myUri = new Uri("/üri");

Console.WriteLine($"AbsoluteUri: {myUri.AbsoluteUri}");
Console.WriteLine($"ToString: {myUri.ToString()}");
```

<span data-ttu-id="7c95b-108">Resultado en la versión anterior de .NET:</span><span class="sxs-lookup"><span data-stu-id="7c95b-108">Output on previous .NET version:</span></span>

```text
AbsoluteUri: /%C3%BCri/%C3%BCri
ToString: /üri/üri
```

<span data-ttu-id="7c95b-109">Resultado en .NET 5.0 u otra versión posterior:</span><span class="sxs-lookup"><span data-stu-id="7c95b-109">Output on .NET 5.0 or later version:</span></span>

```text
AbsoluteUri: /%C3%BCri
ToString: /üri
```

#### <a name="version-introduced"></a><span data-ttu-id="7c95b-110">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7c95b-110">Version introduced</span></span>

<span data-ttu-id="7c95b-111">5.0</span><span class="sxs-lookup"><span data-stu-id="7c95b-111">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="7c95b-112">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="7c95b-112">Recommended action</span></span>

<span data-ttu-id="7c95b-113">Si tiene código que espera segmentos de ruta de acceso duplicados y los tiene en cuenta, puede quitar ese código.</span><span class="sxs-lookup"><span data-stu-id="7c95b-113">If you have code that expects and accounts for the duplicated path segments, you can remove that code.</span></span>

#### <a name="category"></a><span data-ttu-id="7c95b-114">Categoría</span><span class="sxs-lookup"><span data-stu-id="7c95b-114">Category</span></span>

<span data-ttu-id="7c95b-115">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="7c95b-115">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="7c95b-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="7c95b-116">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
