---
title: Filtrar Crear patrones de mosaico diferentes con un objeto TileBrush
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TileBrush [WPF], creating tile patterns
- tile patterns [WPF], creating
- creating [WPF], tile patterns with TileBrush
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
ms.openlocfilehash: 2efd070ac9ad502f2539d100fa450f95bcdddced
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57367783"
---
# <a name="how-to-create-different-tile-patterns-with-a-tilebrush"></a>Filtrar Crear patrones de mosaico diferentes con un objeto TileBrush
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad de un <xref:System.Windows.Media.TileBrush> para crear un patrón.  
  
 El <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad le permite especificar cómo el contenido de un <xref:System.Windows.Media.TileBrush> se repite, es decir, en mosaico para rellenar un área de salida. Para crear un modelo, puede establecer el <xref:System.Windows.Media.TileBrush.TileMode%2A> a <xref:System.Windows.Media.TileMode.Tile>, <xref:System.Windows.Media.TileMode.FlipX>, <xref:System.Windows.Media.TileMode.FlipY>, o <xref:System.Windows.Media.TileMode.FlipXY>. También debe establecer el <xref:System.Windows.Media.TileBrush.Viewport%2A> de la <xref:System.Windows.Media.TileBrush> para que sea menor que el área que se está pintando; en caso contrario, solo un único mosaico está generado, independientemente que <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración utilizada.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se crea cinco <xref:System.Windows.Media.DrawingBrush> los objetos, proporciona a cada uno un diferentes <xref:System.Windows.Media.TileBrush.TileMode%2A> configuración y los usa para dibujar cinco rectángulos. Aunque este ejemplo usa el <xref:System.Windows.Media.DrawingBrush> clase para demostrar <xref:System.Windows.Media.TileBrush.TileMode%2A> comportamiento, el <xref:System.Windows.Media.TileBrush.TileMode%2A> propiedad funciona de forma idéntica para todas la <xref:System.Windows.Media.TileBrush> objetos, es decir, para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush>, y <xref:System.Windows.Media.DrawingBrush>.  
  
 En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![TileBrush en mosaico de salida de ejemplo](./media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm_DrawingBrushTileModeExample")  
Patrones de mosaico creados con la propiedad TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xaml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](~/samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## <a name="see-also"></a>Vea también
- [Establecer el tamaño del mosaico de un TileBrush](how-to-set-the-tile-size-for-a-tilebrush.md)
- [Pintar con imágenes, dibujos y elementos visuales](painting-with-images-drawings-and-visuals.md)
