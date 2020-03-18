---
ms.openlocfilehash: efa0efaf40e2e432d477f1659d7bde3abc98241d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857506"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="8d2b6-101">Ahora se admiten las categorías de la versión 8.0 del estándar Unicode</span><span class="sxs-lookup"><span data-stu-id="8d2b6-101">Unicode standard version 8.0 categories now supported</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8d2b6-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="8d2b6-102">Details</span></span>|<span data-ttu-id="8d2b6-103">En .NET Framework 4.6.2, los datos Unicode se han actualizado de la versión 6.3 del estándar Unicode a la versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="8d2b6-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="8d2b6-104">Al solicitar las categorías de caracteres Unicode en .NET Framework 4.6.2, es posible que algunos de los resultados no coincidan con los de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="8d2b6-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="8d2b6-105">Este cambio afecta principalmente a las sílabas cheroquis y a las marcas de tono y signos de vocal Nuevo Tai Lue.</span><span class="sxs-lookup"><span data-stu-id="8d2b6-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>|
|<span data-ttu-id="8d2b6-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="8d2b6-106">Suggestion</span></span>|<span data-ttu-id="8d2b6-107">Revise el código y quite o cambie la lógica que depende de categorías de caracteres Unicode codificados de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="8d2b6-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>|
|<span data-ttu-id="8d2b6-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="8d2b6-108">Scope</span></span>|<span data-ttu-id="8d2b6-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="8d2b6-109">Minor</span></span>|
|<span data-ttu-id="8d2b6-110">Versión</span><span class="sxs-lookup"><span data-stu-id="8d2b6-110">Version</span></span>|<span data-ttu-id="8d2b6-111">4.6.2</span><span class="sxs-lookup"><span data-stu-id="8d2b6-111">4.6.2</span></span>|
|<span data-ttu-id="8d2b6-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="8d2b6-112">Type</span></span>|<span data-ttu-id="8d2b6-113">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="8d2b6-113">Runtime</span></span>|
|<span data-ttu-id="8d2b6-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="8d2b6-114">Affected APIs</span></span>|<ul><li><xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType></li><li><xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType></li></ul>|
