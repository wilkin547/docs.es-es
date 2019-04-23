---
title: Procedimiento Reproducir elementos multimedia con un objeto VideoDrawing
ms.date: 03/30/2017
helpviewer_keywords:
- playback of media [WPF]
- classes [WPF], MediaPlayer
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
ms.openlocfilehash: 186c9ae8167dafd09f029418c1d23f81f7a9e906
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59203618"
---
# <a name="how-to-play-media-using-a-videodrawing"></a>Procedimiento Reproducir elementos multimedia con un objeto VideoDrawing
Para reproducir un archivo de audio o vídeo, usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer>. Hay dos maneras de cargar y reproducir elementos multimedia. La primera consiste en utilizar un <xref:System.Windows.Media.MediaPlayer> y un <xref:System.Windows.Media.VideoDrawing> por su cuenta y la segunda manera consiste en crear sus propios <xref:System.Windows.Media.MediaTimeline> para usar con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer> para reproducir un archivo de vídeo una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para obtener el control de tiempo sobre los medios, use un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos. El <xref:System.Windows.Media.MediaTimeline> le permite especificar si se debe repetir el vídeo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos que se va a reproducir un vídeo varias veces.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, cuando se usa un <xref:System.Windows.Media.MediaTimeline>, usa el modo interactivo <xref:System.Windows.Media.Animation.ClockController> devuelto desde el <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de la <xref:System.Windows.Media.MediaClock> para controlar la reproducción multimedia en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.VideoDrawing>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
