---
title: 'Cómo: Obtener la vista predeterminada de una recolección de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
ms.openlocfilehash: e82d252ed82e4d2e6d641e8b60e890cc93bb0427
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459117"
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Cómo: Obtener la vista predeterminada de una recolección de datos
Las vistas permiten ver la misma recopilación de datos de maneras diferentes, en función de los criterios de ordenación, filtrado o agrupación. Cada colección tiene una vista predeterminada compartida, que se utiliza como el origen de Enlace real cuando un enlace especifica una colección como su origen. En este ejemplo se muestra cómo obtener la vista predeterminada de una colección.  
  
## <a name="example"></a>Ejemplo  
 Para crear la vista, necesita una referencia de objeto a la colección. Este objeto de datos se puede obtener haciendo referencia a su propio objeto de código subyacente, obteniendo el contexto de datos, obteniendo una propiedad del origen de datos o obteniendo una propiedad del enlace. En este ejemplo se muestra cómo obtener el <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y cómo utilizarlo para obtener directamente la vista de colección predeterminada de esta colección.  
  
 [!code-csharp[CollectionView#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 En este ejemplo, el elemento raíz es un <xref:System.Windows.Controls.StackPanel>. La <xref:System.Windows.FrameworkElement.DataContext%2A> se establece en mi *DataSource*, que hace referencia a un proveedor de datos que es una <xref:System.Collections.ObjectModel.ObservableCollection%601> de objetos de *pedido* .  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Como alternativa, puede crear una instancia de y enlazar a su propia vista de colección mediante la <xref:System.Windows.Data.CollectionViewSource> clase. Esta vista de colección solo la comparten los controles que se enlazan a ella directamente. Para obtener un ejemplo, vea la sección Cómo crear una vista en [información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md).  
  
 Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, vea [ordenar datos en una vista](how-to-sort-data-in-a-view.md), [filtrar datos en una vista](how-to-filter-data-in-a-view.md)y [navegar por los objetos de una colección de datos](how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vea también

- [Ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
