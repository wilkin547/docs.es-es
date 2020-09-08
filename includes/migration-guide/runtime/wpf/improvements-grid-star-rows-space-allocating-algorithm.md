---
ms.openlocfilehash: 415eb1960c20fb662469e126560d6f366309eb0d
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89497301"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella

#### <a name="details"></a>Detalles

Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.  En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.

#### <a name="suggestion"></a>Sugerencia

Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

No detectable a través del análisis de la API.

<!--

#### Affected APIs

Not detectable via API analysis.

-->
