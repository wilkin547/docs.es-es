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
ms.openlocfilehash: fb5fd3575a0caa692e4a4013452e3069210c9a4c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-with-animations"></a><span data-ttu-id="443b6-102">Cómo: Reproducir medios con animaciones</span><span class="sxs-lookup"><span data-stu-id="443b6-102">How to: Play Media with Animations</span></span>
<span data-ttu-id="443b6-103">Este ejemplo muestra cómo reproducir animaciones y multimedia al mismo tiempo mediante el <xref:System.Windows.Media.MediaTimeline> y <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> clases en el mismo <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="443b6-103">This example shows how to play media and animations at the same time by using the <xref:System.Windows.Media.MediaTimeline> and <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames> classes in the same <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="443b6-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="443b6-104">Example</span></span>  
 <span data-ttu-id="443b6-105">Puede usar uno o varios <xref:System.Windows.Media.MediaTimeline> objetos en un <xref:System.Windows.Media.Animation.Storyboard> junto con otros usuarios <xref:System.Windows.Media.Animation.Timeline> objetos, como las animaciones.</span><span class="sxs-lookup"><span data-stu-id="443b6-105">You can use one or more <xref:System.Windows.Media.MediaTimeline> objects in a <xref:System.Windows.Media.Animation.Storyboard> together with other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span>  
  
 <span data-ttu-id="443b6-106">El ejemplo siguiente se establece la <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> propiedad de la <xref:System.Windows.Media.Animation.Storyboard> en un valor de `Slip`, que especifica que la animación no avanza hasta que progresa el medio (vídeo en este ejemplo).</span><span class="sxs-lookup"><span data-stu-id="443b6-106">The following example sets the <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A> property of the <xref:System.Windows.Media.Animation.Storyboard> to a value of `Slip`, which specifies that the animation does not progress until the media (video in this example) progresses.</span></span> <span data-ttu-id="443b6-107">Esta funcionalidad puede ser necesaria si se retrasa la reproducción multimedia debido al tiempo de carga.</span><span class="sxs-lookup"><span data-stu-id="443b6-107">This functionality might be needed if media playback is delayed because of loading time.</span></span>  
  
 [!code-xaml[MediaGallery_snippet#MediaTimelinePlusAnimationExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snippet/CSharp/MediaTimelinePlusAnimationExample.xaml#mediatimelineplusanimationexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="443b6-108">Vea también</span><span class="sxs-lookup"><span data-stu-id="443b6-108">See Also</span></span>  
 <xref:System.Windows.Media.MediaTimeline>  
 <xref:System.Windows.Media.Animation.DoubleAnimationUsingKeyFrames>  
 <xref:System.Windows.Media.Animation.Storyboard>  
 <xref:System.Windows.Media.Animation.ParallelTimeline.SlipBehavior%2A>  
 [<span data-ttu-id="443b6-109">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="443b6-109">How-to Topics</span></span>](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)  
 [<span data-ttu-id="443b6-110">Información general sobre objetos Storyboard </span><span class="sxs-lookup"><span data-stu-id="443b6-110">Storyboards Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)  
 [<span data-ttu-id="443b6-111">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="443b6-111">Key-Frame Animations Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)  
 [<span data-ttu-id="443b6-112">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="443b6-112">Animation Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)  
 [<span data-ttu-id="443b6-113">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="443b6-113">Graphics and Multimedia</span></span>](../../../../docs/framework/wpf/graphics-multimedia/index.md)
