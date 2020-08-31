---
ms.openlocfilehash: 0246f325a6274082b7fb0d5590cec7c80687ae85
ms.sourcegitcommit: ef86c24c418439b8bb5e3e7d64bbdbe5e11c3e9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2020
ms.locfileid: "88720214"
---
### <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="3efe1-101">Reconocimiento de URI de rutas UNC en UNIX</span><span class="sxs-lookup"><span data-stu-id="3efe1-101">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="3efe1-102">La clase <xref:System.Uri> ahora reconoce cadenas que comienzan con dos barras diagonales (`//`) como rutas de acceso UNC (Convención de nomenclatura universal) en sistemas operativos UNIX.</span><span class="sxs-lookup"><span data-stu-id="3efe1-102">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="3efe1-103">Este cambio hace que el comportamiento de estas cadenas sea coherente en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="3efe1-103">This change makes the behavior for such strings consistent across all platforms.</span></span>

#### <a name="change-description"></a><span data-ttu-id="3efe1-104">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="3efe1-104">Change description</span></span>

<span data-ttu-id="3efe1-105">En versiones anteriores de .NET, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales, por ejemplo `//contoso`, como rutas de acceso de archivo absolutas en sistemas operativos UNIX.</span><span class="sxs-lookup"><span data-stu-id="3efe1-105">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="3efe1-106">Pero en Windows, estas cadenas se reconocen como rutas de acceso UNC.</span><span class="sxs-lookup"><span data-stu-id="3efe1-106">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="3efe1-107">A partir de .NET 5.0, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en todas las plataformas, incluido UNIX.</span><span class="sxs-lookup"><span data-stu-id="3efe1-107">Starting in .NET 5.0,  the <xref:System.Uri> class recognizes strings that start with with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="3efe1-108">Además, las propiedades se comportan de acuerdo con la semántica de UNC:</span><span class="sxs-lookup"><span data-stu-id="3efe1-108">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="3efe1-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="3efe1-109"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="3efe1-110">Las barras diagonales inversas de la ruta de acceso se reemplazan por barras diagonales.</span><span class="sxs-lookup"><span data-stu-id="3efe1-110">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="3efe1-111">Por ejemplo, `//first\second` se convierte en `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="3efe1-111">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="3efe1-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> no codifica los caracteres.</span><span class="sxs-lookup"><span data-stu-id="3efe1-112"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="3efe1-113">Por ejemplo, `//first/\uFFF0` *no* se convierte en `//first/%EF%BF%B0`.</span><span class="sxs-lookup"><span data-stu-id="3efe1-113">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="3efe1-114">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="3efe1-114">Version introduced</span></span>

<span data-ttu-id="3efe1-115">5.0</span><span class="sxs-lookup"><span data-stu-id="3efe1-115">5.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="3efe1-116">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="3efe1-116">Recommended action</span></span>

<span data-ttu-id="3efe1-117">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="3efe1-117">No action is required on the part of the developer.</span></span>

#### <a name="category"></a><span data-ttu-id="3efe1-118">Categoría</span><span class="sxs-lookup"><span data-stu-id="3efe1-118">Category</span></span>

<span data-ttu-id="3efe1-119">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="3efe1-119">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="3efe1-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3efe1-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Uri`

-->
