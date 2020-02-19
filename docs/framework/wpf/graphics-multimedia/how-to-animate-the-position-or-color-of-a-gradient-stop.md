---
title: 'Cómo: Animar la posición o color de un punto de degradado'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- position [WPF], animating
- animation [WPF], position of GradientStop objects
- GradientStop objects [WPF], animating color of
- colors [WPF], animating
- animation [WPF], color of GradientStop objects
- GradientStop objects [WPF], animating position of
ms.assetid: 6f5b8b47-6c32-4b8e-98ee-fdf6515ec843
ms.openlocfilehash: aeae33f5f3c8016808988f58d61969e9b6f05039
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452849"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Cómo: Animar la posición o color de un punto de degradado
En este ejemplo se muestra cómo animar el <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se animan tres delimitadores de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>. En el ejemplo se usan tres animaciones, cada una de las cuales anima un delimitador de degradado diferente:  
  
- La primera animación, una <xref:System.Windows.Media.Animation.DoubleAnimation>, anima el primer <xref:System.Windows.Media.GradientStop.Offset%2A> de delimitador de degradado de 0,0 a 1,0 y después vuelve a 0,0. Como resultado, el primer color del degradado se desplaza desde el lado izquierdo hasta el lado derecho del rectángulo y, a continuación, vuelve al lado izquierdo.  
  
- La segunda animación, una <xref:System.Windows.Media.Animation.ColorAnimation>, anima el <xref:System.Windows.Media.GradientStop.Color%2A> del segundo delimitador de degradado de <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y, a continuación, de nuevo a <xref:System.Windows.Media.Colors.Purple%2A>. Como resultado, el color intermedio del degradado cambia de púrpura a amarillo y de nuevo a púrpura.  
  
- La tercera animación, otra <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad del tercer delimitador de degradado <xref:System.Windows.Media.GradientStop.Color%2A> por-1 y, a continuación, hacia atrás. Como resultado, el tercer color del degradado se atenúa y vuelve a ser opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar objetos <xref:System.Windows.Media.GradientStop> dentro de un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Para obtener más ejemplos, vea el [ejemplo brushes](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Brushes).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.GradientStop>
- [Información general sobre animaciones](animation-overview.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
