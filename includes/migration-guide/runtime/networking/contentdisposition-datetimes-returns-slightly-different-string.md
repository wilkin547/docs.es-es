---
ms.openlocfilehash: eb5c032a020799fa19cc0a8cfaabb56e01417ff4
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497835"
---
### <a name="contentdisposition-datetimes-returns-slightly-different-string"></a><span data-ttu-id="3630b-101">ContentDisposition DateTimes devuelve una cadena ligeramente diferente</span><span class="sxs-lookup"><span data-stu-id="3630b-101">ContentDisposition DateTimes returns slightly different string</span></span>

#### <a name="details"></a><span data-ttu-id="3630b-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="3630b-102">Details</span></span>

<span data-ttu-id="3630b-103">Se han actualizado las representaciones de cadena de los elementos <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>, a partir de la versión 4.6, para que representen siempre el componente de hora de un elemento <xref:System.DateTime?displayProperty=fullName> con dos dígitos.</span><span class="sxs-lookup"><span data-stu-id="3630b-103">String representations of <xref:System.Net.Mime.ContentDisposition?displayProperty=fullName>'s have been updated, beginning in 4.6, to always represent the hour component of a <xref:System.DateTime?displayProperty=fullName> with two digits.</span></span> <span data-ttu-id="3630b-104">La finalidad es cumplir con [RFC822](https://www.ietf.org/rfc/rfc0822.txt) y [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span><span class="sxs-lookup"><span data-stu-id="3630b-104">This is to comply with [RFC822](https://www.ietf.org/rfc/rfc0822.txt) and [RFC2822](https://www.ietf.org/rfc/rfc2822.txt).</span></span> <span data-ttu-id="3630b-105">De este modo, <xref:System.Net.Mime.ContentDisposition.ToString> devuelve una cadena ligeramente diferente en escenarios de la versión 4.6 en los que uno de los elementos de hora de la disposición era anterior a las 10:00.</span><span class="sxs-lookup"><span data-stu-id="3630b-105">This causes <xref:System.Net.Mime.ContentDisposition.ToString> to return a slightly different string in 4.6 in scenarios where one of the disposition's time elements was before 10:00 AM.</span></span> <span data-ttu-id="3630b-106">Tenga en cuenta que los elementos ContentDisposition a veces se serializan convirtiéndolos en cadenas, por lo que debería revisarse cualquier operación <xref:System.Net.Mime.ContentDisposition.ToString>, serialización o llamada a GetHashCode.</span><span class="sxs-lookup"><span data-stu-id="3630b-106">Note that ContentDispositions are sometimes serialized via converting them to strings, so any <xref:System.Net.Mime.ContentDisposition.ToString> operations, serialization, or GetHashCode calls should be reviewed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="3630b-107">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="3630b-107">Suggestion</span></span>

<span data-ttu-id="3630b-108">No espere que las representaciones de cadena de elementos ContentDisposition de otras versiones de .NET Framework se comparen correctamente entre sí.</span><span class="sxs-lookup"><span data-stu-id="3630b-108">Do not expect that string representations of ContentDispositions from different .NET Framework versions will correctly compare to one another.</span></span> <span data-ttu-id="3630b-109">Vuelva a convertir las cadenas a elementos ContentDisposition, si fuera posible, antes de realizar una comparación.</span><span class="sxs-lookup"><span data-stu-id="3630b-109">Convert the strings back to ContentDispositions, if possible, before conducting a comparison.</span></span>

| <span data-ttu-id="3630b-110">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3630b-110">Name</span></span>    | <span data-ttu-id="3630b-111">Valor</span><span class="sxs-lookup"><span data-stu-id="3630b-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="3630b-112">Ámbito</span><span class="sxs-lookup"><span data-stu-id="3630b-112">Scope</span></span>   |<span data-ttu-id="3630b-113">Secundaria</span><span class="sxs-lookup"><span data-stu-id="3630b-113">Minor</span></span>|
|<span data-ttu-id="3630b-114">Versión</span><span class="sxs-lookup"><span data-stu-id="3630b-114">Version</span></span>|<span data-ttu-id="3630b-115">4.6</span><span class="sxs-lookup"><span data-stu-id="3630b-115">4.6</span></span>|
|<span data-ttu-id="3630b-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="3630b-116">Type</span></span>|<span data-ttu-id="3630b-117">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3630b-117">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="3630b-118">API afectadas</span><span class="sxs-lookup"><span data-stu-id="3630b-118">Affected APIs</span></span>

- <xref:System.Net.Mime.ContentDisposition.ToString?displayProperty=nameWithType>
- <xref:System.Net.Mime.ContentDisposition.GetHashCode?displayProperty=nameWithType>

<!--

#### Affected APIs

- `M:System.Net.Mime.ContentDisposition.ToString`
- `M:System.Net.Mime.ContentDisposition.GetHashCode`

-->
