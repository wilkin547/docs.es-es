---
title: "C&#243;mo: Filtrar datos en una vista | Microsoft Docs"
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
  - "enlace de datos, filtrar datos en vistas"
  - "filtrar datos en vistas"
  - "vistas, filtrar datos"
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Filtrar datos en una vista
En este ejemplo se muestra cómo filtrar los datos en una vista.  
  
## Ejemplo  
 Para crear un filtro, se define un método que proporciona la lógica de filtrado.  El método se utiliza como devolución de llamada y acepta un parámetro de tipo `object`.  El método siguiente devuelve todos los objetos `Order` cuya propiedad `filled` está establecida en "No", y deja fuera el resto de los objetos.  
  
 [!code-csharp[SortFilter#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 A continuación, puede aplicar el filtro, como se muestra en el ejemplo siguiente.  En este ejemplo, `myCollectionView` es un objeto <xref:System.Windows.Data.ListCollectionView>.  
  
 [!code-csharp[SortFilter#Filter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 Para deshacer el filtrado, puede establecer la propiedad <xref:System.Windows.Data.CollectionView.Filter%2A> en `null`:  
  
 [!code-csharp[SortFilter#Unfilter](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 Para obtener información acerca de cómo crear u obtener vistas, consulte [Obtener la vista predeterminada de una recolección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Para obtener el ejemplo completo, vea [Sorting and Filtering Items in a View Sample](http://go.microsoft.com/fwlink/?LinkID=160040).  
  
 Si el objeto de vista procede de un objeto <xref:System.Windows.Data.CollectionViewSource>, la lógica de filtrado se aplica estableciendo un controlador para el evento <xref:System.Windows.Data.CollectionViewSource.Filter>.  En el ejemplo siguiente, `listingDataView` es una instancia de <xref:System.Windows.Data.CollectionViewSource>.  
  
 [!code-csharp[DataBindingLab#10](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 En el ejemplo siguiente se muestra la implementación del controlador de eventos del filtro `ShowOnlyBargainsFilter` de ejemplo.  Este controlador de eventos usa la propiedad <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> para filtrar objetos `AuctionItem` que tienen un `CurrentPrice` de 25 $ o más.  
  
 [!code-csharp[DataBindingLab#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## Vea también  
 <xref:System.Windows.Data.CollectionView.CanFilter%2A>   
 <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Ordenar datos en una vista](../../../../docs/framework/wpf/data/how-to-sort-data-in-a-view.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)