---
ms.openlocfilehash: 1be68c2968d0eaa9024007bcf37abf9e44c36f1c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622151"
---
### <a name="scrolling-a-wpf-treeview-or-grouped-listbox-in-a-virtualizingstackpanel-can-cause-a-hang"></a>Desplazar una instancia de TreeView o ListBox agrupada de WPF en un elemento VirtualizingStackPanel puede hacer que el programa no responda

#### <a name="details"></a>Detalles

En .NET Framework 4.5, desplazar un elemento <xref:System.Windows.Controls.TreeView?displayProperty=fullName> de WPF en un panel StackPanel virtualizado puede hacer que el programa no responda si hay márgenes en la ventanilla (entre los elementos de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>, por ejemplo, o en algún elemento ItemsPresenter). Además, en algunos casos, los elementos de diferentes tamaños de la vista pueden originar inestabilidad aun cuando no haya márgenes.

#### <a name="suggestion"></a>Sugerencia

Este error puede evitarse actualizando a .NET Framework 4.5.1. Como alternativa, se pueden eliminar los márgenes de las colecciones de vista (como las instancias de <xref:System.Windows.Controls.TreeView?displayProperty=fullName>) dentro de los paneles StackPanel virtualizados si todos los elementos contenidos son del mismo tamaño.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Major|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Windows.Controls.VirtualizingStackPanel.SetIsVirtualizing(System.Windows.DependencyObject,System.Boolean)?displayProperty=nameWithType></li></ul>|
