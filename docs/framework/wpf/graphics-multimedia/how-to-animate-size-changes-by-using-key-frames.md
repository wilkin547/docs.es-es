---
title: 'Cómo: Animar los cambios de tamaño mediante fotogramas clave'
ms.date: 03/30/2017
helpviewer_keywords:
- key frames [WPF], animating size changes with
- animation [WPF], size changes with key frames
- size changes [WPF], animating with key frames
ms.assetid: 86bd2950-d4c9-4ec4-aa8d-7dc3ccadded4
ms.openlocfilehash: 42cecfc9df4304be4033ea39edc0517016de4a92
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "80344661"
---
# <a name="how-to-animate-size-changes-by-using-key-frames"></a>Cómo: Animar los cambios de tamaño mediante fotogramas clave
En este ejemplo se muestra cómo animar los cambios del tamaño mediante fotogramas clave.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames> siguiente se <xref:System.Windows.Media.ArcSegment.Size%2A> utiliza <xref:System.Windows.Media.ArcSegment>la clase para animar la propiedad de un archivo . Esta animación utiliza tres fotogramas clave de la siguiente manera:  
  
1. Durante el primer medio segundo de la <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> animación, utiliza una instancia de la clase para aumentar gradualmente el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.LinearSizeKeyFrame> clave lineales como crean una transición lineal suave entre los valores.  
  
2. Al final del siguiente medio segundo, utiliza <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> una instancia de la clase para aumentar repentinamente el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame> clave discretos como crear saltos repentinos entre valores, es decir, los cambios de tamaño se producen repentinamente y no son sutiles.  
  
3. Durante los últimos dos segundos, utiliza una instancia de la <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clase para aumentar el tamaño del arco. Los fotogramas <xref:System.Windows.Media.Animation.SplineSizeKeyFrame> clave de spline como crean una <xref:System.Windows.Media.Animation.SplineSizeKeyFrame.KeySpline%2A> transición variable entre los valores según los valores de la propiedad. En este ejemplo, el tamaño del arco aumenta lentamente al principio y va aumentando exponencialmente hacia el final del segmento temporal.  
  
 [!code-xaml[keyframes_snip#SizeAnimationUsingKeyFramesWholePage](~/samples/snippets/xaml/VS_Snippets_Wpf/keyframes_snip/XAML/SizeAnimationUsingKeyFramesExample.xaml#sizeanimationusingkeyframeswholepage)]  
  
 Para consultar el ejemplo completo, vea [Ejemplo de animación mediante fotogramas clave](https://github.com/microsoft/WPF-Samples/tree/master/Animation/KeyFrameAnimation).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.Animation.SizeAnimationUsingKeyFrames>
- <xref:System.Windows.Media.ArcSegment.Size%2A>
- <xref:System.Windows.Media.ArcSegment>
- <xref:System.Windows.Media.Animation.LinearSizeKeyFrame>
- <xref:System.Windows.Media.Animation.DiscreteSizeKeyFrame>
- <xref:System.Windows.Media.Animation.SplineSizeKeyFrame>
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Temas de procedimientos de fotogramas clave](key-frame-animation-how-to-topics.md)
