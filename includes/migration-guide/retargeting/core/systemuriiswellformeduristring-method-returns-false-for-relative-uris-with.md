---
ms.openlocfilehash: f7dcf9c4c3dc7ea536ddc847769a1a30f1298bb2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617282"
---
### <a name="systemuriiswellformeduristring-method-returns-false-for-relative-uris-with-a-colon-char-in-first-segment"></a><span data-ttu-id="1f014-101">El método System.Uri.IsWellFormedUriString devuelve false para los identificadores URI relativos con un carácter de dos puntos en el primer segmento</span><span class="sxs-lookup"><span data-stu-id="1f014-101">System.Uri.IsWellFormedUriString method returns false for relative URIs with a colon char in first segment</span></span>

#### <a name="details"></a><span data-ttu-id="1f014-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="1f014-102">Details</span></span>

<span data-ttu-id="1f014-103">A partir de .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> tratará los identificadores URI relativos con un `:` en el primer segmento como mal formados.</span><span class="sxs-lookup"><span data-stu-id="1f014-103">Beginning with the .NET Framework 4.5, <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)> will treat relative URIs with a `:` in their first segment as not well formed.</span></span> <span data-ttu-id="1f014-104">Se trata de un cambio con respecto al comportamiento de <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> en .NET Framework 4.0 que se realizó para cumplir con RFC3986.</span><span class="sxs-lookup"><span data-stu-id="1f014-104">This is a change from <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> behavior in the .NET Framework 4.0 that was made to conform to RFC3986.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="1f014-105">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="1f014-105">Suggestion</span></span>

<span data-ttu-id="1f014-106">Este cambio (como muchos otros cambios de URI) solo afecta a las aplicaciones destinadas a .NET Framework 4.5 (o una versión posterior).</span><span class="sxs-lookup"><span data-stu-id="1f014-106">This change (like many other URI changes) will only affect applications targeting the .NET Framework 4.5 (or later).</span></span> <span data-ttu-id="1f014-107">Para seguir usando el comportamiento anterior, cambie el destino de la aplicación a .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="1f014-107">To keep using the old behavior, target the app against the .NET Framework 4.0.</span></span> <span data-ttu-id="1f014-108">Como alternativa, examine el URI antes de llamar a <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> en busca de caracteres `:` que se puedan quitar con fines de validación, si quiere el comportamiento anterior.</span><span class="sxs-lookup"><span data-stu-id="1f014-108">Alternatively, scan URI's prior to calling <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=fullName> looking for `:` characters that you may want to remove for validation purposes, if the old behavior is desirable.</span></span>

| <span data-ttu-id="1f014-109">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="1f014-109">Name</span></span>    | <span data-ttu-id="1f014-110">Valor</span><span class="sxs-lookup"><span data-stu-id="1f014-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="1f014-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="1f014-111">Scope</span></span>   | <span data-ttu-id="1f014-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="1f014-112">Minor</span></span>       |
| <span data-ttu-id="1f014-113">Versión</span><span class="sxs-lookup"><span data-stu-id="1f014-113">Version</span></span> | <span data-ttu-id="1f014-114">4.5</span><span class="sxs-lookup"><span data-stu-id="1f014-114">4.5</span></span>         |
| <span data-ttu-id="1f014-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="1f014-115">Type</span></span>    | <span data-ttu-id="1f014-116">Redestinación</span><span class="sxs-lookup"><span data-stu-id="1f014-116">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="1f014-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="1f014-117">Affected APIs</span></span>

- <xref:System.Uri.IsWellFormedUriString(System.String,System.UriKind)?displayProperty=nameWithType>
