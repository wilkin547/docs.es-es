---
title: Filtrar Reproducir elementos multimedia con animaciones
ms.date: 03/30/2017
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
ms.openlocfilehash: 200f9d62c67a02088fe5a5789cdb41a04837d430
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079908"
---
# <a name="how-to-play-media-with-animations"></a>Filtrar Reproducir elementos multimedia con animaciones
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
- [Información general sobre objetos Storyboard](storyboards-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Gráficos y multimedia](index.md)
