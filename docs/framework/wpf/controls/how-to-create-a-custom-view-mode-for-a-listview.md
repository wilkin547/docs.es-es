---
title: Procedimiento Crear un modo de vista personalizado para un control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: d39f8829e7bdc89c05cda0f586298518908683f5
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613029"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Procedimiento Crear un modo de vista personalizado para un control ListView
En este ejemplo se muestra cómo crear una personalizada <xref:System.Windows.Controls.ListView.View%2A> modo para un <xref:System.Windows.Controls.ListView> control.  
  
## <a name="example"></a>Ejemplo  
 Debe usar el <xref:System.Windows.Controls.ViewBase> clase cuando se crea una vista personalizada para el <xref:System.Windows.Controls.ListView> control. El ejemplo siguiente muestra un modo de vista que se llama `PlainView`, que se deriva el <xref:System.Windows.Controls.ViewBase> clase.  
  
 [!code-csharp[ListViewCustomView#PlainView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Para aplicar un estilo a la vista personalizada, use la <xref:System.Windows.Style> clase. En el ejemplo siguiente se define un <xref:System.Windows.Style> para el `PlainView` modo de vista. En el ejemplo anterior, este estilo se establece como valor de la <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> propiedad que se define para `PlainView`.  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Para definir el diseño de datos en un modo de vista personalizada, defina un <xref:System.Windows.DataTemplate> objeto. En el ejemplo siguiente se define un <xref:System.Windows.DataTemplate> que puede utilizarse para mostrar datos en el `PlainView` modo de vista.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 El ejemplo siguiente muestra cómo definir un <xref:System.Windows.ResourceKey> para el `PlainView` modo de vista que usa el <xref:System.Windows.DataTemplate> que se define en el ejemplo anterior.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Un <xref:System.Windows.Controls.ListView> control puede usar una vista personalizada si establece la <xref:System.Windows.Controls.ListView.View%2A> propiedad a la clave de recurso. El ejemplo siguiente muestra cómo especificar `PlainView` como el modo de vista para un <xref:System.Windows.Controls.ListView>.  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Para obtener un ejemplo completo, vea [ListView con varias vistas (C#)](https://github.com/dotnet/samples/tree/master/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con varias Views(Visual Basic)](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Información general sobre ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Información general sobre GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
