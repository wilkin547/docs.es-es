---
title: "Cómo: Reproducir medios con animaciones"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- multimedia [WPF], playback with animations
- playback of media [WPF], with animations
- animation [WPF], media playback with
- media [WPF], playback with animations
ms.assetid: 8982b7b7-1c6c-4b24-8801-b328862975f5
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 44ebb89c25fc37292f82533c929aae44854db5c9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-play-media-with-animations"></a>Cómo: Reproducir medios con animaciones
Este ejemplo muestra cómo reproducir animaciones y multimedia al mismo tiempo mediante el <xref:System.Windows.Media.MediaTimeline> y <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> clases en el mismo <xref:System.Windows.Media.Animation.Storyboard>.  
  
## <a name="example"></a>Ejemplo  
 Puede usar uno o varios <xref:System.Windows.Media.MediaTimeline> objetos en un <xref:System.Windows.Media.Animation.Storyboard> junto con otros usuarios <xref:System.Windows.Media.Animation.Timeline> objetos, como las animaciones.  
  
 El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> propiedad de la <xref:System.Windows.Media.Animation.Storyboard> en un valor de `Slip`, que especifica que la animación no avanza hasta que progresa el medio (vídeo en este ejemplo). Esta funcionalidad puede ser necesaria si se retrasa la reproducción multimedia debido al tiempo de carga.  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [Información general sobre objetos Storyboard ](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)
