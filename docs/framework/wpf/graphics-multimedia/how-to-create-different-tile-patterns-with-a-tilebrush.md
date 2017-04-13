---
title: "C&#243;mo: Crear patrones de mosaico diferentes con un objeto TileBrush | Microsoft Docs"
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
  - "crear, patrones de mosaico con TileBrush"
  - "patrones de mosaico, crear"
  - "TileBrush, crear patrones de mosaico"
ms.assetid: 5aa46632-3527-4668-9d8d-0375c8af28aa
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Crear patrones de mosaico diferentes con un objeto TileBrush
En este ejemplo se muestra cómo usar la propiedad <xref:System.Windows.Media.TileBrush.TileMode%2A> de <xref:System.Windows.Media.TileBrush> para crear un patrón.  
  
 La propiedad <xref:System.Windows.Media.TileBrush.TileMode%2A> permite especificar cómo se repite el contenido de un objeto <xref:System.Windows.Media.TileBrush>, es decir, en mosaico para rellenar una área de salida.  Para crear un patrón, <xref:System.Windows.Media.TileBrush.TileMode%2A> se establece en <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode>, <xref:System.Windows.Media.TileMode> o <xref:System.Windows.Media.TileMode>.  También se debe establecer la propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A> del objeto <xref:System.Windows.Media.TileBrush> para que sea menor que el área que está pintando; de lo contrario, sólo se genera un mosaico, independientemente del valor de <xref:System.Windows.Media.TileBrush.TileMode%2A> que se use.  
  
## Ejemplo  
 En el ejemplo siguiente se crean cinco objetos <xref:System.Windows.Media.DrawingBrush>, se proporciona a cada uno un valor de <xref:System.Windows.Media.TileBrush.TileMode%2A> diferente y se usan para pintar cinco rectángulos.  Aunque en este ejemplo se usa la clase <xref:System.Windows.Media.DrawingBrush> para mostrar el comportamiento de <xref:System.Windows.Media.TileBrush.TileMode%2A>, la propiedad <xref:System.Windows.Media.TileBrush.TileMode%2A> funciona de manera idéntica para todos los objetos <xref:System.Windows.Media.TileBrush>, es decir, para <xref:System.Windows.Media.ImageBrush>, <xref:System.Windows.Media.VisualBrush> y <xref:System.Windows.Media.DrawingBrush>.  
  
 En la ilustración siguiente se muestra el resultado de aplicar este ejemplo.  
  
 ![Resultado de ejemplo de disposición en mosaico TileBrush](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-drawingbrushtilemodeexample.png "graphicsmm\_DrawingBrushTileModeExample")  
Patrones de mosaico creados con la propiedad TileMode  
  
 [!code-csharp[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/BrushesIntroduction_snip/CSharp/TileModeExample.cs#graphicsmmdrawingbrushtilemodeexample)]
 [!code-vb[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/BrushesIntroduction_snip/visualbasic/tilemodeexample.vb#graphicsmmdrawingbrushtilemodeexample)]
 [!code-xml[BrushesIntroduction_snip#GraphicsMMDrawingBrushTileModeExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/BrushesIntroduction_snip/XAML/TileModeExample.xaml#graphicsmmdrawingbrushtilemodeexample)]  
  
## Vea también  
 [Establecer el tamaño del mosaico de un TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-set-the-tile-size-for-a-tilebrush.md)   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)