---
title: Filtrar Animar el color o la opacidad de un objeto SolidColorBrush
ms.date: 03/30/2017
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
ms.openlocfilehash: 541835a7827467aeceb1ed72e54b69e62dc4f916
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57354445"
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Filtrar Animar el color o la opacidad de un objeto SolidColorBrush
En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente utiliza tres animaciones para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.  
  
-   La primera animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el mouse entra en el rectángulo.  
  
-   La siguiente animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.  
  
-   La última animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0.0 cuando se presiona el botón primario del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](~/samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Para obtener un ejemplo más completo, que muestra cómo animar tipos diferentes de pinceles, vea el [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información acerca de la animación, vea el [información general sobre animaciones](animation-overview.md).  
  
 Para mantener la coherencia con otros ejemplos de animación, las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto para aplicar sus animaciones. Sin embargo, al aplicar una animación única en código, resulta más fácil de usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
- [Ejemplo de pinceles](https://go.microsoft.com/fwlink/?LinkID=159973)
