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
# <a name="how-to-play-media-using-a-videodrawing"></a>Cómo: Reproducir elementos multimedia con un objeto VideoDrawing
Para reproducir un archivo de audio o vídeo, utilizar un <xref:System.Windows.Media.VideoDrawing> y <xref:System.Windows.Media.MediaPlayer>. Hay dos maneras de cargar y reproducir elementos multimedia. La primera consiste en utilizar un <xref:System.Windows.Media.MediaPlayer> y un <xref:System.Windows.Media.VideoDrawing> por sí mismos y la segunda manera es crear sus propios <xref:System.Windows.Media.MediaTimeline> para usar con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Al distribuir elementos multimedia con la aplicación, no puede utilizar un archivo multimedia como recurso del proyecto, como haría con una imagen. En el archivo de proyecto, debe establecer en su lugar el tipo de elemento multimedia en `Content` y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.VideoDrawing> y un <xref:System.Windows.Media.MediaPlayer> para reproducir un archivo de vídeo de una vez.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para tener un control de tiempo adicionales sobre los medios, use un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos. El <xref:System.Windows.Media.MediaTimeline> le permite especificar si se debe repetir el vídeo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.MediaTimeline> con el <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> objetos que se va a reproducir un vídeo varias veces.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, cuando se usa un <xref:System.Windows.Media.MediaTimeline>, usa el interactivo <xref:System.Windows.Media.Animation.ClockController> procedentes de la la <xref:System.Windows.Media.Animation.Clock.Controller%2A> propiedad de la <xref:System.Windows.Media.MediaClock> para controlar la reproducción de medios en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.VideoDrawing>  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
