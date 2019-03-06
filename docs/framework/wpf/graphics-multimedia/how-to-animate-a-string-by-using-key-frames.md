---
title: Procedimiento Animar un objeto String mediante fotogramas clave
ms.date: 03/30/2017
helpviewer_keywords:
- animation [WPF], strings with key frames
- strings [WPF], animating with key frames
- key frames [WPF], animating strings with
ms.assetid: c62bc9fd-c09a-4227-bce0-0a1ab82049dd
ms.openlocfilehash: 70c5766da2ea91f519756cb47b20d688b33253e0
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356261"
---
# <a name="how-to-animate-a-string-by-using-key-frames"></a>Procedimiento Animar un objeto String mediante fotogramas clave
En este ejemplo se muestra cómo animar una cadena, que en este ejemplo es el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button> control mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames> clase se va a animar el <xref:System.Windows.Controls.ContentControl.Content%2A> propiedad de un <xref:System.Windows.Controls.Button>.  
  
 Todos los fotogramas clave en este ejemplo utilizan una instancia de la <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> clase porque una animación de cadena que se crea con fotogramas clave solo puede usar fotogramas clave discretos. Los fotogramas clave discretos como <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame> crean saltos súbitos entre los valores, es decir, los cambios realizados en la animación se producen rápidamente y no son sutiles.  
  
 [!code-xaml[keyframes_snip#StringAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/StringAnimationUsingKeyFramesExample.xaml#stringanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://go.microsoft.com/fwlink/?LinkID=160012).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.Animation.StringAnimationUsingKeyFrames>
- <xref:System.Windows.Controls.ContentControl.Content%2A>
- <xref:System.Windows.Controls.Button>
- <xref:System.Windows.Media.Animation.DiscreteStringKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
