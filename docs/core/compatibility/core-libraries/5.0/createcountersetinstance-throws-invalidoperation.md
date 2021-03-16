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
# <a name="countersetcreatecountersetinstance-now-throws-invalidoperationexception-if-instance-already-exists"></a>CounterSet.CreateCounterSetInstance ahora produce una excepción InvalidOperationException si ya existe la instancia

A partir de .NET 5, <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)?displayProperty=nameWithType> produce <xref:System.InvalidOperationException> en lugar de <xref:System.ArgumentException> si el conjunto de contadores ya existe.

## <a name="change-description"></a>Descripción del cambio

En .NET Framework y .NET Core 1.0 hasta la versión 3.1, puede crear una instancia del conjunto de contadores mediante una llamada a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>. Pero si el conjunto de contadores ya existe, el método produce una excepción <xref:System.ArgumentException>.

En .NET 5 y versiones posteriores, cuando se llama a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A> y el conjunto de contadores existe, se produce una excepción <xref:System.InvalidOperationException>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Si detecta excepciones de <xref:System.ArgumentException> en la aplicación al llamar a <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A>, considere también la opción de detectar excepciones de <xref:System.InvalidOperationException>.

> [!NOTE]
> No se recomienda detectar excepciones de <xref:System.ArgumentException>.

## <a name="affected-apis"></a>API afectadas

- <xref:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance%2A?displayProperty=fullName>

<!--

### Category

Core .NET libraries

### Affected APIs

- `M:System.Diagnostics.PerformanceData.CounterSet.CreateCounterSetInstance(System.String)`

-->
