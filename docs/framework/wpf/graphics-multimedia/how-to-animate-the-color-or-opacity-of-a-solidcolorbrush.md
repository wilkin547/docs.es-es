---
title: "Cómo: Animar el color o la opacidad de un objeto SolidColorBrush"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SolidColorBrush [WPF], animating color of
- colors [WPF], animating
- opacity [WPF], animating
- animation [WPF], color of SolidColorBrush
- animation [WPF], opacity of SolidColorBrush
- SolidColorBrush [WPF], animating opacity of
ms.assetid: d9154354-843f-4713-bad1-35bb0ba6eaeb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4bac3ae90fa0fa2229e236f46b8884c942b99bef
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-animate-the-color-or-opacity-of-a-solidcolorbrush"></a>Cómo: Animar el color o la opacidad de un objeto SolidColorBrush
Este ejemplo muestra cómo animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza tres animaciones para animar la <xref:System.Windows.Media.SolidColorBrush.Color%2A> y <xref:System.Windows.Media.Brush.Opacity%2A> de un <xref:System.Windows.Media.SolidColorBrush>.  
  
-   La primera animación, un <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Gray%2A> cuando el mouse entra en el rectángulo.  
  
-   La siguiente animación, otro <xref:System.Windows.Media.Animation.ColorAnimation>, cambia el color del pincel a <xref:System.Windows.Media.Colors.Orange%2A> cuando el mouse sale del rectángulo.  
  
-   La última animación, un <xref:System.Windows.Media.Animation.DoubleAnimation>, cambia la opacidad del pincel a 0.0 cuando se presiona el botón primario del mouse.  
  
 [!code-csharp[brushanimations_snip#SolidColorBrushAnimationExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/brushanimations_snip/CSharp/SolidColorBrushExample.cs#solidcolorbrushanimationexample)]  
  
 Para obtener un ejemplo más completo, que muestra cómo animar tipos diferentes de pinceles, consulte la [ejemplo pinceles](http://go.microsoft.com/fwlink/?LinkID=159973). Para obtener más información acerca de la animación, consulte el [información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md).  
  
 Para mantener la coherencia con otros ejemplos de animación, en las versiones de código de este ejemplo utiliza un <xref:System.Windows.Media.Animation.Storyboard> objeto que se va a aplicar sus animaciones. Sin embargo, al aplicar una animación única en código, es más fácil utilizar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método en lugar de usar un <xref:System.Windows.Media.Animation.Storyboard>. Para obtener un ejemplo, vea [Animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Ejemplo de pinceles](http://go.microsoft.com/fwlink/?LinkID=159973)
