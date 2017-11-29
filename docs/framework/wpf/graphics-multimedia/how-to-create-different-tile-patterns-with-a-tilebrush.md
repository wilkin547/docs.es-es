---
title: "Cómo: Crear patrones de mosaico diferentes con un objeto TileBrush"
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
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6247f6a16cd8ab7be683d0d4d33aac021f3a2b32
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Cómo: Crear patrones de mosaico diferentes con un objeto TileBrush
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de una <xref:System.Windows.Media.TileBrush> para crear un patrón.  
  
 El <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad le permite especificar cómo el contenido de un <xref:System.Windows.Media.TileBrush> se repite, es decir, en forma de mosaico para rellenar un área de salida. Para crear un modelo, puede establecer la <xref:System.Windows.Media.TileBrush.TileMode%2A> a <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>. También debe establecer el <xref:System.Windows.Media.TileBrush.Viewport%2A> de la <xref:System.Windows.Media.TileBrush> para que sea menor que el área que se está pintando; en caso contrario, solo un único mosaico es generado, sin tener en cuenta que <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración utilizada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea cinco <xref:System.Windows.Media.DrawingBrush> los objetos, les cada otra <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración y las utiliza para pintar cinco rectángulos. Aunque en este ejemplo se usa el <xref:System.Windows.Media.DrawingBrush> clase para mostrar <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamiento, el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad funciona de forma idéntica para todos los <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, y <xref:System.Windows.Media.DrawingBrush>.  
  
 En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![TileBrush en mosaico de salida de ejemplo](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Patrones de mosaico creados con la propiedad TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Vea también  
 [Establecer el tamaño del mosaico de un TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)  
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)
