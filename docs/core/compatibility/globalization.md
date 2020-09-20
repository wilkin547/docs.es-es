---
title: Cambios importantes de la globalización
description: Enumera los cambios importantes de la globalización en .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 93990d89204df1b2d7498e1d748378fae05598c3
ms.sourcegitcommit: a69d548f90a03e105ee6701236c38390ecd9ccd1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "90065075"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="c2a19-103">Cambios importantes de la globalización</span><span class="sxs-lookup"><span data-stu-id="c2a19-103">Globalization breaking changes</span></span>

<span data-ttu-id="c2a19-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="c2a19-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c2a19-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="c2a19-105">Breaking change</span></span> | <span data-ttu-id="c2a19-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="c2a19-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c2a19-107">Categoría Unicode modificada para algunos caracteres del alfabeto latino 1</span><span class="sxs-lookup"><span data-stu-id="c2a19-107">Unicode category changed for some Latin-1 characters</span></span>](#unicode-category-changed-for-some-latin-1-characters) | <span data-ttu-id="c2a19-108">5.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-108">5.0</span></span> |
| [<span data-ttu-id="c2a19-109">Las API de globalización usan bibliotecas de ICU en Windows</span><span class="sxs-lookup"><span data-stu-id="c2a19-109">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="c2a19-110">5.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-110">5.0</span></span> |
| [<span data-ttu-id="c2a19-111">StringInfo y TextElementEnumerator ahora son compatibles con UAX29</span><span class="sxs-lookup"><span data-stu-id="c2a19-111">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="c2a19-112">5.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-112">5.0</span></span> |
| [<span data-ttu-id="c2a19-113">La configuración regional de "C" se asigna a la configuración regional invariable</span><span class="sxs-lookup"><span data-stu-id="c2a19-113">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="c2a19-114">3.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c2a19-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-115">.NET 5.0</span></span>

[!INCLUDE [unicode-categories-for-latin1-chars](../../../includes/core-changes/globalization/5.0/unicode-categories-for-latin1-chars.md)]

***

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="c2a19-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c2a19-116">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
