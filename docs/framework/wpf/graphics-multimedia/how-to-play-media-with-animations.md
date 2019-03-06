---
title: Procedimiento Reproducir medios con animaciones
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 0dc39d08ef17a628675018c17602623f2efd0173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57372911"
---
# <a name="how-to-play-media-with-animations"></a>Procedimiento Reproducir medios con animaciones
En este ejemplo se muestra cómo reproducir archivos multimedia y animaciones al mismo tiempo mediante la <xref:System.Windows.Media.MediaTimeline> y <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> clases en el mismo <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Ejemplo  
 Puede usar uno o varios <xref:System.Windows.Media.MediaTimeline> objetos en un <xref:System.Windows.Media.Animation.Storyboard> junto con otros usuarios <xref:System.Windows.Media.Animation.Timeline> objetos, como animaciones.  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> propiedad de la <xref:System.Windows.Media.Animation.Storyboard> en un valor de `Slip`, que especifica que la animación no avanza hasta que avanza la multimedia (el vídeo en este ejemplo). Esta funcionalidad puede ser necesaria si se retrasa la reproducción multimedia debido al tiempo de carga.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>
- <xref:System.Windows.Media.Animation.Storyboard>
- <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>
- [Temas "Cómo..."](audio-and-video-how-to-topics.md)
- [Información general sobre objetos Storyboard ](storyboards-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Gráficos y multimedia](index.md)
