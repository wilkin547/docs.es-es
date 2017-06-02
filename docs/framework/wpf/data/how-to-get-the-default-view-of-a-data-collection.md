---
title: "C&#243;mo: Obtener la vista predeterminada de una recolecci&#243;n de datos | Microsoft Docs"
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
  - "crear, vistas de colecciones de datos"
  - "enlace de datos, crear vistas de colecciones de datos"
  - "colecciones de datos, crear vistas de"
ms.assetid: b641e96c-c2f6-42ea-9c5d-bac81176ad65
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Obtener la vista predeterminada de una recolecci&#243;n de datos
Las vistas permiten ver la misma recolección de datos de maneras diferentes, según los criterios de ordenación, filtrado o agrupación.  Cada recolección tiene una vista predeterminada compartida, que se utiliza como origen de enlace cuando en el enlace se especifica una recolección como origen.  En este ejemplo se muestra cómo obtener la vista predeterminada de una recolección.  
  
## Ejemplo  
 Para crear la vista, se necesita una referencia de objeto a la recolección.  Este objeto de datos se puede obtener haciendo referencia al propio objeto subyacente, obteniendo el contexto de datos, obteniendo una propiedad del origen de datos u obteniendo una propiedad del enlace.  En este ejemplo se muestra cómo obtener la propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> de un objeto de datos y utilizarla para abrir directamente la vista predeterminada de esta recolección.  
  
 [!code-csharp[CollectionView#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml.cs#2)]
 [!code-vb[CollectionView#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionView/VisualBasic/Page1.xaml.vb#2)]  
  
 En este ejemplo el elemento raíz es un objeto <xref:System.Windows.Controls.StackPanel>.  La propiedad <xref:System.Windows.FrameworkElement.DataContext%2A> se establece en *myDataSource*, que hace referencia a un proveedor de datos que es una colección <xref:System.Collections.ObjectModel.ObservableCollection%601> de objetos *Order*.  
  
 [!code-xml[CollectionView#CollectionViewDataContext](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionView/CSharp/Page1.xaml#collectionviewdatacontext)]  
  
 Otra posibilidad es crear instancias y enlazar a su propia vista de recolección mediante la clase <xref:System.Windows.Data.CollectionViewSource>.  Esta vista de recolección sólo la comparten los controles que se enlazan a ella directamente.  Para obtener un ejemplo, consulte cómo crear una sección de vista en [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Para obtener ejemplos de la funcionalidad proporcionada por una vista de colección, consulte [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md), [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md) y [Navegar por los objetos de una colección de datos mediante CollectionView](../../../../docs/framework/wpf/data/how-to-navigate-through-the-objects-in-a-data-collectionview.md).  
  
## Vea también  
 [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)