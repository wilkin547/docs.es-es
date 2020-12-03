---
title: 'Cambio importante: CreateCounterSetInstance inicia una excepción InvalidOperationException si ya existe la instancia'
description: Obtenga información sobre el cambio importante de .NET 5.0 en las bibliotecas básicas de.NET donde CounterSet.CreateCounterSetInstance inicia otra excepción si el contador ya existe.
ms.date: 11/01/2020
ms.openlocfilehash: 28042690b71f9b86e4e54748ec75467bbe232684
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95760205"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="27f15-103">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="27f15-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="27f15-104">A partir de .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> produce <xref:System.InvalidOperationException> en lugar de <xref:System.ArgumentException> si el conjunto de contadores ya existe.</span><span class="sxs-lookup"><span data-stu-id="27f15-104">Starting in .NET 5.0, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="27f15-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="27f15-105">Change description</span></span>

<span data-ttu-id="27f15-106">En .NET Framework y .NET Core 1.0 hasta la versión 3.1, puede crear una instancia del conjunto de contadores mediante una llamada a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="27f15-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="27f15-107">Pero si el conjunto de contadores ya existe, el método produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="27f15-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="27f15-108">En .NET 5.0 y versiones posteriores, cuando se llama a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> y el conjunto de contadores existe, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="27f15-108">In .NET 5.0 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="27f15-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="27f15-109">Version introduced</span></span>

<span data-ttu-id="27f15-110">5.0</span><span class="sxs-lookup"><span data-stu-id="27f15-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="27f15-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="27f15-111">Recommended action</span></span>

<span data-ttu-id="27f15-112">Si detecta excepciones de <xref:System.ArgumentException> en la aplicación al llamar a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, considere también la opción de detectar excepciones de <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="27f15-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="27f15-113">No se recomienda detectar excepciones de <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="27f15-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="27f15-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="27f15-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
