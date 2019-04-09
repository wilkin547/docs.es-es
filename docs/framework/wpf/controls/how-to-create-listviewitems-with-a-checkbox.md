---
title: Filtrar Crear controles ListViewItems con un control CheckBox
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], ListView
- controls [WPF], CheckBox
- ListView controls [WPF], CheckBox controls
- CheckBox control [WPF], ListView control
ms.assetid: f6d66c7f-906c-4f65-a55a-0ede9d00e26a
ms.openlocfilehash: b09d5ad11b0961febf524cec1e19cb1e59832e44
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083112"
---
# <a name="how-to-create-listviewitems-with-a-checkbox"></a>Filtrar Crear controles ListViewItems con un control CheckBox
En este ejemplo se muestra cómo mostrar una columna de <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Ejemplo  
 Para crear una columna que contiene <xref:System.Windows.Controls.CheckBox> controles en un <xref:System.Windows.Controls.ListView>, cree un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>. A continuación, establezca el <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> de un <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.  
  
 El ejemplo siguiente se muestra un <xref:System.Windows.DataTemplate> que contiene un <xref:System.Windows.Controls.CheckBox>. El ejemplo se enlaza el <xref:System.Windows.Controls.Primitives.ToggleButton.IsChecked%2A> propiedad de la <xref:System.Windows.Controls.CheckBox> a la <xref:System.Windows.Controls.ListBoxItem.IsSelected%2A> valor de propiedad de la <xref:System.Windows.Controls.ListViewItem> que lo contiene. Por lo tanto, cuando el <xref:System.Windows.Controls.ListViewItem> que contiene el <xref:System.Windows.Controls.CheckBox> está activada, el <xref:System.Windows.Controls.CheckBox> está activada.  
  
 [!code-xaml[ListViewChkBox#CheckBoxDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#checkboxdatatemplate)]  
  
 El ejemplo siguiente muestra cómo crear una columna de <xref:System.Windows.Controls.CheckBox> controles. Convertir la columna, el ejemplo establece la <xref:System.Windows.Controls.GridViewColumn.CellTemplate%2A> propiedad de la <xref:System.Windows.Controls.GridViewColumn> a la <xref:System.Windows.DataTemplate>.  
  
 [!code-xaml[ListViewChkBox#GridViewColumnCheckBox](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#gridviewcolumncheckbox)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Información general sobre ListView](listview-overview.md)
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre GridView](gridview-overview.md)
