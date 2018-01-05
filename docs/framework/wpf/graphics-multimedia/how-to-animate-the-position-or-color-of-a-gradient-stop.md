---
title: "Cómo: Animar la posición o color de un punto de degradado"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9c5a72d5df9d7ff9cdd90d6e09a7dab574e2caaf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-position-or-color-of-a-gradient-stop"></a>Cómo: Animar la posición o color de un punto de degradado
Este ejemplo muestra cómo animar la <xref:System.Windows.Media.GradientStop.Color%2A> y <xref:System.Windows.Media.GradientStop.Offset%2A> de <xref:System.Windows.Media.GradientStop> objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se anima tres puntos de degradado dentro de un <xref:System.Windows.Media.LinearGradientBrush>. El ejemplo utiliza tres animaciones, cada uno de los cuales anima un delimitador de degradado diferente:  
  
-   La primera animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, anima la detención de degradado primera <xref:System.Windows.Media.GradientStop.Offset%2A> comprendido entre 0,0 y 1,0 y luego de nuevo a 0,0. Como resultado, el primer color del degradado cambia del lado izquierdo a la derecha del rectángulo y luego de nuevo a la izquierda.  
  
-   La segunda animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, anima la detención de degradado segundo <xref:System.Windows.Media.GradientStop.Color%2A> de <xref:System.Windows.Media.Colors.Purple%2A> a <xref:System.Windows.Media.Colors.Yellow%2A> y, a continuación, de nuevo a <xref:System.Windows.Media.Colors.Purple%2A>. Como resultado, el color intermedio del degradado cambia del púrpura a amarillo y vuelve al púrpura.  
  
-   La tercera animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, anima la opacidad de la detención de degradado tercer <xref:System.Windows.Media.GradientStop.Color%2A> por -1 y luego de nuevo. Como resultado, el tercer color del degradado se atenúa gradualmente y, a continuación, se convierte en opaco.  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/GradientStopAnimationExample.cs#graphicsmmgradientanimationexampleswholepage)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/gradientstopanimationexample.vb#graphicsmmgradientanimationexampleswholepage)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMGradientAnimationExamplesWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/GradientStopAnimationExample.xaml#graphicsmmgradientanimationexampleswholepage)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Media.LinearGradientBrush>, el proceso es el mismo para animar <xref:System.Windows.Media.GradientStop> objetos dentro de un <xref:System.Windows.Media.RadialGradientBrush>.  
  
 Para obtener ejemplos adicionales, consulte la [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.GradientStop>  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)
