---
title: 'Cómo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 481d92d4301401f8ba87c4912cd44b17c5104b1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Cómo: Utilizar plantillas para aplicar un estilo a un control ListView que utiliza un modo GridView
Este ejemplo muestra cómo utilizar el <xref:System.Windows.DataTemplate> y <xref:System.Windows.Style> objetos que se va a especificar la apariencia de un <xref:System.Windows.Controls.ListView> control que usa un <xref:System.Windows.Controls.GridView> el modo de vista.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que personalizan la apariencia de un encabezado de columna para un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 En el ejemplo siguiente se muestra cómo usar estas <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que se va a establecer el <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> propiedades de un <xref:System.Windows.Controls.GridViewColumn>. El <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad define el contenido de las celdas de la columna.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 El <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> son sólo dos de varias propiedades que puede usar para personalizar la apariencia del encabezado de columna para un <xref:System.Windows.Controls.GridView> control. Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](../../../../docs/framework/wpf/controls/gridview-column-header-styles-and-templates-overview.md).  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.DataTemplate> que personaliza la apariencia de las celdas de un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 En el ejemplo siguiente se muestra cómo utilizar este <xref:System.Windows.DataTemplate> para definir el contenido de un <xref:System.Windows.Controls.GridViewColumn> celda. Esta plantilla se usa en lugar de la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad que se muestra en la versión anterior <xref:System.Windows.Controls.GridViewColumn> ejemplo.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
