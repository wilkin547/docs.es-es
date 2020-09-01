---
title: 'Cómo: aplicar un estilo a una fila en un control ListView que usa GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- GridView controls [WPF], styling rows
- styling rows in ListViews implementing GridViews [WPF]
- ListView controls [WPF], styling rows with GridViews
ms.assetid: 2e406ba2-70a0-4e62-841f-0934859de76e
ms.openlocfilehash: 4b8b8e2f1b2d7207a37205d981bf2dab3f65122e
ms.sourcegitcommit: e0803b8975d3eb12e735a5d07637020dd6dac5ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2020
ms.locfileid: "89271950"
---
# <a name="how-to-style-a-row-in-a-listview-that-implements-a-gridview"></a>Cómo: Aplicar un estilo a una fila en un control ListView que implementa una clase GridView
En este ejemplo se muestra cómo aplicar un estilo a una fila en un <xref:System.Windows.Controls.ListView> control que utiliza un <xref:System.Windows.Controls.GridView> <xref:System.Windows.Controls.ListView.View%2A> modo.  
  
## <a name="example"></a>Ejemplo  
 Puede aplicar un estilo a una fila de un <xref:System.Windows.Controls.ListView> control estableciendo <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> en el <xref:System.Windows.Controls.ListView> control. Establezca el estilo de los elementos que se representan como <xref:System.Windows.Controls.ListViewItem> objetos. El <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> objeto hace referencia <xref:System.Windows.Controls.ControlTemplate> a los objetos que se usan para mostrar el contenido de la fila.  
  
 El ejemplo completo, del que se extraen los ejemplos siguientes, muestra una colección de información de la canción almacenada en una base de datos XML. Cada canción de la base de datos tiene un campo de clasificación y el valor de este campo especifica cómo mostrar una fila de información de la canción.  
  
 En el ejemplo siguiente se muestra cómo definir <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> para los <xref:System.Windows.Controls.ListViewItem> objetos que representan las canciones de la colección Song. <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A>Objetos de referencia <xref:System.Windows.Controls.ControlTemplate> que especifican cómo mostrar una fila de información de la canción.  
  
 [!code-xaml[ListViewItemStyleSnippet#ItemContainerStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#itemcontainerstyle)]  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.ControlTemplate> que agrega la cadena de texto `"Strongly Recommended"` a la fila. Se hace referencia a esta plantilla en el <xref:System.Windows.Controls.ItemsControl.ItemContainerStyle%2A> y se muestra cuando la clasificación de la canción tiene un valor de 5 (cinco). <xref:System.Windows.Controls.ControlTemplate>Incluye un <xref:System.Windows.Controls.GridViewRowPresenter> objeto que coloca el contenido de la fila en columnas tal y como se define en el <xref:System.Windows.Controls.GridView> modo de vista.  
  
 [!code-xaml[ListViewItemStyleSnippet#ControlTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#controltemplate)]  
  
 En el ejemplo siguiente se define <xref:System.Windows.Controls.GridView> .  
  
 [!code-xaml[ListViewItemStyleSnippet#GridView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewItemStyleSnippet/CS/Window1.xaml#gridview)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Temas de procedimientos](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Aplicar estilos y plantillas](../../../desktop-wpf/fundamentals/styles-templates-overview.md)
