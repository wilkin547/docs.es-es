---
title: 'Cómo: Cambiar el tamaño de filas con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
ms.openlocfilehash: 9bd7b073237fa995ac67fe23b616cd54980fbec9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554890"
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a>Cómo: Cambiar el tamaño de filas con un GridSplitter
Este ejemplo muestra cómo utilizar una horizontal <xref:System.Windows.Controls.GridSplitter> para redistribuir el espacio entre las dos filas de un <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de la <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Ejemplo  
 **Cómo crear un control GridSplitter que se superponga al borde de una fila**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de filas adyacentes en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Row%2A> propiedad adjunta a una de las filas que desee cambiar. Si su <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad adjunta para especificar el número de columnas. A continuación, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Top> o <xref:System.Windows.VerticalAlignment.Bottom> (la alineación que establezca depende en que dos filas que desea cambiar el tamaño). Por último, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad <xref:System.Windows.HorizontalAlignment.Stretch>.  
  
 En el ejemplo siguiente se muestra cómo definir una horizontal <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las filas adyacentes.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 A <xref:System.Windows.Controls.GridSplitter> que no ocupe su propia fila pueden estar ocultos por otros controles en la <xref:System.Windows.Controls.Grid>. Para más información sobre cómo evitar este problema, vea [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Cómo crear un control GridSplitter que ocupa una fila**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que ocupa una fila en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Row%2A> propiedad adjunta a una de las filas que desee cambiar. Si su <xref:System.Windows.Controls.Grid> tiene más de una columna, establezca la <xref:System.Windows.Controls.Grid.ColumnSpan%2A> propiedad adjunta en el número de columnas. A continuación, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Center>, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad a <xref:System.Windows.HorizontalAlignment.Stretch>y establezca el <xref:System.Windows.Controls.RowDefinition.Height%2A> de la fila que contiene el <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.  
  
 En el ejemplo siguiente se muestra cómo definir una horizontal <xref:System.Windows.Controls.GridSplitter> que ocupa una fila y cambia el tamaño de las filas en ambos lados de él.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridSplitter>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
