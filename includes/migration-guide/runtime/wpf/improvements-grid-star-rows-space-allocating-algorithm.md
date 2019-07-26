---
ms.openlocfilehash: 8e0c934cd8c3cb8c08a526c7e145436db6ecf4a5
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237612"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella

|   |   |
|---|---|
|Detalles|Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.  En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.|
|Sugerencia|Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.|
|Ámbito|Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|
