---
title: 'Cómo: Crear un modo de vista personalizado para un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: b8600a2e201fdbcb566e6a322e3ecdabbe1641ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Cómo: Crear un modo de vista personalizado para un control ListView
Este ejemplo muestra cómo crear una personalizada <xref:System.Windows.Controls.ListView.View%2A> modo para un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Debe utilizar el <xref:System.Windows.Controls.ViewBase> clase cuando se crea una vista personalizada para el <xref:System.Windows.Controls.ListView> control. En el ejemplo siguiente se muestra un modo de vista que se llama `PlainView`, que se deriva de la <xref:System.Windows.Controls.ViewBase> clase.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Para aplicar un estilo a la vista personalizada, utilice la <xref:System.Windows.Style> clase. En el ejemplo siguiente se define un <xref:System.Windows.Style> para el `PlainView` el modo de vista. En el ejemplo anterior, este estilo se establece como el valor de la <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> propiedad que se define para `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Para definir el diseño de datos en un modo de vista personalizada, defina un <xref:System.Windows.DataTemplate> objeto. En el ejemplo siguiente se define un <xref:System.Windows.DataTemplate> que se puede utilizar para mostrar los datos en el `PlainView` modo de vista.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 En el ejemplo siguiente se muestra cómo definir un <xref:System.Windows.ResourceKey> para el `PlainView` modo de vista que usa el <xref:System.Windows.DataTemplate> que se define en el ejemplo anterior.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 A <xref:System.Windows.Controls.ListView> control puede usar una vista personalizada si establece la <xref:System.Windows.Controls.ListView.View%2A> propiedad a la clave de recurso. En el ejemplo siguiente se muestra cómo especificar `PlainView` como el modo de vista para un <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Para obtener un ejemplo completo, vea [ListView with Multiple Views Sample](http://go.microsoft.com/fwlink/?LinkID=160013).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
