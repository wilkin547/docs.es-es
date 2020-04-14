---
title: 'Cómo: Crear un modo de vista personalizado para un control ListView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], creating custom View mode
ms.assetid: 71077349-eeb9-4344-ab29-b5df96df3314
ms.openlocfilehash: 3b9ca17bddcecb1895205fca76f0a489ecf25c4f
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2020
ms.locfileid: "81243224"
---
# <a name="how-to-create-a-custom-view-mode-for-a-listview"></a>Cómo: Crear un modo de vista personalizado para un ListView

En este ejemplo se <xref:System.Windows.Controls.ListView.View%2A> muestra cómo <xref:System.Windows.Controls.ListView> crear un modo personalizado para un control.  
  
## <a name="example"></a>Ejemplo  
 Debe usar <xref:System.Windows.Controls.ViewBase> la clase al crear una <xref:System.Windows.Controls.ListView> vista personalizada para el control. En el ejemplo siguiente `PlainView` se muestra un modo <xref:System.Windows.Controls.ViewBase> de vista denominado que se deriva de la clase.  
  
 [!code-csharp[ListViewCustomView#PlainView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/PlainView.cs#plainview)]
 [!code-vb[ListViewCustomView#PlainView](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/plainview.vb#plainview)]  
  
 Para aplicar un estilo a la <xref:System.Windows.Style> vista personalizada, utilice la clase. En el ejemplo <xref:System.Windows.Style> siguiente `PlainView` se define un para el modo de vista. En el ejemplo anterior, este estilo se <xref:System.Windows.Controls.ViewBase.DefaultStyleKey%2A> establece como el `PlainView`valor de la propiedad definida para .  
  
 [!code-xaml[ListViewCustomView#PlainViewStyle](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Themes/Generic.xaml#plainviewstyle)]  
  
 Para definir el diseño de datos en <xref:System.Windows.DataTemplate> un modo de vista personalizado, defina un objeto. En el ejemplo <xref:System.Windows.DataTemplate> siguiente se define un `PlainView` que se puede utilizar para mostrar datos en el modo de vista.  
  
 [!code-xaml[ListViewCustomView#PlainViewDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewdatatemplate)]  
  
 En el ejemplo siguiente <xref:System.Windows.ResourceKey> se `PlainView` muestra cómo definir <xref:System.Windows.DataTemplate> un para el modo de vista que utiliza el que se define en el ejemplo anterior.  
  
 [!code-xaml[ListViewCustomView#PlainViewtileView](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml#plainviewtileview)]  
  
 Un <xref:System.Windows.Controls.ListView> control puede usar una vista <xref:System.Windows.Controls.ListView.View%2A> personalizada si establece la propiedad en la clave de recurso. En el ejemplo siguiente `PlainView` se muestra cómo <xref:System.Windows.Controls.ListView>especificar como modo de vista para un archivo .  
  
 [!code-csharp[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp/Window1.xaml.cs#listviewtileviewmode)]
 [!code-vb[ListViewCustomView#ListViewtileViewmode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic/window1.xaml.vb#listviewtileviewmode)]  
  
 Para obtener el ejemplo completo, vea [ListView con varias vistas (C)](https://github.com/dotnet/docs/tree/master/samples/snippets/csharp/VS_Snippets_Wpf/ListViewCustomView/CSharp) o [ListView con varias vistas (Visual Basic).](https://github.com/dotnet/docs/tree/master/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewCustomView/visualbasic)  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Temas de procedimientos](listview-how-to-topics.md)
- [Información general sobre ListView](listview-overview.md)
- [Información general sobre GridView](gridview-overview.md)
