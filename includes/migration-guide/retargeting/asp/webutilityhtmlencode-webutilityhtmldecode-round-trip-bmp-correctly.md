---
ms.openlocfilehash: acb5b467fc8f0692d8fa1b3b8263fd27308cc124
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617260"
---
### <a name="webutilityhtmlencode-and-webutilityhtmldecode-round-trip-bmp-correctly"></a><span data-ttu-id="e33b0-101">WebUtility.HtmlEncode y WebUtility.HtmlDecode realizan correctamente el recorrido de ida y vuelta de BMP</span><span class="sxs-lookup"><span data-stu-id="e33b0-101">WebUtility.HtmlEncode and WebUtility.HtmlDecode round-trip BMP correctly</span></span>

#### <a name="details"></a><span data-ttu-id="e33b0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="e33b0-102">Details</span></span>

<span data-ttu-id="e33b0-103">En las aplicaciones que tienen como destino .NET Framework 4.5, los caracteres que no pertenecen a Basic Multilingual Plane (BMP) realizan correctamente el recorrido de ida y vuelta cuando se pasan al método <xref:System.Net.WebUtility.HtmlDecode(System.String)>.</span><span class="sxs-lookup"><span data-stu-id="e33b0-103">For applications that target the .NET Framework 4.5, characters that are outside the Basic Multilingual Plane (BMP) round-trip correctly when they are passed to the <xref:System.Net.WebUtility.HtmlDecode(System.String)> methods.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e33b0-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="e33b0-104">Suggestion</span></span>

<span data-ttu-id="e33b0-105">Este cambio no debería tener ningún efecto en las aplicaciones actuales, pero, para restaurar el comportamiento original, establezca el atributo `targetFramework` del elemento `<httpRuntime>` en una cadena distinta a "4.5".</span><span class="sxs-lookup"><span data-stu-id="e33b0-105">This change should have no effect on current applications, but to restore the original behavior, set the `targetFramework` attribute of the `<httpRuntime>` element to a string other than "4.5".</span></span> <span data-ttu-id="e33b0-106">También puede establecer los atributos `unicodeEncodingConformance` y `unicodeDecodingConformance` del elemento de configuración `<webUtility>` para controlar este comportamiento con independencia de la versión de .NET Framework que se use como destino.</span><span class="sxs-lookup"><span data-stu-id="e33b0-106">You can also set the `unicodeEncodingConformance` and `unicodeDecodingConformance` attributes of the `<webUtility>` configuration element to control this behavior independently of the targeted version of the .NET Framework.</span></span>

| <span data-ttu-id="e33b0-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e33b0-107">Name</span></span>    | <span data-ttu-id="e33b0-108">Valor</span><span class="sxs-lookup"><span data-stu-id="e33b0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e33b0-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="e33b0-109">Scope</span></span>   | <span data-ttu-id="e33b0-110">Borde</span><span class="sxs-lookup"><span data-stu-id="e33b0-110">Edge</span></span>        |
| <span data-ttu-id="e33b0-111">Versión</span><span class="sxs-lookup"><span data-stu-id="e33b0-111">Version</span></span> | <span data-ttu-id="e33b0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="e33b0-112">4.5</span></span>         |
| <span data-ttu-id="e33b0-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="e33b0-113">Type</span></span>    | <span data-ttu-id="e33b0-114">Redestinación</span><span class="sxs-lookup"><span data-stu-id="e33b0-114">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="e33b0-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="e33b0-115">Affected APIs</span></span>

- <xref:System.Net.WebUtility.HtmlEncode(System.String)?displayProperty=nameWithType>
- <xref:System.Net.WebUtility.HtmlEncode(System.String,System.IO.TextWriter)?displayProperty=nameWithType>
