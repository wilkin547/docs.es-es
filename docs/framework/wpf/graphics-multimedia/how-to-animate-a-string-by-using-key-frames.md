---
title: 'Cómo: Animar una cadena mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: c954806ca901bbfc3ab6d4bbcc237cd0e404f154
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344669"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Cómo: Animar una cadena mediante fotogramas clave
En este ejemplo se muestra cómo animar una <xref:System.Windows.Controls.ContentControl.Content%2A> cadena, <xref:System.Windows.Controls.Button> que en este ejemplo es la propiedad de un control, mediante marcos de clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Controls.ContentControl.Content%2A> utiliza <xref:System.Windows.Controls.Button>la clase para animar la propiedad de un archivo .  
  
 Todos los fotogramas clave de este <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> ejemplo utilizan una instancia de la clase porque una animación de cadena que se crea con fotogramas clave solo puede utilizar fotogramas clave discretos. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, los cambios en la animación se producen rápidamente y no son sutiles.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
