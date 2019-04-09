---
title: Filtrar Controlar un control MediaElement mediante un guión gráfico
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- multimedia [WPF], controlling playback of media with Storyboards
- controlling playback of media [WPF], with Storyboards
- Storyboards [WPF], controlling playback of media with
- media [WPF], controlling playback with Storyboards
- playback of media [WPF], controlling with Storyboards
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
ms.openlocfilehash: ae785e11b1da0f2c408b24021ad46ab071419378
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59100319"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Filtrar Controlar un control MediaElement mediante un guión gráfico
En este ejemplo se muestra cómo controlar un <xref:System.Windows.Controls.MediaElement> mediante el uso de un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Ejemplo  
 Cuando se usa un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> para controlar la temporización de un <xref:System.Windows.Controls.MediaElement>, la funcionalidad es idéntica a la funcionalidad de otros <xref:System.Windows.Media.Animation.Timeline> objetos, como animaciones. Por ejemplo, un <xref:System.Windows.Media.MediaTimeline> usa <xref:System.Windows.Media.Animation.Timeline> propiedades como el <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad para especificar cuándo se debe iniciar un <xref:System.Windows.Controls.MediaElement> (iniciar la reproducción multimedia). También usa el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para especificar cuánto tiempo el <xref:System.Windows.Controls.MediaElement> está activo (duración de reproducción multimedia). Para obtener más información sobre el uso de <xref:System.Windows.Media.Animation.Timeline> los objetos que tienen un <xref:System.Windows.Media.Animation.Storyboard>, consulte [Storyboards Overview](storyboards-overview.md).  
  
 En este ejemplo se muestra cómo crear un Reproductor de medios sencillo que usa un <xref:System.Windows.Media.MediaTimeline> para controlar la reproducción. El Reproductor multimedia incluye reproducir, pausar, reanudar y detener los botones. El Reproductor también tiene un <xref:System.Windows.Controls.Slider> control que actúa como una barra de progreso.  
  
 En el ejemplo siguiente se crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el Reproductor de medios.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 El ejemplo siguiente crea la funcionalidad de la barra de progreso.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [Información general sobre objetos Storyboard](storyboards-overview.md)
- [Información general sobre animaciones de fotogramas clave](key-frame-animations-overview.md)
- [Información general sobre animaciones](animation-overview.md)
- [Temas "Cómo..."](audio-and-video-how-to-topics.md)
- [Gráficos y multimedia](index.md)
