---
title: Procedimiento Reproducir elementos multimedia con un objeto VideoDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 2e2007525be770186a17cf9d2d42a7c52ba93fba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956955"
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="66283-102">Procedimiento Reproducir elementos multimedia con un objeto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="66283-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="66283-103">Para reproducir un archivo de audio o vídeo, use <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>y.</span><span class="sxs-lookup"><span data-stu-id="66283-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="66283-104">Hay dos maneras de cargar y reproducir elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="66283-104">There are two ways to load and play media.</span></span> <span data-ttu-id="66283-105">La <xref:System.Windows.Media.MediaPlayer> primera es usar una y una <xref:System.Windows.Media.VideoDrawing> por sí <xref:System.Windows.Media.MediaPlayer> misma, y la segunda consiste en crear la suya propia <xref:System.Windows.Media.MediaTimeline> para usarla con y <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="66283-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="66283-106">Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen.</span><span class="sxs-lookup"><span data-stu-id="66283-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="66283-107">En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.</span><span class="sxs-lookup"><span data-stu-id="66283-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66283-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66283-108">Example</span></span>  
 <span data-ttu-id="66283-109">En el ejemplo siguiente se <xref:System.Windows.Media.VideoDrawing> usa un <xref:System.Windows.Media.MediaPlayer> y un para reproducir un archivo de vídeo una vez.</span><span class="sxs-lookup"><span data-stu-id="66283-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="66283-110">Para obtener un <xref:System.Windows.Media.MediaTimeline> control de tiempo adicional sobre los medios, utilice con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y.</span><span class="sxs-lookup"><span data-stu-id="66283-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="66283-111"><xref:System.Windows.Media.MediaTimeline> Permite especificar si el vídeo debe repetirse.</span><span class="sxs-lookup"><span data-stu-id="66283-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="66283-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="66283-112">Example</span></span>  
 <span data-ttu-id="66283-113">En el ejemplo siguiente se <xref:System.Windows.Media.MediaTimeline> usa con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y para reproducir un vídeo repetidamente.</span><span class="sxs-lookup"><span data-stu-id="66283-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="66283-114">Tenga <xref:System.Windows.Media.MediaClock> en cuenta que, cuando se <xref:System.Windows.Media.MediaTimeline>usa un, se usa <xref:System.Windows.Media.Animation.ClockController> la interactiva <xref:System.Windows.Media.Animation.Clock.Controller%2A> devuelta desde la propiedad de para controlar la reproducción multimedia en lugar de <xref:System.Windows.Media.MediaPlayer>los métodos interactivos de.</span><span class="sxs-lookup"><span data-stu-id="66283-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66283-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="66283-115">See also</span></span>

- <xref:System.Windows.Media.VideoDrawing>
- [<span data-ttu-id="66283-116">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="66283-116">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
