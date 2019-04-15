---
ms.openlocfilehash: 0887379fb23e9e66c6cc55a3774545162634c3f0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236705"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Desplazar una instancia de TreeView o ListBox agrupada de WPF en un elemento VirtualizingStackPanel puede hacer que el programa no responda

|   |   |
|---|---|
|Detalles|En .NET Framework 4.5, desplazar un elemento <xref:System.Windows.Controls.TreeView?displayProperty=name> de WPF en un panel StackPanel virtualizado puede hacer que el programa no responda si hay márgenes en la ventanilla (entre los elementos de <xref:System.Windows.Controls.TreeView?displayProperty=name>, por ejemplo, o en algún elemento ItemsPresenter). Además, en algunos casos, los elementos de diferentes tamaños de la vista pueden originar inestabilidad aun cuando no haya márgenes.|
|Sugerencia|Este error puede evitarse actualizando a .NET Framework 4.5.1. Como alternativa, se pueden eliminar los márgenes de las colecciones de vista (como las instancias de <xref:System.Windows.Controls.TreeView?displayProperty=name>) dentro de los paneles StackPanel virtualizados si todos los elementos contenidos son del mismo tamaño.|
|Ámbito|Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
|API afectadas|<ul><li><xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
