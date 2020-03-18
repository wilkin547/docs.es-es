---
ms.openlocfilehash: 3a82822aae281ea7e873ba649f05b1d68686ec69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/15/2020
ms.locfileid: "70997719"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Desplazamiento de elementos de una lista plana con elementos con alto en píxeles diferente

|   |   |
|---|---|
|Detalles|Cuando un control <xref:System.Windows.Controls.ItemsControl?displayProperty=name> muestra una colección mediante la virtualización (<code>IsVirtualizing=true</code>) y el desplazamiento de elementos (<code>ScrollUnit=Item</code>), y cuando el control se desplaza para mostrar un elemento cuyo alto en píxeles difiere de sus vecinos, el <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=name> recorre en iteración todos los elementos de la colección. La UI no responde durante esta iteración; si la colección es grande, puede parecer un bloqueo. Esta iteración se produce en otras circunstancias, incluso en versiones anteriores de .NET Framework. Por ejemplo, se produce al desplazarse por píxeles (<code>ScrollUnit=Pixel</code>) al encontrar un elemento con otro alto en píxeles y, al desplazar por elementos datos jerárquicos (como en un control <xref:System.Windows.Controls.TreeView?displayProperty=name> o un <xref:System.Windows.Controls.ItemsControl?displayProperty=name> con la agrupación habilitada) al encontrar un elemento con un número de elementos descendientes distinto al de sus vecinos. Para el caso de desplazamiento por elementos y otra altura en píxeles, la iteración se introdujo en .NET Framework 4.6.1 para corregir errores en el diseño de los datos jerárquicos.  No es necesario si los datos son planos (sin jerarquía), en cuyo caso, .NET Framework 4.6.2 no realiza la iteración.|
|Sugerencia|Si la iteración se produce en .NET Framework 4.6.1, pero no en versiones anteriores (es decir, si <xref:System.Windows.Controls.ItemsControl?displayProperty=name> realiza el desplazamiento de elementos en una lista plana con elementos de diferentes alturas en píxeles), hay dos soluciones:<ol><li>Instalar .NET Framework 4.6.2.</li><li>Instalar la revisión HR 1605 para .NET Framework 4.6.1.</li></ol>|
|Ámbito|Secundaria|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType></li></ul>|
