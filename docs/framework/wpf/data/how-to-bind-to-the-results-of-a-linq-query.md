---
title: "Cómo: Enlazar a los resultados de una consulta LINQ"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e77a0c698dae0330877c54422c15e14c82376891
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Cómo: Enlazar a los resultados de una consulta LINQ
Este ejemplo muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea dos cuadros de lista. El primer cuadro de lista contiene tres elementos de lista.  
  
 [!code-xaml[LinqExample#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Seleccionar un elemento en el primer cuadro de lista, invoca el controlador de eventos siguiente. En este ejemplo, `Tasks` es una colección de `Task` objetos. El `Task` clase tiene una propiedad denominada `Priority`. Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionado y, a continuación, se establece como el <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 El segundo cuadro de lista se enlaza a esa colección porque su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor se establece en `{Binding}`. Como resultado, muestra la colección devuelta (en función de la `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>Vea también  
 [Hacer que los datos estén disponibles para el enlace en XAML](../../../../docs/framework/wpf/data/how-to-make-data-available-for-binding-in-xaml.md)  
 [Enlazar a una colección y mostrar información basada en la selección](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [Novedades de WPF versión 4.5](../../../../docs/framework/wpf/getting-started/whats-new.md)  
 [Información general sobre el enlace de datos](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
