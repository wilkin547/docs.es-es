---
title: 'Cómo: Establecer las propiedades de ancho de un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 682929625612114d042e4619d8388617988b3c48
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124278"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Cómo: Establecer las propiedades de ancho de un elemento
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestran visualmente las diferencias en el comportamiento de la representación entre las cuatro propiedades relacionadas con el ancho en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de ancho de un elemento. Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina de la siguiente manera: el valor <xref:System.Windows.FrameworkElement.MinWidth%2A> tiene prioridad sobre el valor <xref:System.Windows.FrameworkElement.MaxWidth%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Width%2A>. Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, es de solo lectura y notifica el ancho real según lo establecido por las interacciones con el proceso de diseño.  
  
 En los siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos se dibuja un elemento de <xref:System.Windows.Shapes.Rectangle> (`rect1`) como elemento secundario de <xref:System.Windows.Controls.Canvas>. Puede cambiar las propiedades de ancho de un <xref:System.Windows.Shapes.Rectangle> mediante una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>y <xref:System.Windows.FrameworkElement.Width%2A>. De esta manera, la prioridad de cada propiedad se muestra visualmente.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente controlan los eventos que genera el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Cada método personalizado toma la entrada del <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y aplica el valor a la propiedad relacionada con el ancho especificada. Los valores de ancho también se convierten en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> (la definición de esos elementos no se muestra en el código XAML seleccionado).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](~/samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener el ejemplo completo, vea [ejemplo de comparación de propiedades de ancho](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Información general sobre elementos Panel](panels-overview.md)
- [Establecer las propiedades de alto de un elemento](how-to-set-the-height-properties-of-an-element.md)
- [Ejemplo de comparación de propiedades de ancho](https://github.com/Microsoft/WPF-Samples/tree/master/Elements/WidthProperties)
