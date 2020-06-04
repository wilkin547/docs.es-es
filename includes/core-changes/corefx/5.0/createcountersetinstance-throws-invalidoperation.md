---
ms.openlocfilehash: fabbc9a51f61a703ce97db50ab251e7a13ffe348
ms.sourcegitcommit: ee5b798427f81237a3c23d1fd81fff7fdc21e8d3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "84144491"
---
### <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="76273-101">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="76273-101">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="76273-102">A partir de .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> produce <xref:System.InvalidOperationException> en lugar de <xref:System.ArgumentException> si el conjunto de contadores ya existe.</span><span class="sxs-lookup"><span data-stu-id="76273-102">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

#### <a name="change-description"></a><span data-ttu-id="76273-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="76273-103">Change description</span></span>

<span data-ttu-id="76273-104">En .NET Framework y .NET Core 1.0 hasta la versión 3.1, puede crear una instancia del conjunto de contadores mediante una llamada a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="76273-104">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="76273-105">Pero si el conjunto de contadores ya existe, el método produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="76273-105">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="76273-106">En .NET 5.0 y versiones posteriores, cuando se llama a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> y el conjunto de contadores existe, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="76273-106">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="76273-107">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="76273-107">Version introduced</span></span>

<span data-ttu-id="76273-108">5.0 (versión preliminar 5)</span><span class="sxs-lookup"><span data-stu-id="76273-108">5.0 Preview 5</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="76273-109">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="76273-109">Recommended action</span></span>

<span data-ttu-id="76273-110">Si detecta excepciones de <xref:System.ArgumentException> en la aplicación al llamar a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, considere también la opción de detectar excepciones de <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="76273-110">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="76273-111">No se recomienda detectar excepciones de <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="76273-111">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

#### <a name="category"></a><span data-ttu-id="76273-112">Categoría</span><span class="sxs-lookup"><span data-stu-id="76273-112">Category</span></span>

<span data-ttu-id="76273-113">Bibliotecas de Core .NET</span><span class="sxs-lookup"><span data-stu-id="76273-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="76273-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="76273-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
