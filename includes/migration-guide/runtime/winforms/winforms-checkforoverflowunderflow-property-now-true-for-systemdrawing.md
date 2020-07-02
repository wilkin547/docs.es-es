---
ms.openlocfilehash: 4cd06fd02fadbaa9f74e40f850e688ee883454ed
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620695"
---
### <a name="winforms-checkforoverflowunderflow-property-is-now-true-for-systemdrawing"></a><span data-ttu-id="96610-101">La propiedad CheckForOverflowUnderflow de WinForm ahora es true para System.Drawing</span><span class="sxs-lookup"><span data-stu-id="96610-101">WinForm's CheckForOverflowUnderflow property is now true for System.Drawing</span></span>

#### <a name="details"></a><span data-ttu-id="96610-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="96610-102">Details</span></span>

<span data-ttu-id="96610-103">La propiedad CheckForOverflowUnderflow para el ensamblado System.Drawing.dll se establece en true.</span><span class="sxs-lookup"><span data-stu-id="96610-103">The CheckForOverflowUnderflow property for the System.Drawing.dll assembly is set to true.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="96610-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="96610-104">Suggestion</span></span>

<span data-ttu-id="96610-105">Anteriormente, cuando se producían desbordamientos, el resultado se truncaba de manera silenciosa.</span><span class="sxs-lookup"><span data-stu-id="96610-105">Previously when overflows occurred, the result would be silently truncated.</span></span> <span data-ttu-id="96610-106">Ahora se inicia una excepción <xref:System.OverflowException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="96610-106">Now an <xref:System.OverflowException?displayProperty=fullName> exception is thrown.</span></span>

| <span data-ttu-id="96610-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="96610-107">Name</span></span>    | <span data-ttu-id="96610-108">Valor</span><span class="sxs-lookup"><span data-stu-id="96610-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="96610-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="96610-109">Scope</span></span>   |<span data-ttu-id="96610-110">Borde</span><span class="sxs-lookup"><span data-stu-id="96610-110">Edge</span></span>|
|<span data-ttu-id="96610-111">Versión</span><span class="sxs-lookup"><span data-stu-id="96610-111">Version</span></span>|<span data-ttu-id="96610-112">4.5</span><span class="sxs-lookup"><span data-stu-id="96610-112">4.5</span></span>|
|<span data-ttu-id="96610-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="96610-113">Type</span></span>|<span data-ttu-id="96610-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="96610-114">Runtime</span></span>|
