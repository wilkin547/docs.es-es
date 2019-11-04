---
title: 'Cómo: Navegar por los objetos de una colección de datos mediante CollectionView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
ms.openlocfilehash: 5ca386db89dcaa66d364d2ed7169c67393cebead
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459707"
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Cómo: Navegar por los objetos de una colección de datos mediante CollectionView
Las vistas permiten ver la misma recopilación de datos de maneras diferentes, en función de la ordenación, el filtrado o la agrupación. Las vistas también proporcionan un concepto de puntero de registro actual y permiten mover el puntero. En este ejemplo se muestra cómo obtener el objeto actual y cómo navegar por los objetos de una colección de datos mediante la funcionalidad proporcionada en la clase <xref:System.Windows.Data.CollectionView>.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `myCollectionView` es un objeto <xref:System.Windows.Data.CollectionView> que es una vista de una colección enlazada.  
  
 En el ejemplo siguiente, `OnButton` es un controlador de eventos para los botones `Previous` y `Next` de una aplicación, que son botones que permiten al usuario navegar por la recopilación de datos. Tenga en cuenta que las propiedades <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> notifican si el puntero del registro actual ha llegado al principio y al final de la lista, respectivamente para que se pueda llamar a <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> como corresponda.  
  
 La propiedad <xref:System.Windows.Data.CollectionView.CurrentItem%2A> de la vista se convierte en una `Order` para devolver el elemento de pedido actual en la colección.  
  
 [!code-csharp[CollectionView#OnButton](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
- [Ordenar datos en una vista](how-to-sort-data-in-a-view.md)
- [Filtrar datos en una vista](how-to-filter-data-in-a-view.md)
- [Ordenar y agrupar datos mediante una vista en XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
