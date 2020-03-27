---
title: 'Cómo: Animar un objeto Boolean mediante fotogramas clave'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Booleans [WPF], animating with key frames
- animation [WPF], Booleans with key frames
- key frames [WPF], animating Booleans with
ms.assetid: 4b0fac96-6231-4fcf-9775-4dd673ddc785
ms.openlocfilehash: 35704996dcf21fe463169dc13572941bcd8fbad1
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344932"
---
# <a name="how-to-animate-a-boolean-by-using-key-frames"></a>Cómo: Animar un objeto Boolean mediante fotogramas clave
En este ejemplo se muestra cómo <xref:System.Windows.Controls.Button> animar el valor de propiedad booleana de un control mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames> siguiente se <xref:System.Windows.UIElement.IsEnabled%2A> utiliza <xref:System.Windows.Controls.Button> la clase para animar la propiedad de un control. Todos los fotogramas clave de este <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> ejemplo utilizan una instancia de la clase. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteBooleanKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, el movimiento de la animación es desigual.  
  
 [!code-csharp[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/keyframes_snip/CSharp/BooleanAnimationUsingKeyFramesExample.cs#booleananimationusingkeyframeswholepage)]
 [!code-vb[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/keyframes_snip/visualbasic/booleananimationusingkeyframesexample.vb#booleananimationusingkeyframeswholepage)]
 [!code-xaml[keyframes_snip#BooleanAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/BooleanAnimationUsingKeyFramesExample.xaml#booleananimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.BooleanAnimationUsingKeyFrames>
- <xref:System.Windows.UIElement.IsEnabled%2A>
- <xref:System.Windows.Controls.Button>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
