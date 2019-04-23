---
title: Procedimiento Cambiar el tamaño de columnas con un GridSplitter
ms.date: 03/30/2017
helpviewer_keywords:
- grid columns [WPF], resizing
- GridSplitter control [WPF], resizing grid columns
- resizing grid columns [WPF]
ms.assetid: 47b20fe6-7adc-4aa6-9693-b4e184eef74b
ms.openlocfilehash: f743e9ccf8a984a646a4b8f05ee99162e5bc73ad
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59210443"
---
# <a name="how-to-resize-columns-with-a-gridsplitter"></a>Procedimiento Cambiar el tamaño de columnas con un GridSplitter
En este ejemplo se muestra cómo crear una vertical <xref:System.Windows.Controls.GridSplitter> para redistribuir el espacio entre las dos columnas de una <xref:System.Windows.Controls.Grid> sin cambiar las dimensiones de la <xref:System.Windows.Controls.Grid>.  
  
## <a name="example"></a>Ejemplo  
 **Cómo crear un control GridSplitter que se superponga al borde de una columna**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que cambia el tamaño de las columnas adyacentes en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta en una de las columnas que desea cambiar el tamaño. Si su <xref:System.Windows.Controls.Grid> tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas. A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> propiedad <xref:System.Windows.HorizontalAlignment.Left> o <xref:System.Windows.HorizontalAlignment.Right> (cuya alineación establecida depende de las dos columnas que desee cambiar el tamaño). Por último, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad <xref:System.Windows.VerticalAlignment.Stretch>.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterColumnOverlay](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplittercolumnoverlay)]  
  
 Un <xref:System.Windows.Controls.GridSplitter> que no tiene su propia columna puede estar ocultado por otros controles en el <xref:System.Windows.Controls.Grid>. Para más información sobre cómo evitar este problema, vea [Asegurarse de que un GridSplitter es visible](how-to-make-sure-that-a-gridsplitter-is-visible.md).  
  
 **Cómo crear un control GridSplitter que ocupa una columna**  
  
 Para especificar un <xref:System.Windows.Controls.GridSplitter> que ocupa una columna en un <xref:System.Windows.Controls.Grid>, establezca el <xref:System.Windows.Controls.Grid.Column%2A> propiedad adjunta en una de las columnas que desea cambiar el tamaño. Si la cuadrícula tiene más de una fila, establezca el <xref:System.Windows.Controls.Grid.RowSpan%2A> propiedad adjunta en el número de filas. A continuación, establezca el <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> a <xref:System.Windows.HorizontalAlignment.Center>, establezca el <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> propiedad a <xref:System.Windows.VerticalAlignment.Stretch>y establezca el <xref:System.Windows.Controls.ColumnDefinition.Width%2A> de la columna que contiene el <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.  
  
 El ejemplo siguiente muestra cómo definir una vertical <xref:System.Windows.Controls.GridSplitter> que ocupa una columna y cambia el tamaño de las columnas en cada lado del mismo.  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireColumnPart2](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirecolumnpart2)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.GridSplitter>
- [Temas "Cómo..."](gridsplitter-how-to-topics.md)
