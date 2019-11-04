---
title: 'Cómo: Enlazar a los resultados de una consulta LINQ'
ms.date: 03/30/2017
helpviewer_keywords:
- running a LINQ query [WPF], bind to results
- binding to LINQ query results [WPF]
ms.assetid: ff2844d9-17ed-4ea6-aab1-5111af0bc684
ms.openlocfilehash: d21ac5f366e001ea76d6eda64ed62583248796f6
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73454421"
---
# <a name="how-to-bind-to-the-results-of-a-linq-query"></a>Cómo: Enlazar a los resultados de una consulta LINQ

En este ejemplo se muestra cómo ejecutar una consulta LINQ y cómo enlazar a los resultados.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se crean dos cuadros de lista. El primer cuadro de lista contiene tres elementos de lista.

[!code-xaml[LinqExample#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml#ui)]

Al seleccionar un elemento del primer cuadro de lista, se invoca el siguiente controlador de eventos. En este ejemplo, `Tasks` es una colección de objetos `Task`. La clase `Task` tiene una propiedad denominada `Priority`. Este controlador de eventos ejecuta una consulta LINQ que devuelve la colección de `Task` objetos que tienen el valor de prioridad seleccionado y, a continuación, lo establece como <xref:System.Windows.FrameworkElement.DataContext%2A>:

[!code-csharp[LinqExample#Using](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#using)]
[!code-csharp[LinqExample#Tasks](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#tasks)]
[!code-csharp[LinqExample#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/LinqExample/CSharp/Window1.xaml.cs#handler)]

El segundo cuadro de lista se enlaza a esa colección porque su valor <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> está establecido en `{Binding}`. Como resultado, se muestra la colección devuelta (basada en el `myTaskTemplate` <xref:System.Windows.DataTemplate>).

## <a name="see-also"></a>Vea también

- [Hacer que los datos estén disponibles para el enlace en XAML](how-to-make-data-available-for-binding-in-xaml.md)
- [Enlazar a una colección y mostrar información basada en la selección](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [Novedades de WPF versión 4.5](../getting-started/whats-new.md)
- [Información general sobre el enlace de datos](../../../desktop-wpf/data/data-binding-overview.md)
