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
# <a name="how-to-control-a-mediaelement-by-using-a-storyboard"></a><span data-ttu-id="50050-102">Filtrar Controlar un control MediaElement mediante un guión gráfico</span><span class="sxs-lookup"><span data-stu-id="50050-102">How to: Control a MediaElement by Using a Storyboard</span></span>
<span data-ttu-id="50050-103">En este ejemplo se muestra cómo controlar un <xref:System.Windows.Controls.MediaElement> mediante el uso de un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard>.</span><span class="sxs-lookup"><span data-stu-id="50050-103">This example shows how to control a <xref:System.Windows.Controls.MediaElement> by using a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50050-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="50050-104">Example</span></span>  
 <span data-ttu-id="50050-105">Cuando se usa un <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> para controlar la temporización de un <xref:System.Windows.Controls.MediaElement>, la funcionalidad es idéntica a la funcionalidad de otros <xref:System.Windows.Media.Animation.Timeline> objetos, como animaciones.</span><span class="sxs-lookup"><span data-stu-id="50050-105">When you use a <xref:System.Windows.Media.MediaTimeline> in a <xref:System.Windows.Media.Animation.Storyboard> to control the timing of a <xref:System.Windows.Controls.MediaElement>, the functionality is identical to the functionality of other <xref:System.Windows.Media.Animation.Timeline> objects, such as animations.</span></span> <span data-ttu-id="50050-106">Por ejemplo, un <xref:System.Windows.Media.MediaTimeline> usa <xref:System.Windows.Media.Animation.Timeline> propiedades como el <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> propiedad para especificar cuándo se debe iniciar un <xref:System.Windows.Controls.MediaElement> (iniciar la reproducción multimedia).</span><span class="sxs-lookup"><span data-stu-id="50050-106">For example, a <xref:System.Windows.Media.MediaTimeline> uses <xref:System.Windows.Media.Animation.Timeline> properties like the <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A> property to specify when to start a <xref:System.Windows.Controls.MediaElement> (start media playback).</span></span> <span data-ttu-id="50050-107">También usa el <xref:System.Windows.Media.Animation.Timeline.Duration%2A> propiedad para especificar cuánto tiempo el <xref:System.Windows.Controls.MediaElement> está activo (duración de reproducción multimedia).</span><span class="sxs-lookup"><span data-stu-id="50050-107">It also uses the <xref:System.Windows.Media.Animation.Timeline.Duration%2A> property to specify how long the <xref:System.Windows.Controls.MediaElement> is active (duration of media playback).</span></span> <span data-ttu-id="50050-108">Para obtener más información sobre el uso de <xref:System.Windows.Media.Animation.Timeline> los objetos que tienen un <xref:System.Windows.Media.Animation.Storyboard>, consulte [Storyboards Overview](storyboards-overview.md).</span><span class="sxs-lookup"><span data-stu-id="50050-108">For more information about using <xref:System.Windows.Media.Animation.Timeline> objects with a <xref:System.Windows.Media.Animation.Storyboard>, see [Storyboards Overview](storyboards-overview.md).</span></span>  
  
 <span data-ttu-id="50050-109">En este ejemplo se muestra cómo crear un Reproductor de medios sencillo que usa un <xref:System.Windows.Media.MediaTimeline> para controlar la reproducción.</span><span class="sxs-lookup"><span data-stu-id="50050-109">This example shows how to create a simple media player that uses a <xref:System.Windows.Media.MediaTimeline> to control playback.</span></span> <span data-ttu-id="50050-110">El Reproductor multimedia incluye reproducir, pausar, reanudar y detener los botones.</span><span class="sxs-lookup"><span data-stu-id="50050-110">The media player includes play, pause, resume, and stop buttons.</span></span> <span data-ttu-id="50050-111">El Reproductor también tiene un <xref:System.Windows.Controls.Slider> control que actúa como una barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="50050-111">The player also has a <xref:System.Windows.Controls.Slider> control that acts as a progress bar.</span></span>  
  
 <span data-ttu-id="50050-112">En el ejemplo siguiente se crea el [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el Reproductor de medios.</span><span class="sxs-lookup"><span data-stu-id="50050-112">The following example creates the [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] for the media player.</span></span>  
  
 [!code-xaml[MediaGallery_snip#MediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 <span data-ttu-id="50050-113">El ejemplo siguiente crea la funcionalidad de la barra de progreso.</span><span class="sxs-lookup"><span data-stu-id="50050-113">The following example creates the functionality for the progress bar.</span></span>  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="50050-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="50050-114">See also</span></span>

- <xref:System.Windows.Controls.MediaElement>
- <xref:System.Windows.Media.MediaTimeline>
- <xref:System.Windows.Media.Animation.Storyboard>
- [<span data-ttu-id="50050-115">Controlar un control MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)</span><span class="sxs-lookup"><span data-stu-id="50050-115">Control a MediaElement (Play, Pause, Stop, Volume, and Speed)</span></span>](how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)
- [<span data-ttu-id="50050-116">Información general sobre objetos Storyboard</span><span class="sxs-lookup"><span data-stu-id="50050-116">Storyboards Overview</span></span>](storyboards-overview.md)
- [<span data-ttu-id="50050-117">Información general sobre animaciones de fotogramas clave</span><span class="sxs-lookup"><span data-stu-id="50050-117">Key-Frame Animations Overview</span></span>](key-frame-animations-overview.md)
- [<span data-ttu-id="50050-118">Información general sobre animaciones</span><span class="sxs-lookup"><span data-stu-id="50050-118">Animation Overview</span></span>](animation-overview.md)
- [<span data-ttu-id="50050-119">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="50050-119">How-to Topics</span></span>](audio-and-video-how-to-topics.md)
- [<span data-ttu-id="50050-120">Gráficos y multimedia</span><span class="sxs-lookup"><span data-stu-id="50050-120">Graphics and Multimedia</span></span>](index.md)
