---
title: 'Cómo: Aplicar animaciones a texto'
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], animations
- animation [WPF], text
ms.assetid: eec3d26c-0a21-420f-8012-671621c47089
ms.openlocfilehash: ed2f3beb904f724ac93e2c4033aa6b2eb3fa1290
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174633"
---
# <a name="how-to-apply-animations-to-text"></a>Cómo: Aplicar animaciones a texto
Las animaciones pueden modificar la presentación y la apariencia del texto en la aplicación. En los ejemplos siguientes se utilizan diferentes tipos de <xref:System.Windows.Controls.TextBlock> animaciones para afectar a la visualización de texto en un control.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para animar el ancho del bloque de texto. El valor del ancho cambia del ancho del bloque de texto a 0 durante 10 segundos y, a continuación, invierte los valores de ancho y continúa. Este tipo de animación crea un efecto de barrido.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample1](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample1)]  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para animar la opacidad del bloque de texto. El valor de opacidad cambia de 1,0 a 0 durante 5 segundos y, a continuación, invierte los valores de opacidad y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample2](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample2)]  
  
 El diagrama siguiente muestra <xref:System.Windows.Controls.TextBlock> el efecto del `1.00` control `0.00` cambiando su opacidad de <xref:System.Windows.Media.Animation.Timeline.Duration%2A>a durante el intervalo de 5 segundos definido por el archivo .  
  
 ![Texto cambiando la opacidad de 1.00 a 0.00.](./media/how-to-apply-animations-to-text/faded-text-opacity-change.png)  

 En el ejemplo <xref:System.Windows.Media.Animation.ColorAnimation> siguiente se utiliza a para animar el color de primer plano del bloque de texto. El valor de color de primer plano cambia de un color a un segundo color durante 5 segundos y, a continuación, invierte los valores de color y continúa.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample3](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample3)]  
  
 En el ejemplo <xref:System.Windows.Media.Animation.DoubleAnimation> siguiente se utiliza a para rotar el bloque de texto. El bloque de texto realiza una rotación completa durante 20 segundos y, a continuación, sigue repitiendo la rotación.  
  
 [!code-xaml[TextAnimationSample#TextAnimationSample4](~/samples/snippets/csharp/VS_Snippets_Wpf/TextAnimationSample/CS/Window1.xaml#textanimationsample4)]  
  
## <a name="see-also"></a>Consulte también

- [Información general sobre animaciones](../graphics-multimedia/animation-overview.md)
