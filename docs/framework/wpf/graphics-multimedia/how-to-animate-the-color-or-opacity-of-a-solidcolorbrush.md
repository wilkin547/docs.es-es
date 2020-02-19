---
title: 'Cómo: Animar el color o la opacidad de un objeto SolidColorBrush'
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 08b85935e0cb1ababd1fb63b9d02518ea3fcfa17
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452888"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Cómo: Animar el color o la opacidad de un objeto SolidColorBrush
En este ejemplo se muestra cómo animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de una <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usan tres animaciones para animar el <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de una <xref:System.Windows.Media.SolidColorBrush>.  
  
- La primera animación, una <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el Mouse entra en el rectángulo.  
  
- La siguiente animación, otra <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.  
  
- La animación final, una <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0,0 cuando se presiona el botón primario del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Para obtener un ejemplo más completo, en el que se muestra cómo animar distintos tipos de pinceles, vea el [ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes). Para obtener más información acerca de la animación, consulte [información general sobre animaciones](animation-overview.md).  
  
 Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo se usa un objeto <xref:System.Windows.Media.Animation.Storyboard> para aplicar sus animaciones. Sin embargo, al aplicar una animación única en el código, es más fácil utilizar el método <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
- [Ejemplo de pinceles](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes)
