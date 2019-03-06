---
title: Procedimiento Obtener la vista predeterminada de una recolección de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: 28a21aae7f8a08efebfd16bacd2a2d82b04de0c1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360074"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Filtrar Obtener la vista predeterminada de una recolección de datos
Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de la ordenación, filtrado o criterio de agrupación. Cada colección tiene una vista compartida de forma predeterminada, que se usa como origen de enlace real cuando un enlace especifica una colección como origen. En este ejemplo se muestra cómo obtener la vista predeterminada de una colección.  
  
## <a name="example"></a>Ejemplo  
 Para crear la vista, necesita una referencia de objeto a la colección. Este objeto de datos puede obtenerse haciendo referencia a su propio objeto de código subyacente, obteniendo el contexto de datos, obteniendo una propiedad del origen de datos, u obteniendo una propiedad del enlace. En este ejemplo se muestra cómo obtener el <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y uso para obtener directamente la colección predeterminada ver de esta colección.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 En este ejemplo, el elemento raíz es un <xref:System.Windows.Controls.StackPanel>. El <xref:System.Windows.FrameworkElement.DataContext%2A> está establecido en *myDataSource*, que hace referencia a un proveedor de datos que es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de *orden* objetos.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Como alternativa, puede crear instancias y enlazar a su propia vista de colección mediante el <xref:System.Windows.Data.CollectionViewSource> clase. Esta vista de colección solo se comparte entre los controles que se enlazan directamente a él. Para obtener un ejemplo, vea cómo crear una sección de vista en el [Data Binding Overview](data-binding-overview.md).  
  
 Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, consulte [ordenar datos en una vista](how-to-sort-data-in-a-view.md), [filtrar los datos en una vista](how-to-filter-data-in-a-view.md), y [navegar por los objetos de una colección de datos mediante CollectionView](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vea también
- [Ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
