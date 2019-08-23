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
ms.openlocfilehash: cde7c32b48dff3d6d054e700b2f95771ba3b3773
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930164"
---
# <a name="how-to-control-a-mediaelement-play-pause-stop-volume-and-speed"></a>Procedimiento Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
En el ejemplo siguiente se muestra cómo controlar la reproducción de medios <xref:System.Windows.Controls.MediaElement>mediante. En el ejemplo se crea un reproductor multimedia sencillo que permite reproducir, pausar, detener y saltar hacia atrás y hacia delante en el medio, así como ajustar el volumen y la proporción de velocidad.  
  
## <a name="example"></a>Ejemplo  
 El código siguiente crea la interfaz de usuario.  
  
> [!NOTE]
> La <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> propiedad de <xref:System.Windows.Controls.MediaElement> debe establecerse en `Manual` para poder detener, pausar y reproducir los medios interactivamente.  
  
 [!code-xaml[MediaGallery_snip#MediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## <a name="example"></a>Ejemplo  
 El código siguiente implementa la funcionalidad de los controles de interfaz de usuario de ejemplo. Los <xref:System.Windows.Controls.MediaElement.Play%2A>métodos <xref:System.Windows.Controls.MediaElement.Pause%2A>, y<xref:System.Windows.Controls.MediaElement.Stop%2A> se usan para reproducir, pausar y detener el medio respectivamente. Cambiar la <xref:System.Windows.Controls.MediaElement.Position%2A> propiedad <xref:System.Windows.Controls.MediaElement> de le permite omitir el contenido multimedia. Por último, <xref:System.Windows.Controls.MediaElement.Volume%2A> las <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> propiedades y se usan para ajustar el volumen y la velocidad de reproducción del medio.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## <a name="see-also"></a>Vea también

- [Controlar un control MediaElement mediante un guión gráfico](how-to-control-a-mediaelement-by-using-a-storyboard.md)
