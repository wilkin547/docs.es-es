---
ms.openlocfilehash: 02a15f6b9c02002b60c568b9e1d871af49744092
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622144"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="b3eb3-101">ConcurrentQueue&lt;T&gt;.TryPeek puede devolver un valor NULL erróneo mediante su parámetro out</span><span class="sxs-lookup"><span data-stu-id="b3eb3-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="b3eb3-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="b3eb3-102">Details</span></span>

<span data-ttu-id="b3eb3-103">En algunos escenarios con múltiples subprocesos, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).</span><span class="sxs-lookup"><span data-stu-id="b3eb3-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="b3eb3-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="b3eb3-104">Suggestion</span></span>

<span data-ttu-id="b3eb3-105">Este problema se corrigió en .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="b3eb3-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="b3eb3-106">Actualizar a esta versión de .NET Framework solucionará el problema.</span><span class="sxs-lookup"><span data-stu-id="b3eb3-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="b3eb3-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b3eb3-107">Name</span></span>    | <span data-ttu-id="b3eb3-108">Valor</span><span class="sxs-lookup"><span data-stu-id="b3eb3-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="b3eb3-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="b3eb3-109">Scope</span></span>   |<span data-ttu-id="b3eb3-110">Major</span><span class="sxs-lookup"><span data-stu-id="b3eb3-110">Major</span></span>|
|<span data-ttu-id="b3eb3-111">Versión</span><span class="sxs-lookup"><span data-stu-id="b3eb3-111">Version</span></span>|<span data-ttu-id="b3eb3-112">4.5</span><span class="sxs-lookup"><span data-stu-id="b3eb3-112">4.5</span></span>|
|<span data-ttu-id="b3eb3-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="b3eb3-113">Type</span></span>|<span data-ttu-id="b3eb3-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b3eb3-114">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="b3eb3-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="b3eb3-115">Affected APIs</span></span>

-<xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
