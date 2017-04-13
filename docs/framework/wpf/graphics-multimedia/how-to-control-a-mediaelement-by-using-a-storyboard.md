---
title: "C&#243;mo: Controlar un control MediaElement mediante un gui&#243;n gr&#225;fico | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controlar la reproducción multimedia, con guiones gráficos"
  - "multimedia, controlar la reproducción con guiones gráficos"
  - "multimedia, controlar la reproducción multimedia con guiones gráficos"
  - "reproducción multimedia, controlar con guiones gráficos"
  - "Guiones gráficos, controlar la reproducción multimedia con"
ms.assetid: 6128ca77-b826-4e36-b968-6f237157c543
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Controlar un control MediaElement mediante un gui&#243;n gr&#225;fico
En este ejemplo se muestra cómo controlar un control <xref:System.Windows.Controls.MediaElement> mediante una escala de tiempo <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard>.  
  
## Ejemplo  
 Al usar un objeto <xref:System.Windows.Media.MediaTimeline> en un <xref:System.Windows.Media.Animation.Storyboard> para controlar la temporización de un control <xref:System.Windows.Controls.MediaElement>, la funcionalidad es idéntica a la de otros objetos <xref:System.Windows.Media.Animation.Timeline>, como las animaciones.  Por ejemplo, un objeto <xref:System.Windows.Media.MediaTimeline> usa propiedades de <xref:System.Windows.Media.Animation.Timeline>, como la propiedad <xref:System.Windows.Media.Animation.Timeline.BeginTime%2A>, para especificar cuándo iniciar un <xref:System.Windows.Controls.MediaElement> \(iniciar la reproducción multimedia\).  También usa la propiedad <xref:System.Windows.Media.Animation.Timeline.Duration%2A> para especificar durante cuánto tiempo <xref:System.Windows.Controls.MediaElement> está activo \(duración de reproducción multimedia\).  Para obtener más información acerca del uso de objetos <xref:System.Windows.Media.Animation.Timeline> con un <xref:System.Windows.Media.Animation.Storyboard>, consulte [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md).  
  
 En este ejemplo se muestra cómo crear un reproductor multimedia simple que usa <xref:System.Windows.Media.MediaTimeline> para controlar la reproducción.  El reproductor multimedia incluye botones de reproducción, pausa, reanudación y detención.  El reproductor también tiene un control <xref:System.Windows.Controls.Slider> que actúa como una barra de progreso.  
  
 En el ejemplo siguiente se crea la [!INCLUDE[TLA#tla_ui](../../../../includes/tlasharptla-ui-md.md)] para el reproductor multimedia.  
  
 [!code-xml[MediaGallery_snip#MediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml#mediatimelineexamplewholepage)]  
  
 En el ejemplo siguiente se crea la funcionalidad de la barra de progreso.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaTimelineExample.xaml.cs#codebehindmediatimelineexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaTimelineExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaTimelineExample.xaml.vb#codebehindmediatimelineexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Controls.MediaElement>   
 <xref:System.Windows.Media.MediaTimeline>   
 <xref:System.Windows.Media.Animation.Storyboard>   
 [Controlar un MediaElement \(Reproducir, Pausar, Detener, Volumen y Velocidad\)](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-play-pause-stop-volume-and-speed.md)   
 [Información general sobre objetos Storyboard](../../../../docs/framework/wpf/graphics-multimedia/storyboards-overview.md)   
 [Información general sobre animaciones de fotogramas clave](../../../../docs/framework/wpf/graphics-multimedia/key-frame-animations-overview.md)   
 [Información general sobre animaciones](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/graphics-multimedia/audio-and-video-how-to-topics.md)   
 [Gráficos y multimedia](../../../../docs/framework/wpf/graphics-multimedia/index.md)