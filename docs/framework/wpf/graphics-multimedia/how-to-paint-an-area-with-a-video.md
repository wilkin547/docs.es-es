---
title: "C&#243;mo: Pintar un &#225;rea con un v&#237;deo | Microsoft Docs"
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
  - "pinceles, pintar con un vídeo"
  - "pintar con un vídeo"
  - "vídeo, pintar con"
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Pintar un &#225;rea con un v&#237;deo
En este ejemplo se muestra cómo pintar un área con multimedia.  Una manera de pintar un área con multimedia es utilizar un control <xref:System.Windows.Controls.MediaElement> junto con un objeto <xref:System.Windows.Media.VisualBrush>.  Utilice el control <xref:System.Windows.Controls.MediaElement> para cargar y reproducir multimedia y, a continuación, utilícelo para establecer la propiedad <xref:System.Windows.Media.VisualBrush.Visual%2A> de <xref:System.Windows.Media.VisualBrush>.  Luego, puede utilizar <xref:System.Windows.Media.VisualBrush> para pintar un área con el contenido multimedia cargado.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan <xref:System.Windows.Controls.MediaElement> y <xref:System.Windows.Media.VisualBrush> para pintar el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de un control <xref:System.Windows.Controls.TextBlock> con vídeo.  En este ejemplo se establece la propiedad <xref:System.Windows.Controls.MediaElement.IsMuted%2A> de <xref:System.Windows.Controls.MediaElement> en `true` para que no genere ningún sonido.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## Ejemplo  
 Dado que <xref:System.Windows.Media.VisualBrush> hereda de la clase <xref:System.Windows.Media.TileBrush>, proporciona varios modos de mosaico.  Si establece la propiedad <xref:System.Windows.Media.TileBrush.TileMode%2A> de <xref:System.Windows.Media.VisualBrush> en <xref:System.Windows.Media.TileMode> y establece su propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A> en un valor menor que el área que se está pintando, puede crear un modelo en mosaico.  
  
 El ejemplo siguiente es idéntico al ejemplo anterior, salvo que <xref:System.Windows.Media.VisualBrush> genera un modelo a partir del vídeo.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Para obtener información sobre cómo agregar a su aplicación un archivo de contenido, como un archivo multimedia, vea [Archivos de recursos, contenido y datos de aplicaciones de WPF](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md).  Los archivos multimedia deben agregarse como archivos de contenido, no como archivos de recursos.  
  
## Vea también  
 <xref:System.Windows.Media.VisualBrush>   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Información general sobre objetos TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)   
 [Información general sobre multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)