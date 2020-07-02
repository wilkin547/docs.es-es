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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="fb0e2-104">Cómo: Controlar un control MediaElement mediante un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="fb0e2-104">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="fb0e2-105">En este ejemplo se muestra cómo controlar un <xref:System.Windows.Controls.MediaElement> mediante un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> .</span><span class="sxs-lookup"><span data-stu-id="fb0e2-105">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fb0e2-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="fb0e2-106">Example</span></span>  
 <span data-ttu-id="fb0e2-107">Cuando se usa un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> para controlar la temporización de un <xref:System.Windows.Controls.MediaElement> , la funcionalidad es idéntica a la funcionalidad de otros <xref:System.Windows.Media.Animation.Timeline> objetos, como animaciones.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-107">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="fb0e2-108">Por ejemplo, <xref:System.Windows.Media.MediaTimeline> utiliza <xref:System.Windows.Media.Animation.Timeline> propiedades como la <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad para especificar cuándo iniciar un <xref:System.Windows.Controls.MediaElement> (iniciar reproducción multimedia).</span><span class="sxs-lookup"><span data-stu-id="fb0e2-108">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="fb0e2-109">También utiliza la <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para especificar cuánto tiempo <xref:System.Windows.Controls.MediaElement> está activo (duración de la reproducción multimedia).</span><span class="sxs-lookup"><span data-stu-id="fb0e2-109">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="fb0e2-110">Para obtener más información sobre <xref:System.Windows.Media.Animation.Timeline> el uso de objetos con <xref:System.Windows.Media.Animation.Storyboard> , vea [información general sobre guiones gráficos](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="fb0e2-110">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="fb0e2-111">En este ejemplo se muestra cómo crear un reproductor multimedia sencillo que usa <xref:System.Windows.Media.MediaTimeline> para controlar la reproducción.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-111">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="fb0e2-112">El reproductor de media incluye botones Reproducir, pausar, reanudar y detener.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-112">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="fb0e2-113">El reproductor también tiene un <xref:System.Windows.Controls.Slider> control que actúa como barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-113">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="fb0e2-114">En el ejemplo siguiente se crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el reproductor de media.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-114">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="fb0e2-115">En el ejemplo siguiente se crea la funcionalidad de la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="fb0e2-115">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fb0e2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb0e2-116">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="fb0e2-117">Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)</span><span class="sxs-lookup"><span data-stu-id="fb0e2-117">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="fb0e2-118">Información general sobre objetos Storyboard</span><span class="sxs-lookup"><span data-stu-id="fb0e2-118">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="fb0e2-119">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="fb0e2-119">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="fb0e2-120">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="fb0e2-120">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="fb0e2-121">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="fb0e2-121">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="fb0e2-122">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="fb0e2-122">Graphics and Multimedia</span></span>](index.md)
