---
title: Procedimiento Enlazar a los resultados de una consulta LINQ
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: 5464ee9c59a7c99a83774a7535b9b3c422c1d2e1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644423"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Procedimiento Enlazar a los resultados de una consulta LINQ
En este ejemplo se muestra cómo ejecutar una consulta LINQ y, a continuación, enlazar a los resultados.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea dos cuadros de lista. El primer cuadro de lista contiene tres elementos de lista.  
  
 [!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]  
  
 Seleccionar un elemento en el primer cuadro de lista, invoca el controlador de eventos siguiente. En este ejemplo, `Tasks` es una colección de `Task` objetos. El `Task` clase tiene una propiedad denominada `Priority`. Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionada y, a continuación, se establece como el <xref:System.Windows.FrameworkElement.DataContext%2A>:  
  
 [!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]  
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]  
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]  
  
 El segundo cuadro de lista se enlaza a esa colección porque su <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> valor se establece en `{Binding}`. Como resultado, muestra la colección devuelta (según la `myTaskTemplate` <xref:System.Windows.DataTemplate>).  
  
## <a name="see-also"></a>Vea también

- [Hacer que los datos estén disponibles para el enlace en XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Enlazar a una colección y mostrar información basada en la selección](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Novedades de WPF versión 4.5](../getting-started/whats-new.md)
- [Información general sobre el enlace de datos](data-binding-overview.md)
- [Temas "Cómo..."](data-binding-how-to-topics.md)
