---
title: "C&#243;mo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad) | Microsoft Docs"
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
  - "controlar la reproducción multimedia"
  - "multimedia, controlar la reproducción de"
  - "multimedia, controlar la reproducción multimedia"
  - "reproducción multimedia, controlar"
ms.assetid: 6885a730-e054-4c16-8c1e-ffe17b1f7c32
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Controlar un MediaElement (Reproducir, Pausar, Detener, Volumen y Velocidad)
En el ejemplo siguiente se muestra cómo controlar la reproducción multimedia mediante un elemento <xref:System.Windows.Controls.MediaElement>.  En el ejemplo se crea un reproductor multimedia simple que permite reproducir, pausar, detener y avanzar o retroceder a saltos en el elemento multimedia, así como ajustar el volumen y el porcentaje de velocidad.  
  
## Ejemplo  
 En el código siguiente se crea la interfaz de usuario.  
  
> [!NOTE]
>  La propiedad <xref:System.Windows.Controls.MediaElement.LoadedBehavior%2A> de <xref:System.Windows.Controls.MediaElement> debe establecerse en `Manual` para ser que se pueda detener, pausar y reproducir el elemento multimedia de manera interactiva.  
  
 [!code-xml[MediaGallery_snip#MediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml#mediaelementexamplewholepage)]  
  
## Ejemplo  
 El código siguiente implementa la funcionalidad de los controles del ejemplo de interfaz de usuario.  Los métodos <xref:System.Windows.Controls.MediaElement.Play%2A>, <xref:System.Windows.Controls.MediaElement.Pause%2A> y <xref:System.Windows.Controls.MediaElement.Stop%2A> se utilizan respectivamente para reproducir, pausar y detener el elemento multimedia.  Cambiar la propiedad <xref:System.Windows.Controls.MediaElement.Position%2A> de <xref:System.Windows.Controls.MediaElement> permite avanzar o retroceder a saltos en el elemento multimedia.  Por último, se utilizan las propiedades <xref:System.Windows.Controls.MediaElement.Volume%2A> y <xref:System.Windows.Controls.MediaElement.SpeedRatio%2A> para ajustar el volumen y la velocidad de reproducción del elemento multimedia.  
  
 [!code-csharp[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/MediaGallery_snip/CSharp/MediaElementExample.xaml.cs#codebehindmediaelementexamplewholepage)]
 [!code-vb[MediaGallery_snip#CodeBehindMediaElementExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MediaGallery_snip/VB/MediaElementExample.xaml.vb#codebehindmediaelementexamplewholepage)]  
  
## Vea también  
 [Controlar un control MediaElement mediante un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-control-a-mediaelement-by-using-a-storyboard.md)