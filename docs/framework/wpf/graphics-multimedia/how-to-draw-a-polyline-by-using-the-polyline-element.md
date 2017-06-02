---
title: "C&#243;mo: Dibujar una polil&#237;nea mediante el uso del elemento Polyline | Microsoft Docs"
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
  - "líneas conectadas"
  - "dibujar, polilíneas"
  - "gráficos [WPF], polilíneas"
  - "líneas, conectadas (véase polilíneas)"
  - "polilíneas, dibujar"
ms.assetid: 65db8935-d047-4295-87c4-b427ff3ad293
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Dibujar una polil&#237;nea mediante el uso del elemento Polyline
En este ejemplo se muestra cómo dibujar una polilínea, que es una serie de líneas conectadas, mediante el elemento <xref:System.Windows.Shapes.Polyline>.  
  
 Para dibujar una polilínea, cree un elemento <xref:System.Windows.Shapes.Polyline> y use su propiedad <xref:System.Windows.Shapes.Polyline.Points%2A> para especificar los vértices de la forma.  Finalmente, use las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> para describir el contorno de la polilínea, porque una línea sin trazo es invisible.  
  
> [!NOTE]
>  Dado que el elemento <xref:System.Windows.Shapes.Polyline> no es una forma cerrada, la propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> no tiene ningún efecto, aun cuando cierre deliberadamente el contorno de la forma.  Para crear una forma cerrada con un <xref:System.Windows.Shapes.Shape.Fill%2A>, use un elemento <xref:System.Windows.Shapes.Polygon>.  
  
 En el ejemplo siguiente se dibujan dos elementos <xref:System.Windows.Shapes.Polyline> dentro de un objeto <xref:System.Windows.Controls.Canvas>.  
  
## Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista de pares de coordenadas X e Y separadas por comas delimitados por espacios.  
  
 [!code-xml[drawingwithshapeelements#PolylineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polylineexample.xaml#polylineexample1)]  
  
 Aunque en este ejemplo se usa <xref:System.Windows.Controls.Canvas> para contener las polilíneas, puede usar elementos de polilínea \(y todos los demás elementos de formas\) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Vea también  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Shapes.Polygon>   
 <xref:System.Windows.Shapes.Shape>   
 [Ejemplo Shape Elements](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)