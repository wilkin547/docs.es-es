---
ms.openlocfilehash: 4091bdcf7d9ed8872aed5faa6e6d3ed143903787
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77449416"
---
### <a name="unauthorizedaccessexception-thrown-by-filesysteminfoattributes"></a><span data-ttu-id="132e3-101">UnauthorizedAccessException producida por FileSystemInfo.Attributes</span><span class="sxs-lookup"><span data-stu-id="132e3-101">UnauthorizedAccessException thrown by FileSystemInfo.Attributes</span></span>

<span data-ttu-id="132e3-102">En .NET Core, se produce una <xref:System.UnauthorizedAccessException> si el autor de la llamada intenta establecer un valor de atributo de archivo pero no tiene permiso de escritura.</span><span class="sxs-lookup"><span data-stu-id="132e3-102">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown when the caller attempts to set a file attribute value but doesn't have write permission.</span></span>

#### <a name="change-description"></a><span data-ttu-id="132e3-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="132e3-103">Change description</span></span>

<span data-ttu-id="132e3-104">En .NET Framework, se produce una <xref:System.ArgumentException> si el autor de la llamada intenta establecer un valor de atributo de archivo en <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> pero no tiene permiso de escritura.</span><span class="sxs-lookup"><span data-stu-id="132e3-104">In .NET Framework, an <xref:System.ArgumentException> is thrown when the caller attempts to set a file attribute value in <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType> but doesn't have write permission.</span></span> <span data-ttu-id="132e3-105">En .NET Core, se produce una <xref:System.UnauthorizedAccessException> en su lugar.</span><span class="sxs-lookup"><span data-stu-id="132e3-105">In .NET Core, an <xref:System.UnauthorizedAccessException> is thrown instead.</span></span> <span data-ttu-id="132e3-106">(En .NET Core, se sigue produciendo una <xref:System.ArgumentException> si el autor de la llamada intenta establecer un atributo de archivo no válido).</span><span class="sxs-lookup"><span data-stu-id="132e3-106">(In .NET Core, an <xref:System.ArgumentException> is still thrown if the caller attempts to set an invalid file attribute.)</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="132e3-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="132e3-107">Version introduced</span></span>

<span data-ttu-id="132e3-108">1.0</span><span class="sxs-lookup"><span data-stu-id="132e3-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="132e3-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="132e3-109">Recommended action</span></span>

<span data-ttu-id="132e3-110">Modifique las instrucciones `catch` para capturar una <xref:System.UnauthorizedAccessException> en lugar de una <xref:System.ArgumentException>, o además de esta, según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="132e3-110">Modify any `catch` statements to catch an <xref:System.UnauthorizedAccessException> instead of, or in addition to, an <xref:System.ArgumentException>, as necessary.</span></span>

#### <a name="category"></a><span data-ttu-id="132e3-111">Categoría</span><span class="sxs-lookup"><span data-stu-id="132e3-111">Category</span></span>

<span data-ttu-id="132e3-112">CoreFX</span><span class="sxs-lookup"><span data-stu-id="132e3-112">CoreFx</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="132e3-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="132e3-113">Affected APIs</span></span>

- <xref:System.IO.FileSystemInfo.Attributes?displayProperty=nameWithType>

<!--

#### Affected APIs

- `P:System.IO.FileSystemInfo.Attributes`

-->
