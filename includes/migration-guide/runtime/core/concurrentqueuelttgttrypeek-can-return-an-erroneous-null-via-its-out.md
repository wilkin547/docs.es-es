---
ms.openlocfilehash: 004e2d1883b631e88ab5e164b1120c3b081b7041
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497029"
---
### <a name="concurrentqueuelttgttrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="0c7a0-101">ConcurrentQueue&lt;T&gt;.TryPeek puede devolver un valor NULL erróneo mediante su parámetro out</span><span class="sxs-lookup"><span data-stu-id="0c7a0-101">ConcurrentQueue&lt;T&gt;.TryPeek can return an erroneous null via its out parameter</span></span>

#### <a name="details"></a><span data-ttu-id="0c7a0-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="0c7a0-102">Details</span></span>

<span data-ttu-id="0c7a0-103">En algunos escenarios con múltiples subprocesos, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).</span><span class="sxs-lookup"><span data-stu-id="0c7a0-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=fullName> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>

#### <a name="suggestion"></a><span data-ttu-id="0c7a0-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="0c7a0-104">Suggestion</span></span>

<span data-ttu-id="0c7a0-105">Este problema se corrigió en .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="0c7a0-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="0c7a0-106">Actualizar a esta versión de .NET Framework solucionará el problema.</span><span class="sxs-lookup"><span data-stu-id="0c7a0-106">Upgrading to that Framework will solve the issue.</span></span>

| <span data-ttu-id="0c7a0-107">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0c7a0-107">Name</span></span>    | <span data-ttu-id="0c7a0-108">Valor</span><span class="sxs-lookup"><span data-stu-id="0c7a0-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="0c7a0-109">Ámbito</span><span class="sxs-lookup"><span data-stu-id="0c7a0-109">Scope</span></span>   |<span data-ttu-id="0c7a0-110">Major</span><span class="sxs-lookup"><span data-stu-id="0c7a0-110">Major</span></span>|
|<span data-ttu-id="0c7a0-111">Versión</span><span class="sxs-lookup"><span data-stu-id="0c7a0-111">Version</span></span>|<span data-ttu-id="0c7a0-112">4.5</span><span class="sxs-lookup"><span data-stu-id="0c7a0-112">4.5</span></span>|
|<span data-ttu-id="0c7a0-113">Tipo</span><span class="sxs-lookup"><span data-stu-id="0c7a0-113">Type</span></span>|<span data-ttu-id="0c7a0-114">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="0c7a0-114">Runtime</span></span>|

#### <a name="affected-apis"></a><span data-ttu-id="0c7a0-115">API afectadas</span><span class="sxs-lookup"><span data-stu-id="0c7a0-115">Affected APIs</span></span>

- <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType>

<!--

#### Affected APIs

- ``M:System.Collections.Concurrent.ConcurrentQueue`1.TryPeek(`0@)``

-->
