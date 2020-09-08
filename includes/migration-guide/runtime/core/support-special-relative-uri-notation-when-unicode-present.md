---
ms.openlocfilehash: 3c32d2e13447f8fd9aa6b185b5fc7e60f9e1bb61
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496838"
---
### <a name="support-special-relative-uri-notation-when-unicode-is-present"></a><span data-ttu-id="abe8a-101">Admitir una notación de URI relativo especial cuando Unicode está presente</span><span class="sxs-lookup"><span data-stu-id="abe8a-101">Support special relative URI notation when Unicode is present</span></span>

#### <a name="details"></a><span data-ttu-id="abe8a-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="abe8a-102">Details</span></span>

<span data-ttu-id="abe8a-103"><xref:System.Uri> ya no lanzará una excepción <xref:System.NullReferenceException> al llamar a <xref:System.Uri.TryCreate%2A> en ciertos URI relativos que contienen Unicode.</span><span class="sxs-lookup"><span data-stu-id="abe8a-103"><xref:System.Uri> will no longer throw a <xref:System.NullReferenceException> when calling <xref:System.Uri.TryCreate%2A> on certain relative URIs containing Unicode.</span></span> <span data-ttu-id="abe8a-104">La reproducción más sencilla de <xref:System.NullReferenceException> se muestra a continuación, donde las dos instrucciones son equivalentes:</span><span class="sxs-lookup"><span data-stu-id="abe8a-104">The simplest reproduction of the <xref:System.NullReferenceException> is below, with the two statements being equivalent:</span></span><pre><code class="lang-csharp">bool success = Uri.TryCreate(&quot;http:%C3%A8&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;bool success = Uri.TryCreate(&quot;http:&#232;&quot;, UriKind.RelativeOrAbsolute, out Uri href);&#13;&#10;</code></pre><span data-ttu-id="abe8a-105">Para reproducir la excepción <xref:System.NullReferenceException>, se debe cumplir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="abe8a-105">To reproduce the <xref:System.NullReferenceException>, the following items must be true:</span></span><ul><li><span data-ttu-id="abe8a-106">El URI se debe especificar como relativo anteponiendo "http:" y excluyendo "//" después.</span><span class="sxs-lookup"><span data-stu-id="abe8a-106">The URI must be specified as relative by prepending it with ‘http:’ and not following it with ‘//’.</span></span></li><li><span data-ttu-id="abe8a-107">El URI debe contener símbolos no reservados o Unicode codificados por porcentaje.</span><span class="sxs-lookup"><span data-stu-id="abe8a-107">The URI must contain percent-encoded Unicode or unreserved symbols.</span></span></li></ul>

#### <a name="suggestion"></a><span data-ttu-id="abe8a-108">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="abe8a-108">Suggestion</span></span>

<span data-ttu-id="abe8a-109">Los usuarios que dependan de este comportamiento para no permitir los URI relativos deben especificar en su lugar <xref:System.UriKind.Absolute?displayProperty=nameWithType> al crear un URI.</span><span class="sxs-lookup"><span data-stu-id="abe8a-109">Users depending on this behavior to disallow relative URIs should instead specify <xref:System.UriKind.Absolute?displayProperty=nameWithType> when creating a URI.</span></span>

| <span data-ttu-id="abe8a-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="abe8a-110">Name</span></span>    | <span data-ttu-id="abe8a-111">Valor</span><span class="sxs-lookup"><span data-stu-id="abe8a-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="abe8a-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="abe8a-112">Scope</span></span>   |<span data-ttu-id="abe8a-113">Borde</span><span class="sxs-lookup"><span data-stu-id="abe8a-113">Edge</span></span>|
|<span data-ttu-id="abe8a-114">Versión</span><span class="sxs-lookup"><span data-stu-id="abe8a-114">Version</span></span>|<span data-ttu-id="abe8a-115">4.7.2</span><span class="sxs-lookup"><span data-stu-id="abe8a-115">4.7.2</span></span>|
|<span data-ttu-id="abe8a-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="abe8a-116">Type</span></span>|<span data-ttu-id="abe8a-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="abe8a-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="abe8a-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="abe8a-118">Affected APIs</span></span>

- <xref:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)?displayProperty=nameWithType>
- <xref:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Uri.TryCreate(System.Uri,System.Uri,System.Uri@)`
- `M:System.Uri.TryCreate(System.String,System.UriKind,System.Uri@)`
- `M:System.Uri.TryCreate(System.Uri,System.String,System.Uri@)`

-->
