---
ms.openlocfilehash: 770e303ab261b97efb49a3e0865a015d8de33247
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2019
ms.locfileid: "67802670"
---
### <a name="improvements-to-grid-star-rows-space-allocating-algorithm"></a>Mejoras en el algoritmo de asignación de espacio en la cuadrícula de filas de estrella

|   |   |
|---|---|
|Detalles|Se ha corregido un error en el [algoritmo de asignación de los tamaños a ](https://github.com/Microsoft/dotnet/blob/master/Documentation/compatibility/wpf-grid-allocation-of-space-to-star-columns.md)) en un <xref:System.Windows.Controls.Grid> introducido en .NET Framework 4.7.  En algunos casos, como una cuadrícula con <code>Height=&quot;Auto&quot;</code> que contiene las filas vacías, las filas se han organizado en una posición incorrecta, posiblemente fuera de la cuadrícula.|
|Sugerencia|Para que la aplicación se beneficie de estos cambios, se debe ejecutar en .NET Framework 4.8 o una versión posterior.|
|Ámbito|Major|
|Versión|4.8|
|Tipo|Tiempo de ejecución|

