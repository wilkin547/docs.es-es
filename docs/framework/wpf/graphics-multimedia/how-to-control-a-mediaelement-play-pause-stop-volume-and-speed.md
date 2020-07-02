---
title: 'Cómo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)'
description: Controlar la reproducción de elementos multimedia en Windows Presentation Foundation (WPF). Iniciar, detener, pausar, saltar atrás y ajustar el volumen y la velocidad.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- playback of media [WPF], controlling
- controlling playback of media [WPF]
- multimedia [WPF], controlling playback of media
- media [WPF], controlling playback of
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
ms.openlocfilehash: da846299eaa1e36b6e5caab08bc1f861e9f9c46d
ms.sourcegitcommit: b6a1869f97a37f11a68c90afde1a520a6887dcbc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "85853604"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Cómo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
En el ejemplo siguiente se muestra cómo controlar la reproducción de medios mediante <xref:System.Windows.Controls.MediaElement> . En el ejemplo se crea un reproductor multimedia sencillo que permite reproducir, pausar, detener y saltar hacia atrás y hacia delante en el medio, así como ajustar el volumen y la proporción de velocidad.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente crea la interfaz de usuario.  
  
> [!NOTE]
> La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedad de <xref:System.Windows.Controls.MediaElement> debe establecerse en para poder `Manual` detener, pausar y reproducir los medios interactivamente.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente implementa la funcionalidad de los controles de interfaz de usuario de ejemplo. Los <xref:System.Windows.Controls.MediaElement.Play%2A> <xref:System.Windows.Controls.MediaElement.Pause%2A> métodos, y <xref:System.Windows.Controls.MediaElement.Stop%2A> se usan para reproducir, pausar y detener el medio respectivamente. Cambiar la <xref:System.Windows.Controls.MediaElement.Position%2A> propiedad de <xref:System.Windows.Controls.MediaElement> le permite omitir el contenido multimedia. Por último, <xref:System.Windows.Controls.MediaElement.Volume%2A> las <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades y se usan para ajustar el volumen y la velocidad de reproducción del medio.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Controlar un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md)
