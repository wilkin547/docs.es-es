---
title: 'Cambio importante: Reconocimiento de URI de rutas UNC en UNIX'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET donde ahora la clase Uri reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en Unix.
ms.date: 11/01/2020
ms.openlocfilehash: 65baaad5e1be7a8f61e3e62c976fd7e28f48730f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257029"
---
# <a name="uri-recognition-of-unc-paths-on-unix"></a><span data-ttu-id="43e3e-103">Reconocimiento de URI de rutas UNC en UNIX</span><span class="sxs-lookup"><span data-stu-id="43e3e-103">Uri recognition of UNC paths on Unix</span></span>

<span data-ttu-id="43e3e-104">La clase <xref:System.Uri> ahora reconoce cadenas que comienzan con dos barras diagonales (`//`) como rutas de acceso UNC (Convención de nomenclatura universal) en sistemas operativos UNIX.</span><span class="sxs-lookup"><span data-stu-id="43e3e-104">The <xref:System.Uri> class now recognizes strings that start with two forward slashes (`//`) as universal naming convention (UNC) paths on Unix operating systems.</span></span> <span data-ttu-id="43e3e-105">Este cambio hace que el comportamiento de estas cadenas sea coherente en todas las plataformas.</span><span class="sxs-lookup"><span data-stu-id="43e3e-105">This change makes the behavior for such strings consistent across all platforms.</span></span>

## <a name="change-description"></a><span data-ttu-id="43e3e-106">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="43e3e-106">Change description</span></span>

<span data-ttu-id="43e3e-107">En versiones anteriores de .NET, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales, por ejemplo `//contoso`, como rutas de acceso de archivo absolutas en sistemas operativos Unix.</span><span class="sxs-lookup"><span data-stu-id="43e3e-107">In previous versions of .NET, the <xref:System.Uri> class recognizes strings that start with two forward slashes, for example, `//contoso`, as absolute file paths on Unix operating systems.</span></span> <span data-ttu-id="43e3e-108">Pero en Windows, estas cadenas se reconocen como rutas de acceso UNC.</span><span class="sxs-lookup"><span data-stu-id="43e3e-108">However, on Windows, such strings are recognized as UNC paths.</span></span>

<span data-ttu-id="43e3e-109">A partir de .NET 5, la clase <xref:System.Uri> reconoce cadenas que comienzan con dos barras diagonales como rutas de acceso UNC en todas las plataformas, incluido Unix.</span><span class="sxs-lookup"><span data-stu-id="43e3e-109">Starting in .NET 5,  the <xref:System.Uri> class recognizes strings that start with two forward slashes as UNC paths on all platforms, including Unix.</span></span> <span data-ttu-id="43e3e-110">Además, las propiedades se comportan de acuerdo con la semántica de UNC:</span><span class="sxs-lookup"><span data-stu-id="43e3e-110">In addition, properties behave according to UNC semantics:</span></span>

- <span data-ttu-id="43e3e-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> devuelve `true`.</span><span class="sxs-lookup"><span data-stu-id="43e3e-111"><xref:System.Uri.IsUnc?displayProperty=nameWithType> returns `true`.</span></span>
- <span data-ttu-id="43e3e-112">Las barras diagonales inversas de la ruta de acceso se reemplazan por barras diagonales.</span><span class="sxs-lookup"><span data-stu-id="43e3e-112">Backslashes in the path are replaced with forward slashes.</span></span> <span data-ttu-id="43e3e-113">Por ejemplo, `//first\second` se convierte en `//first/second`.</span><span class="sxs-lookup"><span data-stu-id="43e3e-113">For example, `//first\second` becomes `//first/second`.</span></span>
- <span data-ttu-id="43e3e-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> no codifica los caracteres.</span><span class="sxs-lookup"><span data-stu-id="43e3e-114"><xref:System.Uri.LocalPath?displayProperty=nameWithType> doesn't percent-encode characters.</span></span> <span data-ttu-id="43e3e-115">Por ejemplo, `//first/\uFFF0` *no* se convierte en `//first/%EF%BF%B0`.</span><span class="sxs-lookup"><span data-stu-id="43e3e-115">For example, `//first/\uFFF0` is *not* converted to `//first/%EF%BF%B0`.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="43e3e-116">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="43e3e-116">Version introduced</span></span>

<span data-ttu-id="43e3e-117">5.0</span><span class="sxs-lookup"><span data-stu-id="43e3e-117">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="43e3e-118">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="43e3e-118">Recommended action</span></span>

<span data-ttu-id="43e3e-119">No se requiere ninguna acción por parte del desarrollador.</span><span class="sxs-lookup"><span data-stu-id="43e3e-119">No action is required on the part of the developer.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="43e3e-120">API afectadas</span><span class="sxs-lookup"><span data-stu-id="43e3e-120">Affected APIs</span></span>

- <xref:System.Uri?displayProperty=fullName>

<!--

#### Category

Core .NET libraries

### Affected APIs

- `T:System.Uri`

-->
