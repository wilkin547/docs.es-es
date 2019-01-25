---
title: Procedimiento Desencadenar la reproducción de medios con un evento de usuario
ms.date: 03/30/2017
helpviewer_keywords:
- synchronizing media playback with events [WPF]
- playback of media [WPF], synchronizing with events
- media [WPF], synchronizing playback with events
- multimedia [WPF], synchronizing media playback with events
ms.assetid: c4dbe632-6e7f-4d7f-9df5-98737a758bc3
ms.openlocfilehash: 5244c63aea0747c3d0f8d5bdd71496ccd3dc44d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54530069"
---
# <a name="how-to-trigger-media-playback-with-a-user-event"></a>Procedimiento Desencadenar la reproducción de medios con un evento de usuario
En este ejemplo se muestra cómo sincronizar la reproducción de medios con un evento.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el <xref:System.Windows.Controls.MediaElement> control y el <xref:System.Windows.Media.MediaTimeline> clase para reproducir un sonido que se produce cuando el usuario hace clic en un <xref:System.Windows.Controls.Button>.  
  
 [!code-xaml[MediaGallery_snippet#SoundFromUserEventExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/SoundFromUserEventExample.xaml#soundfromusereventexamplewholepage)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.EventTrigger.RoutedEvent%2A>
- <xref:System.Windows.Media.Animation.Storyboard>
- [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)
- [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
