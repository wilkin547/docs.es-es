---
title: 'Cambio importante: IntPtr y UIntPtr implementan IFormattable'
description: Obtenga información sobre el cambio importante de .NET 5 en las bibliotecas básicas de .NET, donde IntPtr y UIntPtr implementan ahora IFormattable.
ms.date: 11/01/2020
ms.openlocfilehash: adfb68807d5fa5f0c750fb41ef75951f63a4b2d5
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2021
ms.locfileid: "102257445"
---
# <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr y UIntPtr implementan IFormattable

<xref:System.IntPtr> y <xref:System.UIntPtr> ahora implementan <xref:System.IFormattable>. Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.

## <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.IntPtr> y <xref:System.UIntPtr> no implementan <xref:System.IFormattable>. Las funciones que comprueban <xref:System.IFormattable> pueden revertir simplemente a llamar a <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> o <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, lo que significa que no se respetan los especificadores de formato ni las referencias culturales.

En .NET 5 y versiones posteriores, <xref:System.IntPtr> y <xref:System.UIntPtr> implementan <xref:System.IFormattable>. Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.

Este cambio afecta a escenarios como cadenas interpoladas y <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, entre otros.

## <a name="reason-for-change"></a>Motivo del cambio

<xref:System.IntPtr> y <xref:System.UIntPtr> ahora tienen compatibilidad de lenguaje en C# mediante las palabras clave `nint` y `nuint`. Los tipos de respaldo se han actualizado para proporcionar paridad cercana (siempre que sea posible) con funcionalidad expuesta por otros tipos primitivos, como <xref:System.Int32?displayProperty=nameWithType>.

## <a name="version-introduced"></a>Versión introducida

5.0

## <a name="recommended-action"></a>Acción recomendada

Si no quiere que se use un especificador de formato o una referencia cultural personalizada al mostrar valores de estos tipos, puede llamar a las sobrecargas <xref:System.IntPtr.ToString?displayProperty=nameWithType> y <xref:System.UIntPtr.ToString?displayProperty=nameWithType> de `ToString()`.

## <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

### Category

Core .NET libraries

### Affected APIs

Not detectable via API analysis.

-->
