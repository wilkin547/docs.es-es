---
ms.openlocfilehash: f389a9e9bcf4ac1777db66731a085d74889c4a98
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496230"
---
### <a name="unicode-standard-version-80-categories-now-supported"></a><span data-ttu-id="c85a2-101">Ahora se admiten las categorías de la versión 8.0 del estándar Unicode</span><span class="sxs-lookup"><span data-stu-id="c85a2-101">Unicode standard version 8.0 categories now supported</span></span>

#### <a name="details"></a><span data-ttu-id="c85a2-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="c85a2-102">Details</span></span>

<span data-ttu-id="c85a2-103">En .NET Framework 4.6.2, los datos Unicode se han actualizado de la versión 6.3 del estándar Unicode a la versión 8.0.</span><span class="sxs-lookup"><span data-stu-id="c85a2-103">In .NET Framework 4.6.2, Unicode data has been upgraded from Unicode Standard version 6.3 to version 8.0.</span></span>  <span data-ttu-id="c85a2-104">Al solicitar las categorías de caracteres Unicode en .NET Framework 4.6.2, es posible que algunos de los resultados no coincidan con los de versiones anteriores de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c85a2-104">When requesting Unicode character categories in .NET Framework 4.6.2, some results might not match the results in previous .NET Framework versions.</span></span>  <span data-ttu-id="c85a2-105">Este cambio afecta principalmente a las sílabas cheroquis y a las marcas de tono y signos de vocal Nuevo Tai Lue.</span><span class="sxs-lookup"><span data-stu-id="c85a2-105">This change mostly affects Cherokee syllables and New Tai Lue vowels signs and tone marks.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="c85a2-106">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="c85a2-106">Suggestion</span></span>

<span data-ttu-id="c85a2-107">Revise el código y quite o cambie la lógica que depende de categorías de caracteres Unicode codificados de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="c85a2-107">Review code and remove/change logic that depends on hard-coded Unicode character categories.</span></span>

| <span data-ttu-id="c85a2-108">Nombre</span><span class="sxs-lookup"><span data-stu-id="c85a2-108">Name</span></span>    | <span data-ttu-id="c85a2-109">Valor</span><span class="sxs-lookup"><span data-stu-id="c85a2-109">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="c85a2-110">Ámbito</span><span class="sxs-lookup"><span data-stu-id="c85a2-110">Scope</span></span>   |<span data-ttu-id="c85a2-111">Secundaria</span><span class="sxs-lookup"><span data-stu-id="c85a2-111">Minor</span></span>|
|<span data-ttu-id="c85a2-112">Versión</span><span class="sxs-lookup"><span data-stu-id="c85a2-112">Version</span></span>|<span data-ttu-id="c85a2-113">4.6.2</span><span class="sxs-lookup"><span data-stu-id="c85a2-113">4.6.2</span></span>|
|<span data-ttu-id="c85a2-114">Tipo</span><span class="sxs-lookup"><span data-stu-id="c85a2-114">Type</span></span>|<span data-ttu-id="c85a2-115">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="c85a2-115">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="c85a2-116">API afectadas</span><span class="sxs-lookup"><span data-stu-id="c85a2-116">Affected APIs</span></span>

- <xref:System.Char.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)?displayProperty=nameWithType>
- <xref:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Char.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.Char)`
- `M:System.Globalization.CharUnicodeInfo.GetUnicodeCategory(System.String,System.Int32)`

-->
