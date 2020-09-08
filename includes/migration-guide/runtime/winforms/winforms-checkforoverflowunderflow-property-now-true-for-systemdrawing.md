---
ms.openlocfilehash: 68b0c4bb032b9744ef585eaef3d68e31afebee24
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497123"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="61b99-101">La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing</span><span class="sxs-lookup"><span data-stu-id="61b99-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="61b99-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="61b99-102">Details</span></span>

<span data-ttu-id="61b99-103">La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.</span><span class="sxs-lookup"><span data-stu-id="61b99-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61b99-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="61b99-104">Suggestion</span></span>

<span data-ttu-id="61b99-105">Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa.</span><span class="sxs-lookup"><span data-stu-id="61b99-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="61b99-106">Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="61b99-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="61b99-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="61b99-107">Name</span></span>    | <span data-ttu-id="61b99-108">Valor</span><span class="sxs-lookup"><span data-stu-id="61b99-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61b99-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="61b99-109">Scope</span></span>   |<span data-ttu-id="61b99-110">Borde</span><span class="sxs-lookup"><span data-stu-id="61b99-110">Edge</span></span>|
|<span data-ttu-id="61b99-111">Versión</span><span class="sxs-lookup"><span data-stu-id="61b99-111">Version</span></span>|<span data-ttu-id="61b99-112">4.5</span><span class="sxs-lookup"><span data-stu-id="61b99-112">4.5</span></span>|
|<span data-ttu-id="61b99-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="61b99-113">Type</span></span>|<span data-ttu-id="61b99-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="61b99-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="61b99-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="61b99-115">Affected APIs</span></span>

<span data-ttu-id="61b99-116">No detectable a través del análisis de la API.</span><span class="sxs-lookup"><span data-stu-id="61b99-116">Not detectable via API analysis.</span></span>

<!--

#### Affected APIs

Not detectable via API analysis.

-->
