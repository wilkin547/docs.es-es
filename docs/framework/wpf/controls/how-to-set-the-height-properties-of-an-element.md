---
title: 'Cómo: Establecer las propiedades de alto de un elemento'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- height properties [WPF]
- Panel control [WPF], height properties of elements
ms.assetid: 5ab9e781-dbb8-469a-a3c8-cf38ce312647
ms.openlocfilehash: 6500af3c637092820e538d79894d600d617953bf
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124291"
---
# <a name="how-to-set-the-height-properties-of-an-element"></a>Cómo: Establecer las propiedades de alto de un elemento
## <a name="example"></a>Ejemplo  
 En este ejemplo se muestran visualmente las diferencias en el comportamiento de la representación entre las cuatro propiedades relacionadas con el alto en [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La clase <xref:System.Windows.FrameworkElement> expone cuatro propiedades que describen las características de alto de un elemento. Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina de la siguiente manera: el valor <xref:System.Windows.FrameworkElement.MinHeight%2A> tiene prioridad sobre el valor <xref:System.Windows.FrameworkElement.MaxHeight%2A>, que a su vez tiene prioridad sobre el valor de <xref:System.Windows.FrameworkElement.Height%2A>. Una cuarta propiedad, <xref:System.Windows.FrameworkElement.ActualHeight%2A>, es de solo lectura y notifica el alto real tal y como lo determinan las interacciones con el proceso de diseño.  
  
 En los siguientes [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos se dibuja un elemento de <xref:System.Windows.Shapes.Rectangle> (`rect1`) como elemento secundario de <xref:System.Windows.Controls.Canvas>. Puede cambiar las propiedades de alto de un <xref:System.Windows.Shapes.Rectangle> mediante una serie de elementos <xref:System.Windows.Controls.ListBox> que representan los valores de propiedad de <xref:System.Windows.FrameworkElement.MinHeight%2A>, <xref:System.Windows.FrameworkElement.MaxHeight%2A>y <xref:System.Windows.FrameworkElement.Height%2A>. De esta manera, la prioridad de cada propiedad se muestra visualmente.  
  
 [!code-xaml[HeightMinHeightMaxHeight#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#1)]  
[!code-xaml[HeightMinHeightMaxHeight#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente controlan los eventos que genera el evento <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged>. Cada controlador toma la entrada del <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y aplica el valor a la propiedad relacionada con el alto especificado. Los valores de alto también se convierten en una cadena y se escriben en varios elementos <xref:System.Windows.Controls.TextBlock> (la definición de esos elementos no se muestra en el código XAML seleccionado).  
  
 [!code-csharp[HeightMinHeightMaxHeight#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HeightMinHeightMaxHeight/CSharp/Window1.xaml.cs#3)]
 [!code-vb[HeightMinHeightMaxHeight#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HeightMinHeightMaxHeight/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener el ejemplo completo, vea [ejemplo de propiedades de alto](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement.ActualHeight%2A>
- <xref:System.Windows.FrameworkElement.MaxHeight%2A>
- <xref:System.Windows.FrameworkElement.MinHeight%2A>
- <xref:System.Windows.FrameworkElement.Height%2A>
- [Establecer las propiedades de ancho de un elemento](how-to-set-the-width-properties-of-an-element.md)
- [Información general sobre elementos Panel](panels-overview.md)
- [Ejemplo de propiedades de alto](https://github.com/microsoft/WPF-Samples/tree/master/Elements/HeightProperties)
