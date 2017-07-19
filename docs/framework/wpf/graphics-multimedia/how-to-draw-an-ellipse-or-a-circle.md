---
title: "C&#243;mo: Dibujar una elipse o un c&#237;rculo | Microsoft Docs"
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
  - "círculos, dibujar"
  - "dibujar círculos"
  - "dibujar elipses"
  - "elipses, dibujar"
  - "gráficos, dibujar círculos"
  - "gráficos, dibujar elipses"
ms.assetid: 99763b8c-bfc8-44be-8231-8a70daf5481a
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Dibujar una elipse o un c&#237;rculo
Este ejemplo muestra cómo dibujar elipses y círculos utilizando el elemento <xref:System.Windows.Shapes.Ellipse>.  Para dibujar una elipse, cree un elemento <xref:System.Windows.Shapes.Ellipse> y especifique su <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.  Utilice su propiedad <xref:System.Windows.Shapes.Shape.Fill%2A> para especificar el objeto <xref:System.Windows.Media.Brush> que se utiliza para pintar el interior de la elipse.  Utilice su propiedad <xref:System.Windows.Shapes.Shape.Stroke%2A> para especificar el objeto <xref:System.Windows.Media.Brush> que se utiliza para pintar el contorno de la elipse.  La propiedad <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> especifica el grosor del contorno de la elipse.  
  
 Para dibujar un círculo, haga que los valores <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A> del elemento <xref:System.Windows.Shapes.Ellipse> sean iguales entre sí.  
  
 El ejemplo siguiente dibuja cuatro elementos <xref:System.Windows.Shapes.Ellipse> dentro de un objeto <xref:System.Windows.Controls.Canvas>.  
  
## Ejemplo  
 [!code-xml[drawingwithshapeelements#EllipseExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/ellipseexample.xaml#ellipseexample1)]  
  
 Aunque en este ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener las elipses, puede usar elementos de elipse \(y todos los demás elementos de formas\) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Vea también  
 <xref:System.Windows.Shapes.Ellipse>   
 <xref:System.Windows.Shapes.Shape>   
 [Ejemplo Shape Elements](http://go.microsoft.com/fwlink/?LinkID=160037)