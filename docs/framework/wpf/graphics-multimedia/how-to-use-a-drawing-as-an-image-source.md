---
title: "C&#243;mo: Usar un dibujo como el origen de una imagen | Microsoft Docs"
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
  - "dibujos, como orígenes de imagen"
  - "gráficos, dibujos, como orígenes de imagen"
  - "orígenes de imagen, dibujos"
ms.assetid: dcf71c7b-9e86-4b8e-8e39-0d0ce0389ef4
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Usar un dibujo como el origen de una imagen
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.Drawing> como la propiedad <xref:System.Windows.Controls.Image.Source%2A> de un control <xref:System.Windows.Controls.Image>.  Para mostrar <xref:System.Windows.Media.Drawing> con un control <xref:System.Windows.Controls.Image>, utilice <xref:System.Windows.Media.DrawingImage> como propiedad <xref:System.Windows.Controls.Image.Source%2A> del control <xref:System.Windows.Controls.Image> y establezca la propiedad <xref:System.Windows.Media.DrawingImage.Drawing%2A?displayProperty=fullName> del objeto <xref:System.Windows.Media.DrawingImage> en el dibujo que desea mostrar.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza un objeto <xref:System.Windows.Media.DrawingImage> y un control <xref:System.Windows.Controls.Image> para mostrar <xref:System.Windows.Media.GeometryDrawing>.  Este ejemplo produce el siguiente resultado.  
  
 ![GeometryDrawing de dos elipses](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-geodraw.png "graphicsmm\_geodraw")  
Objeto DrawingImage  
  
 [!code-csharp[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingImageExample.cs#drawingimageexamplewholepage)]
 [!code-xml[DrawingMiscSnippets_snip#DrawingImageExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingImageExample.xaml#drawingimageexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Dibujar una imagen usando un objeto ImageDrawing](../../../../docs/framework/wpf/graphics-multimedia/how-to-draw-an-image-using-imagedrawing.md)   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [PresentationOptions:Freeze \(Atributo\)](../../../../docs/framework/wpf/advanced/presentationoptions-freeze-attribute.md)