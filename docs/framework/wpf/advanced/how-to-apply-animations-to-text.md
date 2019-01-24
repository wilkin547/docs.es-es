---
title: Procedimiento Aplicar animaciones a texto
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 56336c45639168c6432b92fe555c6d37448cb7cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54720514"
---
# <a name="how-to-apply-animations-to-text"></a>Procedimiento Aplicar animaciones a texto
Las animaciones pueden modificar la presentación y la apariencia del texto en la aplicación. En los ejemplos siguientes usan diferentes tipos de animaciones para influir en la presentación del texto en un <xref:System.Windows.Controls.TextBlock> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el ancho del bloque de texto. El valor del ancho cambia del ancho del bloque de texto a 0 durante 10 segundos y, a continuación, invierte los valores de ancho y continúa. Este tipo de animación crea un efecto de barrido.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la opacidad del bloque de texto. El valor de opacidad cambia de 1,0 a 0 durante 5 segundos y, a continuación, invierte los valores de opacidad y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 El siguiente diagrama muestra el efecto de la <xref:System.Windows.Controls.TextBlock> control cambia su opacidad de `1.00` a `0.00` durante el intervalo de 5 segundos definido por el <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Texto cuya opacidad cambia de 1,00 a 0,00](../../../../docs/framework/wpf/advanced/media/fadedtext01.png "FadedText01")  
Opacidad del texto que cambia de 1,00 a 0,00  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.ColorAnimation> para animar el color de primer plano del bloque de texto. El valor de color de primer plano cambia de un color a un segundo color durante 5 segundos y, a continuación, invierte los valores de color y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para girar el bloque de texto. El bloque de texto realiza una rotación completa durante 20 segundos y, a continuación, sigue repitiendo la rotación.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Vea también
- [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)
