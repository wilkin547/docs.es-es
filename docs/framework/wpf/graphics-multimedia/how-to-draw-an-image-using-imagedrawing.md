---
title: "C&#243;mo: Dibujar una imagen usando un objeto ImageDrawing | Microsoft Docs"
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
  - "clases, ImageDrawing"
  - "dibujar, imágenes"
  - "gráficos, dibujar imágenes"
  - "ImageDrawing (clase)"
  - "imágenes, dibujar"
ms.assetid: df28ab41-25fb-4ab3-b51d-7f695b24f55e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Dibujar una imagen usando un objeto ImageDrawing
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.ImageDrawing> para dibujar una imagen.  Un objeto <xref:System.Windows.Media.ImageDrawing> permite mostrar un objeto <xref:System.Windows.Media.ImageSource> con un objeto <xref:System.Windows.Media.DrawingBrush>, <xref:System.Windows.Media.DrawingImage> o <xref:System.Windows.Media.Visual>.  Para dibujar una imagen, se crea un objeto <xref:System.Windows.Media.ImageDrawing> y se establecen sus propiedades <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> y <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName>.  La propiedad <xref:System.Windows.Media.ImageDrawing.ImageSource%2A?displayProperty=fullName> especifica la imagen que se va a dibujar, y la propiedad <xref:System.Windows.Media.ImageDrawing.Rect%2A?displayProperty=fullName> especifica la posición y el tamaño de cada imagen.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un dibujo compuesto mediante cuatro objetos <xref:System.Windows.Media.ImageDrawing>.  Este ejemplo genera la imagen siguiente.  
  
 ![Varios objetos DrawingImage](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-imagedrawingexample.png "graphicsmm\_ImageDrawingExample")  
Cuatro objetos ImageDrawing  
  
 [!code-csharp[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/ImageDrawingExample.cs#imagedrawingexample)]
 [!code-xml[DrawingMiscSnippets_snip#ImageDrawingExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/ImageDrawingExample.xaml#imagedrawingexample)]  
  
 Para obtener un ejemplo que muestra una manera simple de mostrar una imagen sin utilizar <xref:System.Windows.Media.ImageDrawing>, vea [Usar el elemento de imagen](../../../../docs/framework/wpf/controls/how-to-use-the-image-element.md).  
  
## Vea también  
 <xref:System.Windows.Freezable.Freeze%2A>   
 <xref:System.Windows.Controls.Image>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze \(Atributo\)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)