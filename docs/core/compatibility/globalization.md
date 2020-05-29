---
title: Cambios importantes de la globalización
description: Enumera los cambios importantes de la globalización en .NET Core.
ms.date: 04/07/2020
ms.openlocfilehash: 0c3367cb3515c6f473f53be6062b54f2e836b8c5
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702296"
---
# <a name="globalization-breaking-changes"></a><span data-ttu-id="dfeed-103">Cambios importantes de la globalización</span><span class="sxs-lookup"><span data-stu-id="dfeed-103">Globalization breaking changes</span></span>

<span data-ttu-id="dfeed-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="dfeed-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="dfeed-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="dfeed-105">Breaking change</span></span> | <span data-ttu-id="dfeed-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="dfeed-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="dfeed-107">Las API de globalización usan bibliotecas de ICU en Windows</span><span class="sxs-lookup"><span data-stu-id="dfeed-107">Globalization APIs use ICU libraries on Windows</span></span>](#globalization-apis-use-icu-libraries-on-windows) | <span data-ttu-id="dfeed-108">5.0</span><span class="sxs-lookup"><span data-stu-id="dfeed-108">5.0</span></span> |
| [<span data-ttu-id="dfeed-109">StringInfo y TextElementEnumerator ahora son compatibles con UAX29</span><span class="sxs-lookup"><span data-stu-id="dfeed-109">StringInfo and TextElementEnumerator are now UAX29-compliant</span></span>](#stringinfo-and-textelementenumerator-are-now-uax29-compliant) | <span data-ttu-id="dfeed-110">5.0</span><span class="sxs-lookup"><span data-stu-id="dfeed-110">5.0</span></span> |
| [<span data-ttu-id="dfeed-111">La configuración regional de "C" se asigna a la configuración regional invariable</span><span class="sxs-lookup"><span data-stu-id="dfeed-111">"C" locale maps to the invariant locale</span></span>](#c-locale-maps-to-the-invariant-locale) | <span data-ttu-id="dfeed-112">3.0</span><span class="sxs-lookup"><span data-stu-id="dfeed-112">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="dfeed-113">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="dfeed-113">.NET 5.0</span></span>

[!INCLUDE [icu-globalization-api](../../../includes/core-changes/globalization/5.0/icu-globalization-api.md)]

***

[!INCLUDE [uax29-compliant-grapheme-enumeration](../../../includes/core-changes/globalization/5.0/uax29-compliant-grapheme-enumeration.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="dfeed-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="dfeed-114">.NET Core 3.0</span></span>

[!INCLUDE["C" locale maps to the invariant locale](~/includes/core-changes/globalization/3.0/c-locale-maps-to-invariant-locale.md)]

***
