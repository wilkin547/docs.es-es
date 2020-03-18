---
ms.openlocfilehash: 30580b3fde5b8a99862896bb7d31c6c4024f97e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "74568086"
---
### <a name="floating-point-parsing-operations-no-longer-fail-or-throw-an-overflowexception"></a>Las operaciones de análisis de punto flotante ya no producen un error o lanzan una excepción OverflowException

Los métodos de análisis de punto flotante ya no lanzan una <xref:System.OverflowException> o devuelven `false` cuando analizan una cadena cuyo valor numérico está fuera del rango del tipo de punto flotante <xref:System.Single> o <xref:System.Double>.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y versiones anteriores, los métodos <xref:System.Double.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.Parse%2A?displayProperty=nameWithType> lanzan una <xref:System.OverflowException> para los valores que se encuentran fuera del rango de su tipo respectivo. Los métodos <xref:System.Double.TryParse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> devuelven `false` para las representaciones de cadena de valores numéricos fuera del rango.

A partir de .NET Core 3.0, los métodos <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> ya no producen errores al analizar cadenas numéricas fuera del rango. En su lugar, los métodos de análisis de <xref:System.Double> devuelven <xref:System.Double.PositiveInfinity?displayProperty=nameWithType> para los valores que superan <xref:System.Double.MaxValue?displayProperty=nameWithType> y <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> para los valores menores que <xref:System.Double.MinValue?displayProperty=nameWithType>. Del mismo modo, los métodos de análisis de <xref:System.Single> devuelven <xref:System.Single.PositiveInfinity?displayProperty=nameWithType> para los valores que superan <xref:System.Single.MaxValue?displayProperty=nameWithType> y <xref:System.Single.NegativeInfinity?displayProperty=nameWithType> para los valores menores que <xref:System.Single.MinValue?displayProperty=nameWithType>.

Este cambio se ha realizado para mejorar el cumplimiento de la norma IEEE 754:2008.

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

Este cambio puede afectar al código de alguna de estas dos formas:

- El código depende del controlador para que <xref:System.OverflowException> se ejecute cuando se produce un desbordamiento. En este caso, debe quitar la instrucción `catch` y colocar cualquier código necesario en una instrucción `If` que compruebe si <xref:System.Double.IsInfinity%2A?displayProperty=nameWithType> o <xref:System.Single.IsInfinity%2A?displayProperty=nameWithType> es `true`.

- El código presupone que los valores de punto flotante no son `Infinity`. En este caso, debe agregar el código necesario para comprobar los valores de punto flotante de `PositiveInfinity` y `NegativeInfinity`.

#### <a name="category"></a>Categoría

CoreFX

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!--

### Affected APIs

- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
