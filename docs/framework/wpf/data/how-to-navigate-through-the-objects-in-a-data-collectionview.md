---
title: "C&#243;mo: Navegar por los objetos de una colecci&#243;n de datos mediante CollectionView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "CollectionView, navegar por los objetos"
  - "enlace de datos, navegar por los objetos de una colección de datos mediante CollectionView"
  - "navegar por los objetos de una colección de datos mediante CollectionView"
ms.assetid: fcd37590-bce1-4ac9-8b74-3b96c7458b8a
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Navegar por los objetos de una colecci&#243;n de datos mediante CollectionView
Las vistas permiten ver la misma recolección de datos de maneras diferentes, según cómo se ordene, filtre o agrupe.  Las vistas también proporcionan el concepto de indicador de registro actual y habilitan el movimiento del puntero.  En este ejemplo se muestra cómo obtener el objeto actual y se navega por los objetos de una recolección de datos utilizando la funcionalidad proporcionada en la clase <xref:System.Windows.Data.CollectionView>.  
  
## Ejemplo  
 En este ejemplo, `myCollectionView` es un objeto <xref:System.Windows.Data.CollectionView> que es una vista de una recolección enlazada.  
  
 En el ejemplo siguiente, `OnButton` es un controlador de eventos para los botones `Previous` y `Next` de una aplicación, que permiten al usuario navegar por la recolección de datos.  Observe que las propiedades <xref:System.Windows.Data.CollectionView.IsCurrentBeforeFirst%2A> y <xref:System.Windows.Data.CollectionView.IsCurrentAfterLast%2A> informan de si el indicador de registro actual ha alcanzado el principio o el final de la lista, respectivamente, para que se pueda llamar a <xref:System.Windows.Data.CollectionView.MoveCurrentToFirst%2A> y <xref:System.Windows.Data.CollectionView.MoveCurrentToLast%2A>, según proceda.  
  
 La propiedad <xref:System.Windows.Data.CollectionView.CurrentItem%2A> de la vista se convierte en `Order` para devolver el elemento de orden actual de la recolección.  
  
 [!code-csharp[CollectionView#OnButton](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#onbutton)]
 [!code-vb[CollectionView#OnButton](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#onbutton)]  
  
## Vea también  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)