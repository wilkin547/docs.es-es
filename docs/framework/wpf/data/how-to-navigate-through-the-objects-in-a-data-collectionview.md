---
title: "Cómo: Navegar por los objetos de una colección de datos mediante CollectionView"
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
- CollectionView [WPF], navigating through objects
- data binding [WPF], navigating through objects in data CollectionView
- navigating through objects in data CollectionView [WPF]
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f20881ed452f1ec78381d17a32b4cc2c77305e0e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-through-the-objects-in-a-data-collectionview"></a>Cómo: Navegar por los objetos de una colección de datos mediante CollectionView
Las vistas permiten la misma colección de datos a verse de maneras diferentes, dependiendo de ordenar, filtrar o agrupar. Vistas también proporcionan un concepto de puntero de registro actual y habilitan el movimiento del puntero. Este ejemplo muestra cómo obtener el objeto actual, así como navegar por los objetos en una recopilación de datos mediante la funcionalidad proporcionada en el <xref:System.Windows.Data.CollectionView> clase.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo, `myCollectionView` es un <xref:System.Windows.Data.CollectionView> objeto que es una vista a través de una colección enlazada.  
  
 En el ejemplo siguiente, `OnButton` es un controlador de eventos para el `Previous` y `Next` botones en una aplicación, que son botones que permiten al usuario navegar por la recolección de datos. Tenga en cuenta que la <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> propiedades de informes si el puntero de registro actual ha llegado al principio y el final de la lista respectivamente así que <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A> pueden llamarse como corresponda.  
  
 El <xref:System.Windows.Data.CollectionView.CurrentItem%2A> propiedad de la vista se convierte como un `Order` para devolver el elemento actual de la colección.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)  
 [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)  
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
