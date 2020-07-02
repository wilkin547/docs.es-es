---
title: 'Cómo: Controlar un control MediaElement mediante un guión gráfico'
description: Controlar la reproducción de archivos multimedia mediante un guión gráfico en Windows Presentation Foundation (WPF). Considere este ejemplo para crear un reproductor multimedia sencillo.
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
ms.openlocfilehash: 5a5e41b9a28211495fd3374c1a51a655dd867bca
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853730"
---
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a>Cómo: Controlar un control MediaElement mediante un guión gráfico
En este ejemplo se muestra cómo controlar un <xref:System.Windows.Controls.MediaElement> mediante un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> .  
  
## <a name="example"></a>Ejemplo  
 Cuando se usa un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> para controlar la temporización de un <xref:System.Windows.Controls.MediaElement> , la funcionalidad es idéntica a la funcionalidad de otros <xref:System.Windows.Media.Animation.Timeline> objetos, como animaciones. Por ejemplo, <xref:System.Windows.Media.MediaTimeline> utiliza <xref:System.Windows.Media.Animation.Timeline> propiedades como la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad para especificar cuándo iniciar un <xref:System.Windows.Controls.MediaElement> (iniciar reproducción multimedia). También utiliza la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para especificar cuánto tiempo <xref:System.Windows.Controls.MediaElement> está activo (duración de la reproducción multimedia). Para obtener más información sobre <xref:System.Windows.Media.Animation.Timeline> el uso de objetos con <xref:System.Windows.Media.Animation.Storyboard> , vea [información general sobre guiones gráficos](storyboards-overview.md).  
  
 En este ejemplo se muestra cómo crear un reproductor multimedia sencillo que usa <xref:System.Windows.Media.MediaTimeline> para controlar la reproducción. El reproductor de media incluye botones Reproducir, pausar, reanudar y detener. El reproductor también tiene un <xref:System.Windows.Controls.Slider> control que actúa como barra de progreso.  
  
 En el ejemplo siguiente se crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el reproductor de media.  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 En el ejemplo siguiente se crea la funcionalidad de la barra de progreso.  
  
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
