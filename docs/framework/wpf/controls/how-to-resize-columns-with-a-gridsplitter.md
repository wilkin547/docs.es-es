---
title: 'Cómo: Cambiar el tamaño de columnas con un GridSplitter'
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: b4652c06cfe6f048f6c75a11b9447d70d6820e4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33556155"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Cómo: Cambiar el tamaño de columnas con un GridSplitter
Este ejemplo muestra cómo crear una vertical <xref:System.Windows.Controls.GridSplitter> para redistribuir el espacio entre las dos columnas de una <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de la <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Ejemplo  
 **Cómo crear un control GridSplitter que se superponga al borde de una columna**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las columnas adyacentes en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta a una de las columnas que desee cambiar. Si su <xref:System.Windows.Controls.Grid> tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas. A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (la alineación establezca dependerá en las dos columnas que desea cambiar el tamaño). Por último, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 A <xref:System.Windows.Controls.GridSplitter> que no tiene su propia columna pueden estar ocultos por otros controles en la <xref:System.Windows.Controls.Grid>. Para más información sobre cómo evitar este problema, vea [Asegurarse de que un GridSplitter es visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Cómo crear un control GridSplitter que ocupa una columna**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que ocupa una columna en una <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta a una de las columnas que desee cambiar. Si la cuadrícula tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas. A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> a <xref:System.Windows.HorizontalAlignment.Center>, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad a <xref:System.Windows.VerticalAlignment.Stretch>y establezca el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de la columna que contiene el <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.  
  
 En el ejemplo siguiente se muestra cómo definir una vertical <xref:System.Windows.Controls.GridSplitter> que ocupa una columna y cambia el tamaño de las columnas en cada lado del mismo.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.GridSplitter>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
