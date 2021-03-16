---
title: 'Cambio importante: CreateCounterSetInstance inicia una excepción InvalidOperationException si ya existe la instancia'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de.NET donde CounterSet.CreateCounterSetInstance inicia otra excepción si el contador ya existe.
ms.date: 11/01/2020
ms.openlocfilehash: bf59677a85538bc4992c589f8642ab4a0fce54ac
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257575"
---
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a><span data-ttu-id="d9783-103">CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia</span><span class="sxs-lookup"><span data-stu-id="d9783-103">CounterSet.CreateCounterSetInstance now throws InvalidOperationException if instance already exists</span></span>

<span data-ttu-id="d9783-104">A partir de .NET 5, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> produce <xref:System.InvalidOperationException> en lugar de <xref:System.ArgumentException> si el conjunto de contadores ya existe.</span><span class="sxs-lookup"><span data-stu-id="d9783-104">Starting in .NET 5, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> throws an <xref:System.InvalidOperationException> instead of an <xref:System.ArgumentException> if the counter set already exists.</span></span>

## <a name="change-description"></a><span data-ttu-id="d9783-105">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="d9783-105">Change description</span></span>

<span data-ttu-id="d9783-106">En .NET Framework y .NET Core 1.0 hasta la versión 3.1, puede crear una instancia del conjunto de contadores mediante una llamada a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="d9783-106">In .NET Framework and .NET Core 1.0 to 3.1, you can create an instance of the counter set by calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>.</span></span> <span data-ttu-id="d9783-107">Pero si el conjunto de contadores ya existe, el método produce una excepción <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="d9783-107">However, if the counter set already exists, the method throws an <xref:System.ArgumentException> exception.</span></span>

<span data-ttu-id="d9783-108">En .NET 5 y versiones posteriores, cuando se llama a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> y el conjunto de contadores existe, se produce una excepción <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="d9783-108">In .NET 5 and later versions, when you call <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> and the counter set exists, an <xref:System.InvalidOperationException> exception is thrown.</span></span>

## <a name="version-introduced"></a><span data-ttu-id="d9783-109">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="d9783-109">Version introduced</span></span>

<span data-ttu-id="d9783-110">5.0</span><span class="sxs-lookup"><span data-stu-id="d9783-110">5.0</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d9783-111">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="d9783-111">Recommended action</span></span>

<span data-ttu-id="d9783-112">Si detecta excepciones de <xref:System.ArgumentException> en la aplicación al llamar a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, considere también la opción de detectar excepciones de <xref:System.InvalidOperationException>.</span><span class="sxs-lookup"><span data-stu-id="d9783-112">If you catch <xref:System.ArgumentException> exceptions in your app when calling <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, consider also catching <xref:System.InvalidOperationException> exceptions.</span></span>

> [!NOTE]
> <span data-ttu-id="d9783-113">No se recomienda detectar excepciones de <xref:System.ArgumentException>.</span><span class="sxs-lookup"><span data-stu-id="d9783-113">Catching <xref:System.ArgumentException> exceptions is not recommended.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d9783-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="d9783-114">Affected APIs</span></span>

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
