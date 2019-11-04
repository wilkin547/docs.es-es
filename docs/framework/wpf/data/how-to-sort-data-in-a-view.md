---
title: 'Cómo: Ordenar datos en una vista'
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
ms.openlocfilehash: 14314ed019f9194a657787bd767ae68615e94ac7
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454830"
---
# <a name="how-to-sort-data-in-a-view"></a>Cómo: Ordenar datos en una vista
En este ejemplo se describe cómo ordenar los datos en una vista.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> simple y un <xref:System.Windows.Controls.Button>:  
  
 [!code-xaml[ListBoxSort_snip#HowTo](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón contiene la lógica para ordenar los elementos del <xref:System.Windows.Controls.ListBox> en orden descendente. Puede hacerlo porque agregar elementos a un <xref:System.Windows.Controls.ListBox> de esta manera los agrega al <xref:System.Windows.Controls.ItemCollection> de la <xref:System.Windows.Controls.ListBox>y <xref:System.Windows.Controls.ItemCollection> deriva de la clase <xref:System.Windows.Data.CollectionView>. Si va a enlazar el <xref:System.Windows.Controls.ListBox> a una colección mediante la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, puede usar la misma técnica para ordenar.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Siempre que tenga una referencia al objeto de vista, puede usar la misma técnica para ordenar el contenido de otras vistas de colección. Para obtener un ejemplo de cómo obtener una vista, vea [obtener la vista predeterminada de una recolección de datos](how-to-get-the-default-view-of-a-data-collection.md). Para ver otro ejemplo, vea [ordenar una columna de GridView cuando se hace clic en un encabezado](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md). Para obtener más información sobre las vistas, vea enlazar a colecciones en [información general](../../../desktop-wpf/data/data-binding-overview.md)sobre el enlace de datos.  
  
 Para obtener un ejemplo de cómo aplicar la lógica de ordenación en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], vea [ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>
- [Ordenar una columna de GridView cuando se hace clic en un encabezado](../controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Filtrar datos en una vista](how-to-filter-data-in-a-view.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
