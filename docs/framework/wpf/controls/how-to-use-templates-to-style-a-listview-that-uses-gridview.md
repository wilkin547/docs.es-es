---
title: Procedimiento Usar plantillas para aplicar un estilo a un control ListView que usa un modo GridView
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 94bf964b-96c8-4bdf-a0c3-f5271b7cb565
ms.openlocfilehash: 1caa652c4a2a3a7d0a8d40fe703df7a3e8038c9b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61699128"
---
# <a name="how-to-use-templates-to-style-a-listview-that-uses-gridview"></a>Procedimiento Usar plantillas para aplicar un estilo a un control ListView que usa un modo GridView
En este ejemplo se muestra cómo usar el <xref:System.Windows.DataTemplate> y <xref:System.Windows.Style> objetos que se va a especificar la apariencia de un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView> modo de vista.  
  
## <a name="example"></a>Ejemplo  
 Los ejemplos siguientes muestran <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que personalización la apariencia de un encabezado de columna para un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheaderstyle)]  
  
 [!code-xaml[ListViewTemplate#GridViewHeaderTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewheadertemplate)]  
  
 El ejemplo siguiente muestra cómo usar estas <xref:System.Windows.Style> y <xref:System.Windows.DataTemplate> objetos que se va a establecer el <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> las propiedades de un <xref:System.Windows.Controls.GridViewColumn>. El <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad define el contenido de las celdas de columna.  
  
 [!code-xaml[ListViewTemplate#GridViewColumnTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcolumntemplate)]  
  
 El <xref:System.Windows.Controls.GridViewColumn.HeaderContainerStyle%2A> y <xref:System.Windows.Controls.GridViewColumn.HeaderTemplate%2A> son sólo dos de varias propiedades que puede usar para personalizar la apariencia del encabezado de columna para un <xref:System.Windows.Controls.GridView> control. Para más información, consulte [Información general sobre plantillas y estilos de encabezado de columna en modo GridView](gridview-column-header-styles-and-templates-overview.md).  
  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.DataTemplate> que personaliza la apariencia de las celdas de un <xref:System.Windows.Controls.GridViewColumn>.  
  
 [!code-xaml[ListViewTemplate#GridViewCellTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#gridviewcelltemplate)]  
  
 El ejemplo siguiente muestra cómo utilizar este <xref:System.Windows.DataTemplate> para definir el contenido de un <xref:System.Windows.Controls.GridViewColumn> celda. Esta plantilla se usa en lugar de la <xref:System.Windows.Controls.GridViewColumn.DisplayMemberBinding%2A> propiedad que se muestra en la anterior <xref:System.Windows.Controls.GridViewColumn> ejemplo.  
  
 [!code-xaml[ListViewTemplate#CellTemplateProperty](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewTemplate/CS/window1.xaml#celltemplateproperty)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Información general sobre GridView](gridview-overview.md)
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
