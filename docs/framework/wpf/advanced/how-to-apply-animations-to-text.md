---
title: Procedimiento Aplicar animaciones a texto
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: 38aa432fecc5b5e10d8eb90be9c1c596728ed613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108217"
---
# <a name="how-to-apply-animations-to-text"></a>Procedimiento Aplicar animaciones a texto
Las animaciones pueden modificar la presentación y la apariencia del texto en la aplicación. En los ejemplos siguientes usan diferentes tipos de animaciones para influir en la presentación del texto en un <xref:System.Windows.Controls.TextBlock> control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar el ancho del bloque de texto. El valor del ancho cambia del ancho del bloque de texto a 0 durante 10 segundos y, a continuación, invierte los valores de ancho y continúa. Este tipo de animación crea un efecto de barrido.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para animar la opacidad del bloque de texto. El valor de opacidad cambia de 1,0 a 0 durante 5 segundos y, a continuación, invierte los valores de opacidad y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 El siguiente diagrama muestra el efecto de la <xref:System.Windows.Controls.TextBlock> control cambia su opacidad de `1.00` a `0.00` durante el intervalo de 5 segundos definido por el <xref:System.Windows.Media.Animation.Timeline.Duration%2A>.  
  
 ![Texto cuya opacidad cambia de 1,00 a 0,00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  
   
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.ColorAnimation> para animar el color de primer plano del bloque de texto. El valor de color de primer plano cambia de un color a un segundo color durante 5 segundos y, a continuación, invierte los valores de color y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.Animation.DoubleAnimation> para girar el bloque de texto. El bloque de texto realiza una rotación completa durante 20 segundos y, a continuación, sigue repitiendo la rotación.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Vea también

- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
