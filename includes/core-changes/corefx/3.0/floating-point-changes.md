---
ms.openlocfilehash: 22dbb1e982f83687a9e0eb288ed72c78c676db77
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021587"
---
### <a name="floating-point-formatting-and-parsing-behavior-changed"></a>Cambios en los comportamientos de formato y análisis de los números de punto flotante

Los comportamientos de formato y análisis de los números de punto flotante (de los tipos <xref:System.Double> y <xref:System.Single>) ahora son compatibles con IEEE.

#### <a name="change-description"></a>Descripción del cambio

En .NET Core 2.2 y en versiones anteriores, dar formato con <xref:System.Double.ToString%2A?displayProperty=nameWithType> y <xref:System.Single.ToString%2A?displayProperty=nameWithType>, y realizar análisis con <xref:System.Double.Parse%2A?displayProperty=nameWithType>, <xref:System.Double.TryParse%2A?displayProperty=nameWithType>, <xref:System.Single.Parse%2A?displayProperty=nameWithType> y <xref:System.Single.TryParse%2A?displayProperty=nameWithType> no es compatible con IEEE. Como resultado, no es posible garantizar que un valor realizará todo el proceso con una cadena de formato estándar o personalizado compatible. En algunas entradas, se puede producir un error al intentar analizar un valor con formato y, en otras, el valor analizado no es igual que el valor original.

A partir de .NET Core 3.0, las operaciones de análisis y formato son compatibles con IEEE 754. Esto garantiza que el comportamiento de los tipos de punto flotante en .NET coincide con el de los lenguajes compatibles con IEEE, como C#. Para obtener más información, vea la entrada de blog [Mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="recommended-action"></a>Acción recomendada

En la sección “Posible impacto en el código existente” de la entrada de blog [Mejoras de formato y análisis de punto flotante en .NET Core 3.0](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/), se sugieren cambios en el código si observa un cambio de comportamiento en comparación con las aplicaciones de .NET Core 2.2. Por lo general, esto implica el uso de una cadena de formato estándar o personalizado diferente para aplicar el comportamiento deseado. Es posible que algunos resultados no tengan una solución alternativa si anteriormente eran incorrectos.

#### <a name="category"></a>Categoría

Bibliotecas de Core .NET

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Double.ToString%2A?displayProperty=nameWithType>
- <xref:System.Single.ToString%2A?displayProperty=nameWithType>
- <xref:System.Double.Parse%2A?displayProperty=nameWithType>
- <xref:System.Double.TryParse%2A?displayProperty=nameWithType>
- <xref:System.Single.Parse%2A?displayProperty=nameWithType>
- <xref:System.Single.TryParse%2A?displayProperty=nameWithType>

<!-- 

### Affected APIs

- `Overload:System.Double.ToString`
- `Overload:System.Single.ToString`
- `Overload:System.Double.Parse`
- `Overload:System.Double.TryParse`
- `Overload:System.Single.Parse`
- `Overload:System.Single.TryParse`

-->
