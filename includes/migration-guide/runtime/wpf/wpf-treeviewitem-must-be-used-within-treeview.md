---
ms.openlocfilehash: af8cb9435be078351e3430dc8ded3f7cac377948
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620722"
---
### <a name="wpf-treeviewitem-must-be-used-within-a-treeview"></a>El elemento TreeViewItem de WPF se debe usar dentro de una instancia de TreeView

#### <a name="details"></a>Detalles

En la versión 4.5 se introdujo un cambio que restringe el uso de elementos <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> fuera de una instancia de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>. Se manifiesta en las siguientes condiciones:<ul><li>Cuando el elemento primario del objeto visual de <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> no es un panel. (Un elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> generado para una instancia de <xref:System.Windows.Controls.TreeView?displayProperty=fullName> tendrá un panel como su elemento primario).</li><li>Cuando el elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> es un descendiente de una instancia de <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> que actúa como &quot;host de elementos&quot; para un control de lista (ListBox, DataGrid, ListView, etc.). No es necesario que la virtualización esté activada.</li><li>El panel <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> se desplaza por elementos (<code>ScrollUnit=&quot;Item&quot;</code>).</li><li>Alguien llama a <code>VirtualizingStackPanel.MakeVisible(v)</code> para desplazar un elemento <code>v</code> a la vista. Puede hacerse de forma explícita, o bien implícita de diferentes formas; tal vez la más habitual sea simplemente hacer clic en <code>v</code> para asignarle el foco del teclado.</li><li>La cadena del elemento primario del objeto visual desde <code>v</code> a <xref:System.Windows.Controls.VirtualizingStackPanel?displayProperty=fullName> pasa a través del elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName>.</li></ul>En otras palabras, esto se observa cuando se usa un elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> fuera de una instancia de <xref:System.Windows.Controls.TreeView?displayProperty=fullName> y el usuario hace clic en un descendiente del elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> para mostrarlo en la vista. Si el elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> no tiene ningún descendiente activable, nunca observará este problema. Un ejemplo de situación en la que se produce este problema es cuando el elemento <xref:System.Windows.Controls.TreeViewItem?displayProperty=fullName> es la raíz de una instancia de DataTemplate. Cuando se produce este problema, se genera una instancia InvalidCastException dentro del marco de WPF.

#### <a name="suggestion"></a>Sugerencia

Se lanzará una revisión para esta solucionar esta situación.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
