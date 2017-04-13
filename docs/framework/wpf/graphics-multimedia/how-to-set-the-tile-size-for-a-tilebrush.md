---
title: "C&#243;mo: Establecer el tama&#241;o del mosaico de un TileBrush | Microsoft Docs"
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
  - "TileBrush, tamaño de los mosaicos"
  - "Viewport (propiedad de TileBrush)"
ms.assetid: 04f41090-1b46-4e36-832f-d27d28708b8c
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Establecer el tama&#241;o del mosaico de un TileBrush
En este ejemplo se muestra cómo establecer el tamaño del mosaico para <xref:System.Windows.Media.TileBrush>.  De manera predeterminada, <xref:System.Windows.Media.TileBrush> genera un mosaico único que rellena completamente el área que se está pintando.  Puede invalidar este comportamiento estableciendo las propiedades <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A>.  
  
 La propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A> especifica el tamaño del mosaico para <xref:System.Windows.Media.TileBrush>.  De manera predeterminada, el valor de la propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A> es relativo al tamaño del área que se está pintando.  Para que la propiedad <xref:System.Windows.Media.TileBrush.Viewport%2A> especifique un tamaño del mosaico absoluto, establezca la propiedad <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> en <xref:System.Windows.Media.BrushMappingMode>.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.ImageBrush>, un tipo de <xref:System.Windows.Media.TileBrush>, para pintar un rectángulo con mosaicos.  En el ejemplo se establece el área de salida de cada mosaico en el 50% del alto y del ancho \(el rectángulo\).  Como resultado, el rectángulo se pintado con cuatro proyecciones de la imagen.  
  
 En la ilustración siguiente se muestra el resultado de aplicar el ejemplo.  
  
 ![Ejemplo de disposición en mosaico con un pincel de imagen](../../../../docs/framework/wpf/graphics-multimedia/media/0.png "0")  
  
 [!code-csharp[UsingImageBrush_snip#RelativeTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#relativetilesizeexample)]  
  
 En el ejemplo siguiente se crea <xref:System.Windows.Media.ImageBrush>, se establece <xref:System.Windows.Media.TileBrush.Viewport%2A> en `0,0,25,25` y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> en <xref:System.Windows.Media.BrushMappingMode>, y se lo utiliza para pintar otro rectángulo.  Como resultado, el pincel genera mosaicos que tienen un ancho de 25 [píxeles](GTMT) y un alto de 25 [píxeles](GTMT).  
  
 En la ilustración siguiente se muestra el resultado de aplicar el ejemplo.  
  
 ![TileBrush en mosaico con una ventanilla de 0,0,0.25,0.25](../../../../docs/framework/wpf/graphics-multimedia/media/25x25viewport.png "25x25viewport")  
  
 [!code-csharp[UsingImageBrush_snip#AbsoluteTileSizeExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/TileSizeExample.cs#absolutetilesizeexample)]  
  
 Los ejemplos anteriores forman parte de un ejemplo mayor.  Para obtener el ejemplo completo, vea [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
 Aunque en este ejemplo se utiliza la clase <xref:System.Windows.Media.ImageBrush>, las propiedades <xref:System.Windows.Media.TileBrush.Viewport%2A> y <xref:System.Windows.Media.TileBrush.ViewportUnits%2A> se comportan exactamente igual para los demás objetos <xref:System.Windows.Media.TileBrush>, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>.  Para obtener más información sobre <xref:System.Windows.Media.ImageBrush> y los demás objetos <xref:System.Windows.Media.TileBrush>, consulte [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
## Vea también  
 <xref:System.Windows.Media.TileBrush>   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)   
 [Crear patrones de mosaico diferentes con un objeto TileBrush](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-different-tile-patterns-with-a-tilebrush.md)