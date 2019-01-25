---
title: Procedimiento Navegar por los objetos de una colección de datos mediante CollectionView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: c7de491a76ba6f8d5164c91f8c20bea4a8fa56d7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688407"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Procedimiento Navegar por los objetos de una colección de datos mediante CollectionView
Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de ordenar, filtrar o agrupar. Las vistas también proporcionan un concepto de puntero de registro actual y permiten mover el puntero. En este ejemplo se muestra cómo obtener el objeto actual, así como navegar por los objetos en una recopilación de datos mediante la funcionalidad proporcionada en el <xref:System.Windows.Data.CollectionView> clase.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `myCollectionView` es un <xref:System.Windows.Data.CollectionView> objeto que es una vista a través de una colección enlazada.  
  
 En el ejemplo siguiente, `OnButton` es un controlador de eventos para el `Previous` y `Next` botones en una aplicación, que son los botones que permiten al usuario navegar por la recopilación de datos. Tenga en cuenta que el <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> propiedades de informes si el puntero de registro actual ha llegado al comienzo y final de la lista respectivamente hasta que <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> pueden llamarse como corresponda.  
  
 El <xref:System.Windows.Data.CollectionView.CurrentItem%2A> propiedad de la vista se convierte como un `Order` para devolver el elemento de orden actual de la colección.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)
- [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
