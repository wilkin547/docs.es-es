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
ms.openlocfilehash: fcbb546b64810416d3f7dbe052da77b7bc941e7a
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44083990"
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Cómo: Animar la posición o color de un punto de degradado
En este ejemplo se muestra cómo animar la <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se anima tres puntos de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>. En el ejemplo se utiliza tres animaciones, cada uno de los cuales anima un delimitador de degradado diferentes:  
  
-   La primera animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, anima el delimitador de degradado primera <xref:System.Windows.Media.GradientStop.Offset%2A> de 0,0 a 1,0 y luego volver a 0,0. Como resultado, el primer color del degradado cambia del lado izquierdo a la derecha del rectángulo y, a continuación, realizar una copia en el lado izquierdo.  
  
-   La segunda animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, anima el delimitador de degradado segundo <xref:System.Windows.Media.GradientStop.Color%2A> desde <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y luego volver a <xref:System.Windows.Media.Colors.Purple%2A>. Como resultado, el color medio del degradado cambia de color púrpura a amarillo y volver a púrpura.  
  
-   La tercera animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad del tercer delimitador de degradado <xref:System.Windows.Media.GradientStop.Color%2A> por -1 y, a continuación, realice una copia. Como resultado, el tercer color de degradado que desaparece y, a continuación, se convierte en opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Aunque este ejemplo usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar <xref:System.Windows.Media.GradientStop> objetos dentro de un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Para obtener ejemplos adicionales, vea el [Brushes Sample](https://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.GradientStop>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
