---
ms.openlocfilehash: d23d7821e19b9d7f2db13a6bfdf868a8414cf721
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2020
ms.locfileid: "89496906"
---
### <a name="item-scrolling-a-flat-list-with-items-of-different-pixel-height"></a>Desplazamiento de elementos de una lista plana con elementos con alto en píxeles diferente

#### <a name="details"></a>Detalles

Cuando un control <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> muestra una colección mediante la virtualización (<code>IsVirtualizing=true</code>) y el desplazamiento de elementos (<code>ScrollUnit=Item</code>), y cuando el control se desplaza para mostrar un elemento cuyo alto en píxeles difiere de sus vecinos, el <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> recorre en iteración todos los elementos de la colección. La UI no responde durante esta iteración; si la colección es grande, puede parecer un bloqueo. Esta iteración se produce en otras circunstancias, incluso en versiones anteriores de .NET Framework. Por ejemplo, se produce al desplazarse por píxeles (<code>ScrollUnit=Pixel</code>) al encontrar un elemento con otro alto en píxeles y, al desplazar por elementos datos jerárquicos (como en un control <xref:System.Windows.Controls.TreeView?displayProperty=fullName> o un <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> con la agrupación habilitada) al encontrar un elemento con un número de elementos descendientes distinto al de sus vecinos. Para el caso de desplazamiento por elementos y otra altura en píxeles, la iteración se introdujo en .NET Framework 4.6.1 para corregir errores en el diseño de los datos jerárquicos.  No es necesario si los datos son planos (sin jerarquía), en cuyo caso, .NET Framework 4.6.2 no realiza la iteración.

#### <a name="suggestion"></a>Sugerencia

Si la iteración se produce en .NET Framework 4.6.1, pero no en versiones anteriores (es decir, si <xref:System.Windows.Controls.ItemsControl?displayProperty=fullName> realiza el desplazamiento de elementos en una lista plana con elementos de diferentes alturas en píxeles), hay dos soluciones:<ol><li>Instalar .NET Framework 4.6.2.</li><li>Instalar la revisión HR 1605 para .NET Framework 4.6.1.</li></ol>

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.6.1|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=nameWithType>

<!--

#### Affected APIs

- `T:System.Windows.Controls.VirtualizingStackPanel`

-->
