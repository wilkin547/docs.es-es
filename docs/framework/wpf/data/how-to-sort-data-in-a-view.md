---
title: Procedimiento Ordenar datos en una vista
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], sorting data in views
- data binding [WPF], grouping data in views
- grouping data in views [WPF]
- views [WPF], sorting data
- views [WPF], grouping data
- sorting data in views [WPF]
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
ms.openlocfilehash: 50e1426f2a220c7d947f7feb9c3ec7e1c4de7643
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522679"
---
# <a name="how-to-sort-data-in-a-view"></a>Procedimiento Ordenar datos en una vista
En este ejemplo se describe cómo ordenar datos en una vista.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea una sencilla <xref:System.Windows.Controls.ListBox> y un <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 El <xref:System.Windows.Controls.Primitives.ButtonBase.Click> controlador de eventos del botón contiene lógica para ordenar los elementos de la <xref:System.Windows.Controls.ListBox> en orden descendente. Puede hacerlo porque agregar elementos a un <xref:System.Windows.Controls.ListBox> esta forma agregarán a la <xref:System.Windows.Controls.ItemCollection> de la <xref:System.Windows.Controls.ListBox>, y <xref:System.Windows.Controls.ItemCollection> deriva la <xref:System.Windows.Data.CollectionView> clase. Si va a enlazar sus <xref:System.Windows.Controls.ListBox> a una colección mediante el <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> propiedad, puede usar la misma técnica para ordenar.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Siempre que tenga una referencia al objeto view, puede usar la misma técnica para ordenar el contenido de otras vistas de colección. Para obtener un ejemplo de cómo obtener una vista, consulte [obtener la vista predeterminada de una colección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md). Para obtener otro ejemplo, vea [ordenar un GridView columna cuando un encabezado se hace clic en](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Para obtener más información acerca de las vistas, vea el enlace a colecciones en [Data Binding Overview](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Para obtener un ejemplo de cómo aplicar la lógica de ordenación en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], consulte [ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Ordenar una columna de GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
