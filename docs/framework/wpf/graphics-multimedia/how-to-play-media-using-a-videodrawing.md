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
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedimiento Reproducir elementos multimedia con un objeto VideoDrawing
Para reproducir un archivo de audio o vídeo, use <xref:System.Windows.Media.VideoDrawing> <xref:System.Windows.Media.MediaPlayer>y. Hay dos maneras de cargar y reproducir elementos multimedia. La <xref:System.Windows.Media.MediaPlayer> primera es usar una y una <xref:System.Windows.Media.VideoDrawing> por sí <xref:System.Windows.Media.MediaPlayer> misma, y la segunda consiste en crear la suya propia <xref:System.Windows.Media.MediaTimeline> para usarla con y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
> Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Windows.Media.VideoDrawing> usa un <xref:System.Windows.Media.MediaPlayer> y un para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener un <xref:System.Windows.Media.MediaTimeline> control de tiempo adicional sobre los medios, utilice con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y. <xref:System.Windows.Media.MediaTimeline> Permite especificar si el vídeo debe repetirse.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se <xref:System.Windows.Media.MediaTimeline> usa con <xref:System.Windows.Media.MediaPlayer> los <xref:System.Windows.Media.VideoDrawing> objetos y para reproducir un vídeo repetidamente.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga <xref:System.Windows.Media.MediaClock> en cuenta que, cuando se <xref:System.Windows.Media.MediaTimeline>usa un, se usa <xref:System.Windows.Media.Animation.ClockController> la interactiva <xref:System.Windows.Media.Animation.Clock.Controller%2A> devuelta desde la propiedad de para controlar la reproducción multimedia en lugar de <xref:System.Windows.Media.MediaPlayer>los métodos interactivos de.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.VideoDrawing>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
