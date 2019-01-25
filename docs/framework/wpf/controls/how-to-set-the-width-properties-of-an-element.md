---
title: Procedimiento Establecer las propiedades de ancho de un elemento
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- width properties [WPF]
- Panel control [WPF], width properties of elements
ms.assetid: 6ee04a9d-63f0-4f5b-a406-0a8cd4c35729
ms.openlocfilehash: 739b041d8ca89abb9bd1934abb997d1154f08c95
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54673990"
---
# <a name="how-to-set-the-width-properties-of-an-element"></a>Procedimiento Establecer las propiedades de ancho de un elemento
## <a name="example"></a>Ejemplo  
 Este ejemplo muestran las diferencias de comportamiento entre las cuatro propiedades de ancho en representación [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)].  
  
 La <xref:System.Windows.FrameworkElement> clase expone cuatro propiedades que describen las características de ancho de un elemento. Estas cuatro propiedades pueden entrar en conflicto y, cuando lo hacen, el valor que tiene prioridad se determina como sigue: el <xref:System.Windows.FrameworkElement.MinWidth%2A> valor tiene prioridad sobre la <xref:System.Windows.FrameworkElement.MaxWidth%2A> valor, que a su vez tiene prioridad sobre la <xref:System.Windows.FrameworkElement.Width%2A> valor. Una propiedad de la cuarta, <xref:System.Windows.FrameworkElement.ActualWidth%2A>, es de solo lectura y notifica el ancho real determinado por las interacciones con el proceso de diseño.  
  
 La siguiente [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] ejemplos dibujar un <xref:System.Windows.Shapes.Rectangle> elemento (`rect1`) como un elemento secundario de <xref:System.Windows.Controls.Canvas>. Puede cambiar las propiedades de ancho de un <xref:System.Windows.Shapes.Rectangle> mediante el uso de una serie de <xref:System.Windows.Controls.ListBox> elementos que representan los valores de propiedad <xref:System.Windows.FrameworkElement.MinWidth%2A>, <xref:System.Windows.FrameworkElement.MaxWidth%2A>, y <xref:System.Windows.FrameworkElement.Width%2A>. De esta manera, se muestra gráficamente la prioridad de cada propiedad.  
  
 [!code-xaml[WidthMinWidthMaxWidth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#1)]  
[!code-xaml[WidthMinWidthMaxWidth#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml#2)]  
  
 Los siguientes ejemplos de código subyacente controlan los eventos que el <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> provoca el evento. Cada método personalizado toma la entrada de la <xref:System.Windows.Controls.ListBox>, analiza el valor como un <xref:System.Double>y se aplica el valor a la propiedad relacionada con el ancho especificada. Los valores de ancho también se convierte en una cadena y escritos en varios <xref:System.Windows.Controls.TextBlock> elementos (definición de esos elementos no se muestra en el XAML seleccionado).  
  
 [!code-csharp[WidthMinWidthMaxWidth#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/WidthMinWidthMaxWidth/CSharp/Window1.xaml.cs#3)]
 [!code-vb[WidthMinWidthMaxWidth#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/WidthMinWidthMaxWidth/VisualBasic/Window1.xaml.vb#3)]  
  
 Para obtener un ejemplo completo, vea [ejemplo de comparación de las propiedades ancho](https://go.microsoft.com/fwlink/?LinkID=160050).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.ListBox>
- <xref:System.Windows.FrameworkElement>
- <xref:System.Windows.FrameworkElement.ActualWidth%2A>
- <xref:System.Windows.FrameworkElement.MaxWidth%2A>
- <xref:System.Windows.FrameworkElement.MinWidth%2A>
- <xref:System.Windows.FrameworkElement.Width%2A>
- [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)
- [Establecer las propiedades de alto de un elemento](../../../../docs/framework/wpf/controls/how-to-set-the-height-properties-of-an-element.md)
- [Ejemplo de comparación de las propiedades de ancho](https://go.microsoft.com/fwlink/?LinkID=160050)
