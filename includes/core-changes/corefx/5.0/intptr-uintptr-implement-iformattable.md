---
ms.openlocfilehash: 3d29848e12d496d2d53c204e00ef8604831495e1
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024709"
---
### <a name="intptr-and-uintptr-implement-iformattable"></a>IntPtr y UIntPtr implementan IFormattable

<xref:System.IntPtr> y <xref:System.UIntPtr> ahora implementan <xref:System.IFormattable>. Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.

#### <a name="change-description"></a>Descripción del cambio

En versiones anteriores de .NET, <xref:System.IntPtr> y <xref:System.UIntPtr> no implementan <xref:System.IFormattable>. Las funciones que comprueban <xref:System.IFormattable> pueden revertir simplemente a llamar a <xref:System.IntPtr.ToString%2A?displayProperty=nameWithType> o <xref:System.UIntPtr.ToString%2A?displayProperty=nameWithType>, lo que significa que no se respetan los especificadores de formato ni las referencias culturales.

En .NET 5.0 y versiones posteriores, <xref:System.IntPtr> y <xref:System.UIntPtr> implementan <xref:System.IFormattable>. Las funciones que comprueban la compatibilidad de <xref:System.IFormattable> ahora pueden devolver resultados diferentes para estos tipos, ya que pueden pasar un especificador de formato y una referencia cultural.

Este cambio afecta a escenarios como cadenas interpoladas y <xref:System.Console.WriteLine%2A?displayProperty=nameWithType>, entre otros.

#### <a name="reason-for-change"></a>Motivo del cambio

<xref:System.IntPtr> y <xref:System.UIntPtr> ahora tienen compatibilidad de lenguaje en C# mediante las palabras clave `nint` y `nuint`. Los tipos de respaldo se han actualizado para proporcionar paridad cercana (siempre que sea posible) con funcionalidad expuesta por otros tipos primitivos, como <xref:System.Int32?displayProperty=nameWithType>.

#### <a name="version-introduced"></a>Versión introducida

5.0 (versión preliminar 4)

#### <a name="recommended-action"></a>Acción recomendada

Si no quiere que se use un especificador de formato o una referencia cultural personalizada al mostrar valores de estos tipos, puede llamar a las sobrecargas <xref:System.IntPtr.ToString?displayProperty=nameWithType> y <xref:System.UIntPtr.ToString?displayProperty=nameWithType> de `ToString()`.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
