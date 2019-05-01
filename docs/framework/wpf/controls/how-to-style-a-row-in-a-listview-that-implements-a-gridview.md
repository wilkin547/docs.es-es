---
title: Procedimiento Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 9af8d10c7db2d3bbe8b9443402cbb1cfeaa7edb3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052019"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Procedimiento Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
En este ejemplo se muestra cómo aplicar un estilo una fila en un <xref:System.Windows.Controls.ListView> control que implementa un <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modo.  
  
## <a name="example"></a>Ejemplo  
 Puedes aplicar estilo a una fila en un <xref:System.Windows.Controls.ListView> control estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control. Establecer el estilo de sus elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias el <xref:System.Windows.Controls.ControlTemplate> objetos que se usan para mostrar el contenido de la fila.  
  
 En el ejemplo completo, del cual se extraen los siguientes, se muestra una colección de información de la canción que se almacena en una base de datos [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)]. Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.  
  
 El ejemplo siguiente muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para el <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección de canciones. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> referencias <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 El ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila. Esta plantilla se hace referencia en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco). El <xref:System.Windows.Controls.ControlTemplate> incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que distribuye el contenido de la fila en columnas tal como se define por el <xref:System.Windows.Controls.GridView> modo de vista.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Aplicar estilos y plantillas](styling-and-templating.md)
