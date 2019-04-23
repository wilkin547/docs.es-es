---
ms.openlocfilehash: a93fbbd787aa50f080337a6170cf8f56d0d24e31
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59805075"
---
### <a name="concurrentqueuettrypeek-can-return-an-erroneous-null-via-its-out-parameter"></a><span data-ttu-id="24058-101">ConcurrentQueue\<T>.TryPeek puede devolver un valor NULL erróneo mediante su parámetro out</span><span class="sxs-lookup"><span data-stu-id="24058-101">ConcurrentQueue\<T>.TryPeek can return an erroneous null via its out parameter</span></span>

|   |   |
|---|---|
|<span data-ttu-id="24058-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="24058-102">Details</span></span>|<span data-ttu-id="24058-103">En algunos escenarios con múltiples subprocesos, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> puede devolver true, pero rellenar el parámetro out con un valor nulo (en lugar del valor correcto observado).</span><span class="sxs-lookup"><span data-stu-id="24058-103">In some multi-threaded scenarios, <xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=name> can return true, but populate the out parameter with a null value (instead of the correct, peeked value).</span></span>|
|<span data-ttu-id="24058-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="24058-104">Suggestion</span></span>|<span data-ttu-id="24058-105">Este problema se corrigió en .NET Framework 4.5.1.</span><span class="sxs-lookup"><span data-stu-id="24058-105">This issue is fixed in the .NET Framework 4.5.1.</span></span> <span data-ttu-id="24058-106">Actualizar a esta versión de .NET Framework solucionará el problema.</span><span class="sxs-lookup"><span data-stu-id="24058-106">Upgrading to that Framework will solve the issue.</span></span>|
|<span data-ttu-id="24058-107">Ámbito</span><span class="sxs-lookup"><span data-stu-id="24058-107">Scope</span></span>|<span data-ttu-id="24058-108">Major</span><span class="sxs-lookup"><span data-stu-id="24058-108">Major</span></span>|
|<span data-ttu-id="24058-109">Versión</span><span class="sxs-lookup"><span data-stu-id="24058-109">Version</span></span>|<span data-ttu-id="24058-110">4.5</span><span class="sxs-lookup"><span data-stu-id="24058-110">4.5</span></span>|
|<span data-ttu-id="24058-111">Tipo</span><span class="sxs-lookup"><span data-stu-id="24058-111">Type</span></span>|<span data-ttu-id="24058-112">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="24058-112">Runtime</span></span>|
|<span data-ttu-id="24058-113">API afectadas</span><span class="sxs-lookup"><span data-stu-id="24058-113">Affected APIs</span></span>|<ul><li><xref:System.Collections.Concurrent.ConcurrentQueue%601.TryPeek(%600@)?displayProperty=nameWithType></li></ul>|
