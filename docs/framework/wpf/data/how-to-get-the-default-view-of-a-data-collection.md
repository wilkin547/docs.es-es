---
title: "Cómo: Obtener la vista predeterminada de una recolección de datos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], creating views of
- data binding [WPF], creating views of data collections
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 86d1ababcb7a00496b59005b5e90f875511fefc4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-the-default-view-of-a-data-collection"></a>Cómo: Obtener la vista predeterminada de una recolección de datos
Las vistas permiten la misma colección de datos a verse de varias maneras, dependiendo de ordenación, filtrado o criterio de agrupación. Cada colección tiene una vista predeterminada compartida, que se usa como origen de enlace real cuando un enlace especifica una colección como origen. En este ejemplo se muestra cómo obtener la vista predeterminada de una colección.  
  
## <a name="example"></a>Ejemplo  
 Para crear la vista, se necesita una referencia de objeto a la colección. Este objeto de datos puede obtenerse mediante una referencia a su propio objeto de código subyacente, obteniendo el contexto de datos, obtener una propiedad del origen de datos, o bien obtener una propiedad del enlace. Este ejemplo muestra cómo obtener el <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y uso para obtener directamente de la colección predeterminada ver para esta colección.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 En este ejemplo, el elemento raíz es un <xref:System.Windows.Controls.StackPanel>. El <xref:System.Windows.FrameworkElement.DataContext%2A> está establecido en *myDataSource*, que hace referencia a un proveedor de datos que es un <xref:System.Collections.ObjectModel.ObservableCollection%601> de *orden* objetos.  
  
 [!code-xaml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Como alternativa, puede crear una instancia y enlazar a su propia vista de colección mediante la <xref:System.Windows.Data.CollectionViewSource> clase. Esta vista de colección solo se comparte entre los controles que enlazan directamente a él. Para obtener un ejemplo, vea cómo crear una sección de vista en el [información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, consulte [ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md), y [navegar a través de objetos en un CollectionView datos](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## <a name="see-also"></a>Vea también  
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
