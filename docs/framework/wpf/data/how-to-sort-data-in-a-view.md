---
title: "C&#243;mo: Ordenar datos en una vista | Microsoft Docs"
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
  - "enlace de datos, agrupar datos en vistas"
  - "enlace de datos, ordenar datos en vistas"
  - "agrupar datos en vistas"
  - "ordenar datos en vistas"
  - "vistas, agrupar datos"
  - "vistas, ordenar datos"
ms.assetid: f4c43578-01b7-4774-a953-acb95a13b94a
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Ordenar datos en una vista
En este ejemplo se describe cómo ordenar los datos en una vista.  
  
## Ejemplo  
 En el ejemplo siguiente se crean un control <xref:System.Windows.Controls.ListBox> simple y un control <xref:System.Windows.Controls.Button>:  
  
 [!code-xml[ListBoxSort_snip#HowTo](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml#howto)]  
  
 El controlador de eventos <xref:System.Windows.Controls.Primitives.ButtonBase.Click> del botón contiene la lógica necesaria para ordenar los elementos de <xref:System.Windows.Controls.ListBox> en orden descendente.  Puede hacerlo porque al agregar elementos a <xref:System.Windows.Controls.ListBox> de esta manera se agregan al objeto <xref:System.Windows.Controls.ItemCollection> de <xref:System.Windows.Controls.ListBox>, y <xref:System.Windows.Controls.ItemCollection> se deriva de la clase <xref:System.Windows.Data.CollectionView>.  Si enlaza <xref:System.Windows.Controls.ListBox> a una colección mediante la propiedad <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A>, puede utilizar la misma técnica para ordenar.  
  
 [!code-csharp[ListBoxSort_snip#HowToCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxSort_snip/CSharp/Window1.xaml.cs#howtocode)]
 [!code-vb[ListBoxSort_snip#HowToCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxSort_snip/visualbasic/window1.xaml.vb#howtocode)]  
  
 Siempre que tenga una referencia al objeto de vista, puede utilizar la misma técnica para ordenar el contenido de otras vistas de colección.  Para obtener un ejemplo de cómo obtener una vista, consulte [Obtener la vista predeterminada de una recolección de datos](../../../../docs/framework/wpf/data/how-to-get-the-default-view-of-a-data-collection.md).  Para obtener otro ejemplo, vea [Ordenar una columna de GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md).  Para obtener más información sobre vistas, consulte Enlazar a colecciones en [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Para obtener un ejemplo de cómo aplicar la lógica de ordenación en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], consulte [Ordenar y agrupar datos mediante una vista en XAML](../../../../docs/framework/wpf/data/how-to-sort-and-group-data-using-a-view-in-xaml.md).  
  
## Vea también  
 <xref:System.Windows.Data.ListCollectionView.CustomSort%2A>   
 [Ordenar una columna de GridView cuando se hace clic en un encabezado](../../../../docs/framework/wpf/controls/how-to-sort-a-gridview-column-when-a-header-is-clicked.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Filtrar datos en una vista](../../../../docs/framework/wpf/data/how-to-filter-data-in-a-view.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)