---
title: "C&#243;mo: Enlazar a los resultados de una consulta LINQ | Microsoft Docs"
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
  - "enlazar a los resultados de la consulta LINQ [WPF]"
  - "ejecutar una consulta LINQ [WPF], enlazar a los resultados"
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Enlazar a los resultados de una consulta LINQ
En este ejemplo se muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.  
  
## Ejemplo  
 En el ejemplo siguiente se crean dos cuadros de lista.  El primer cuadro de lista contiene tres elementos de lista.  
  
 [!code-xml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Al seleccionar un elemento del primer cuadro de lista, se invoca el controlador de eventos siguiente.  En este ejemplo, `Tasks` es una colección de objetos `Task`.  La clase `Task` tiene una propiedad denominada `Priority`.  Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de objetos `Task` que tienen el valor de prioridad seleccionado y, a continuación, los establece como <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 El segundo cuadro de lista enlaza a esa colección porque su valor de <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> está establecido en `{Binding}`.  Como resultado, muestra la colección devuelta \(en función de `myTaskTemplate`<xref:System.Windows.DataTemplate>\).  
  
## Vea también  
 [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)   
 [Enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)   
 [Novedades de WPF versión 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)   
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)