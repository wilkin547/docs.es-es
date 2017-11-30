---
title: "Cómo: Pintar un área con un vídeo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- painting with a video [WPF]
- video [WPF], painting with
- brushes [WPF], painting with a video
ms.assetid: 04dd6600-4a6e-4b43-a93e-21cce7dfbcb8
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 362231bbd1f4e95c260370a99233b7e8c2617ca1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-paint-an-area-with-a-video"></a>Cómo: Pintar un área con un vídeo
Este ejemplo muestra cómo se pinta un área con multimedia. Una manera de pintar un área con multimedia es utilizar un <xref:System.Windows.Controls.MediaElement> junto con un <xref:System.Windows.Media.VisualBrush>. Utilice la <xref:System.Windows.Controls.MediaElement> para cargar y reproducir el archivo multimedia y, a continuación, usarla para definir la <xref:System.Windows.Media.VisualBrush.Visual%2A> propiedad de la <xref:System.Windows.Media.VisualBrush>. A continuación, puede usar el <xref:System.Windows.Media.VisualBrush> para pintar un área con el contenido multimedia cargado.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Controls.MediaElement> y un <xref:System.Windows.Media.VisualBrush> para pintar el <xref:System.Windows.Controls.TextBlock.Foreground%2A> de un <xref:System.Windows.Controls.TextBlock> control con vídeo. Este ejemplo se establece la <xref:System.Windows.Controls.MediaElement.IsMuted%2A> propiedad de la <xref:System.Windows.Controls.MediaElement> a `true` para que no genere ningún sonido.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundinline)]  
  
## <a name="example"></a>Ejemplo  
 Dado que <xref:System.Windows.Media.VisualBrush> hereda de la <xref:System.Windows.Media.TileBrush> (clase), proporciona varios modos de mosaico. Estableciendo la <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de un <xref:System.Windows.Media.VisualBrush> a <xref:System.Windows.Media.TileMode.Tile> y estableciendo su <xref:System.Windows.Media.TileBrush.Viewport%2A> propiedad en un valor menor que el área que se está pintando, puede crear un modelo en mosaico.  
  
 El ejemplo siguiente es idéntico al ejemplo anterior, salvo que la <xref:System.Windows.Media.VisualBrush> genera un modelo a partir del vídeo.  
  
 [!code-csharp[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/csharp/VS_Snippets_Wpf/visualbrush_markup_snip/CSharp/PaintWithVideoExample.cs#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-vb[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/visualbrush_markup_snip/visualbasic/paintwithvideoexample.vb#graphicsmmvideoastextbackgroundtiledinline)]
 [!code-xaml[Visualbrush_markup_snip#GraphicsMMVideoAsTextBackgroundTiledInline](../../../../samples/snippets/xaml/VS_Snippets_Wpf/visualbrush_markup_snip/XAML/PaintWithVideoExample.xaml#graphicsmmvideoastextbackgroundtiledinline)]  
  
 Para obtener información sobre cómo agregar un archivo de contenido, como un archivo de medios, para la aplicación, consulte [recursos de la aplicación de WPF, contenido y archivos de datos](../../../../docs/framework/wpf/app-development/wpf-application-resource-content-and-data-files.md). Cuando se agrega un archivo multimedia, debe agregarlo como un archivo de contenido, no como un archivo de recursos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.VisualBrush>  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)  
 [Información general sobre objetos TileBrush](../../../../docs/framework/wpf/graphics-multimedia/tilebrush-overview.md)  
 [Información general sobre multimedia](../../../../docs/framework/wpf/graphics-multimedia/multimedia-overview.md)
