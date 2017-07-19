---
title: "C&#243;mo: Conservar la relaci&#243;n de aspecto de una imagen utilizada como fondo | Microsoft Docs"
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
  - "relaciones de aspecto de las imágenes de fondo, conservar"
  - "imágenes de fondo, conservar relaciones de aspecto"
  - "pinceles, conservar relaciones de aspecto de imágenes de fondo"
ms.assetid: 28c39478-13d7-4011-80a3-8b9cc3e54478
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Conservar la relaci&#243;n de aspecto de una imagen utilizada como fondo
En este ejemplo se muestra cómo utilizar la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> de <xref:System.Windows.Media.ImageBrush> para conservar la [relación de aspecto](GTMT) de la imagen.  
  
 De manera predeterminada, cuando se utiliza un <xref:System.Windows.Media.ImageBrush> para pintar una área, su contenido se expande hasta rellenar completamente el área de salida.  Cuando el área de salida y la imagen tienen [relaciones de aspecto](GTMT) diferentes, la imagen queda distorsionada al ajustarse.  
  
 Para que <xref:System.Windows.Media.ImageBrush> conserve la relación de aspecto de su imagen, establezca la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> en <xref:System.Windows.Media.Stretch> o <xref:System.Windows.Media.Stretch>.  
  
## Ejemplo  
 En el ejemplo siguiente se utilizan dos objetos <xref:System.Windows.Media.ImageBrush> para pintar dos rectángulos.  Cada rectángulo es de 300 por 150 [píxeles](GTMT) y cada uno de ellos contiene una imagen de 300 por 300 píxeles.  La propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> del primer pincel se establece en <xref:System.Windows.Media.Stretch>, y la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> del segundo pincel se establece en <xref:System.Windows.Media.Stretch>.  
  
 [!code-csharp[UsingImageBrush_snip#ImageBrushStretchModesExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/UsingImageBrush_snip/CSharp/StretchModes.cs#imagebrushstretchmodesexamplewholepage)]  
  
 En la ilustración siguiente se muestra la salida del primer pincel, cuya propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> está establecida en el valor <xref:System.Windows.Media.Stretch>.  
  
 ![ImageBrush con ajuste uniforme](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformstretch.png "graphicsmm\_ImageBrushUniformStretch")  
  
 En la ilustración siguiente se muestra la salida del segundo pincel, cuya propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> está establecida en el valor <xref:System.Windows.Media.Stretch>.  
  
 ![ImageBrush con ajuste UniformToFill](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagebrushuniformtofillstretch.png "graphicsmm\_ImageBrushUniformToFillStretch")  
  
 Observe que la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> se comporta exactamente igual para los demás objetos <xref:System.Windows.Media.TileBrush>, es decir, para <xref:System.Windows.Media.DrawingBrush> y <xref:System.Windows.Media.VisualBrush>.  Para obtener más información sobre <xref:System.Windows.Media.ImageBrush> y los demás objetos <xref:System.Windows.Media.TileBrush>, consulte [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md).  
  
 Asimismo, tenga en cuenta que, aunque parezca que la propiedad <xref:System.Windows.Media.TileBrush.Stretch%2A> especifica cómo se expandirá el contenido de <xref:System.Windows.Media.TileBrush> hasta ajustarse a su área de salida, en realidad especifica cómo se expande el contenido de <xref:System.Windows.Media.TileBrush> hasta rellenar su mosaico base.  Para obtener más información, consulte <xref:System.Windows.Media.TileBrush>.  
  
 Este ejemplo de código forma parte de un ejemplo más extenso proporcionado para la clase <xref:System.Windows.Media.ImageBrush>.  Para obtener el ejemplo completo, vea [ImageBrush Sample](http://go.microsoft.com/fwlink/?LinkID=160005).  
  
## Vea también  
 <xref:System.Windows.Media.TileBrush>   
 [Pintar con imágenes, dibujos y elementos visuales](../../../../docs/framework/wpf/graphics-multimedia/painting-with-images-drawings-and-visuals.md)