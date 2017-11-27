---
title: "Cómo: Reproducir elementos multimedia con un objeto VideoDrawing"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2753db8e06c8c1b50c6e5cee17330d421e88511f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-play-media-using-a-videodrawing"></a><span data-ttu-id="4edae-102">Cómo: Reproducir elementos multimedia con un objeto VideoDrawing</span><span class="sxs-lookup"><span data-stu-id="4edae-102">How to: Play Media using a VideoDrawing</span></span>
<span data-ttu-id="4edae-103">Para reproducir un archivo de audio o vídeo, utilizar un <xref:System.Windows.Media.VideoDrawing> y <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="4edae-103">To play an audio or video file, you use a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer>.</span></span> <span data-ttu-id="4edae-104">Hay dos maneras de cargar y reproducir elementos multimedia.</span><span class="sxs-lookup"><span data-stu-id="4edae-104">There are two ways to load and play media.</span></span> <span data-ttu-id="4edae-105">La primera consiste en utilizar un <xref:System.Windows.Media.MediaPlayer> y un <xref:System.Windows.Media.VideoDrawing> por sí mismos y la segunda manera es crear sus propios <xref:System.Windows.Media.MediaTimeline> para usar con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.</span><span class="sxs-lookup"><span data-stu-id="4edae-105">The first is to use a <xref:System.Windows.Media.MediaPlayer> and a <xref:System.Windows.Media.VideoDrawing> by themselves, and the second way is to create your own <xref:System.Windows.Media.MediaTimeline> to use with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4edae-106">Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen.</span><span class="sxs-lookup"><span data-stu-id="4edae-106">When distributing media with your application, you cannot use a media file as a project resource, like you would an image.</span></span> <span data-ttu-id="4edae-107">En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.</span><span class="sxs-lookup"><span data-stu-id="4edae-107">In your project file, you must instead set the media type to `Content` and set `CopyToOutputDirectory` to `PreserveNewest` or `Always`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4edae-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4edae-108">Example</span></span>  
 <span data-ttu-id="4edae-109">En el ejemplo siguiente se usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer> para reproducir un archivo de vídeo de una vez.</span><span class="sxs-lookup"><span data-stu-id="4edae-109">The following example uses a <xref:System.Windows.Media.VideoDrawing> and a <xref:System.Windows.Media.MediaPlayer> to play a video file once.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 <span data-ttu-id="4edae-110">Para tener un control de tiempo adicionales sobre los medios, use un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos.</span><span class="sxs-lookup"><span data-stu-id="4edae-110">To gain additional timing control over the media, use a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects.</span></span> <span data-ttu-id="4edae-111">El <xref:System.Windows.Media.MediaTimeline> le permite especificar si se debe repetir el vídeo.</span><span class="sxs-lookup"><span data-stu-id="4edae-111">The <xref:System.Windows.Media.MediaTimeline> enables you to specify whether the video should repeat.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4edae-112">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4edae-112">Example</span></span>  
 <span data-ttu-id="4edae-113">En el ejemplo siguiente se usa un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos que se va a reproducir un vídeo varias veces.</span><span class="sxs-lookup"><span data-stu-id="4edae-113">The following example uses a <xref:System.Windows.Media.MediaTimeline> with the <xref:System.Windows.Media.MediaPlayer> and <xref:System.Windows.Media.VideoDrawing> objects to play a video repeatedly.</span></span>  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 <span data-ttu-id="4edae-114">Tenga en cuenta que, cuando se usa un <xref:System.Windows.Media.MediaTimeline>, usa el interactivo <xref:System.Windows.Media.Animation.ClockController> procedentes de la la <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de la <xref:System.Windows.Media.MediaClock> para controlar la reproducción de medios en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.</span><span class="sxs-lookup"><span data-stu-id="4edae-114">Note that, when you use a <xref:System.Windows.Media.MediaTimeline>, you use the interactive <xref:System.Windows.Media.Animation.ClockController> returned from the <xref:System.Windows.Media.Animation.Clock.Controller%2A> property of the <xref:System.Windows.Media.MediaClock> to control media playback instead of the interactive methods of <xref:System.Windows.Media.MediaPlayer>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4edae-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="4edae-115">See Also</span></span>  
 <xref:System.Windows.Media.VideoDrawing>  
 [<span data-ttu-id="4edae-116">Información general sobre objetos Drawing</span><span class="sxs-lookup"><span data-stu-id="4edae-116">Drawing Objects Overview</span></span>](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
