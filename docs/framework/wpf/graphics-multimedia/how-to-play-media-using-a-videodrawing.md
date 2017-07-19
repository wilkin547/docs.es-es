---
title: "C&#243;mo: Reproducir elementos multimedia con un objeto VideoDrawing | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "clases, MediaPlayer"
  - "clases, VideoDrawing"
  - "MediaPlayer (clase)"
  - "reproducción multimedia"
  - "VideoDrawing (clase)"
ms.assetid: 165d47ed-22ce-4ded-aa6a-aa9b7467de87
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Reproducir elementos multimedia con un objeto VideoDrawing
Para reproducir un archivo de audio o vídeo, se utiliza un objeto <xref:System.Windows.Media.VideoDrawing> y un objeto <xref:System.Windows.Media.MediaPlayer>.  Hay dos maneras de cargar y reproducir elementos multimedia.  La primera es utilizar <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> por sí solos; la segunda consiste en crear su propio objeto <xref:System.Windows.Media.MediaTimeline> para utilizarlo con <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  
  
> [!NOTE]
>  Al distribuir los objetos multimedia con la aplicación, no se puede usar ningún archivo multimedia como recurso del proyecto, como se haría con una imagen.  En lugar de ello, en el archivo del proyecto debe establecer en `Content` el tipo de medios y establecer `CopyToOutputDirectory` en `PreserveNewest` o `Always`.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan los objetos <xref:System.Windows.Media.VideoDrawing> y <xref:System.Windows.Media.MediaPlayer> para reproducir una vez un archivo de vídeo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#VideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#videodrawingexampleinline)]  
  
 Para controlar mejor el tiempo en los elementos multimedia, utilice un objeto <xref:System.Windows.Media.MediaTimeline> con los objetos <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing>.  <xref:System.Windows.Media.MediaTimeline> permite especificar si el vídeo se debe repetir.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.MediaTimeline> con los objetos <xref:System.Windows.Media.MediaPlayer> y <xref:System.Windows.Media.VideoDrawing> para reproducir repetidamente un vídeo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#RepeatingVideoDrawingExampleInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/VideoDrawingExample.cs#repeatingvideodrawingexampleinline)]  
  
 Tenga en cuenta que, al utilizar <xref:System.Windows.Media.MediaTimeline>, se utiliza el objeto <xref:System.Windows.Media.Animation.ClockController> interactivo devuelto de la propiedad <xref:System.Windows.Media.Animation.Clock.Controller%2A> de <xref:System.Windows.Media.MediaClock> para controlar la reproducción multimedia, en lugar de los métodos interactivos de <xref:System.Windows.Media.MediaPlayer>.  
  
## Vea también  
 <xref:System.Windows.Media.VideoDrawing>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)