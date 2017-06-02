---
title: "C&#243;mo: Crear un dibujo compuesto | Microsoft Docs"
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
  - "clases, DrawingGroup"
  - "dibujos compuestos"
  - "DrawingGroup (clase)"
  - "dibujos, compuestos"
  - "gráficos, dibujos compuestos"
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un dibujo compuesto
En este ejemplo se muestra cómo utilizar un objeto <xref:System.Windows.Media.DrawingGroup> para crear dibujos complejos combinando varios objetos <xref:System.Windows.Media.Drawing> en un mismo dibujo compuesto.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza <xref:System.Windows.Media.DrawingGroup> para crear un dibujo compuesto a partir de los objetos <xref:System.Windows.Media.GeometryDrawing> y <xref:System.Windows.Media.ImageDrawing>.  En la ilustración siguiente se muestra el resultado de aplicar este ejemplo.  
  
 ![DrawingGroup con varios dibujos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.png "graphicsmm\_simple")  
Dibujo compuesto creado mediante DrawingGroup  
  
 Observe el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Puede utilizar <xref:System.Windows.Media.DrawingGroup> para aplicar un valor de <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A>, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A> o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> a los dibujos que contiene.  Dado que <xref:System.Windows.Media.DrawingGroup> también es un objeto <xref:System.Windows.Media.Drawing>, puede contener otros objetos <xref:System.Windows.Media.DrawingGroup>.  
  
 El ejemplo siguiente es similar al anterior, pero utiliza objetos <xref:System.Windows.Media.DrawingGroup> adicionales para aplicar efectos de imagen y una máscara de opacidad a algunos de sus dibujos.  En la ilustración siguiente se muestra el resultado de aplicar este ejemplo.  
  
 ![DrawingGroup con varios dibujos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.png "graphicsmm\_multiple")  
Dibujo compuesto que tiene varios objetos DrawingGroup  
  
 Observe el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Para obtener más información acerca de los objetos <xref:System.Windows.Media.Drawing>, vea [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## Vea también  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>   
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>   
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>   
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>   
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>   
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>   
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)