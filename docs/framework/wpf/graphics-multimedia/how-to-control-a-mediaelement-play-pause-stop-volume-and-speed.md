---
title: Procedimiento Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
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
ms.openlocfilehash: bb7319fc7ccec0220cbd79a32d5d015f9f2422d0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182863"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedimiento Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
El ejemplo siguiente muestra cómo controlar la reproducción de medios mediante un <xref:System.Windows.Controls.MediaElement>. El ejemplo crea un Reproductor de medios sencillo que permite reproducir, pausar, detener y avanzar o retroceder en el medio así como ajustar la proporción de volumen y velocidad.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente crea la interfaz de usuario.  
  
> [!NOTE]
>  El <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedad de <xref:System.Windows.Controls.MediaElement> debe establecerse en `Manual` para poder detener de forma interactiva, pausar y reproducir el archivo multimedia.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente implementa la funcionalidad de los controles de interfaz de usuario de ejemplo. El <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A>, y <xref:System.Windows.Controls.MediaElement.Stop%2A> métodos se usan para reproducir, pausar y detener el elemento multimedia, respectivamente. Cambiar el <xref:System.Windows.Controls.MediaElement.Position%2A> propiedad de la <xref:System.Windows.Controls.MediaElement> permite omitir de los medios. Por último, el <xref:System.Windows.Controls.MediaElement.Volume%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades se utilizan para ajustar la velocidad de reproducción y el volumen de los medios.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Controlar un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md)
