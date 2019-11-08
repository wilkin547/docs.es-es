---
title: 'Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: ce79899d5c8e825ecb39e14ae8af4e0c33f13db3
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733540"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
En este ejemplo se muestra cómo aplicar un estilo a una fila en un control <xref:System.Windows.Controls.ListView> que implementa un modo de <xref:System.Windows.Controls.ListView.View%2A> <xref:System.Windows.Controls.GridView>.  
  
## <a name="example"></a>Ejemplo  
 Puede aplicar un estilo a una fila en un control <xref:System.Windows.Controls.ListView> estableciendo un <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el control <xref:System.Windows.Controls.ListView>. Establezca el estilo de los elementos que se representan como objetos de <xref:System.Windows.Controls.ListViewItem>. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> hace referencia a los objetos <xref:System.Windows.Controls.ControlTemplate> que se usan para mostrar el contenido de la fila.  
  
 El ejemplo completo, del que se extraen los ejemplos siguientes, muestra una colección de información de la canción almacenada en una base de datos XML. Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para los objetos <xref:System.Windows.Controls.ListViewItem> que representan las canciones de la colección Song. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> hace referencia a <xref:System.Windows.Controls.ControlTemplate> objetos que especifican cómo mostrar una fila de información de la canción.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila. Se hace referencia a esta plantilla en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco). El <xref:System.Windows.Controls.ControlTemplate> incluye un objeto <xref:System.Windows.Controls.GridViewRowPresenter> que coloca el contenido de la fila en columnas tal y como se define en el modo de vista <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView>.  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Temas "Cómo..."](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
