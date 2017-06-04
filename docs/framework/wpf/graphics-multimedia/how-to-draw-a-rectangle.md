---
title: "C&#243;mo: Dibujar un rect&#225;ngulo | Microsoft Docs"
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
  - "dibujar, rectángulos"
  - "gráficos [WPF], rectángulos"
  - "rectángulos, dibujar"
ms.assetid: beeb57ef-fab5-4446-a38a-1588f97b4c2f
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Dibujar un rect&#225;ngulo
En este ejemplo se muestra cómo dibujar un rectángulo utilizando el elemento <xref:System.Windows.Shapes.Rectangle>.  
  
 Para dibujar un rectángulo, cree un elemento <xref:System.Windows.Shapes.Rectangle> y especifique sus propiedades <xref:System.Windows.FrameworkElement.Width%2A> y <xref:System.Windows.FrameworkElement.Height%2A>.  Para pintar el interior del rectángulo, establezca su propiedad <xref:System.Windows.Shapes.Shape.Fill%2A>.  Para dar un contorno al rectángulo, utilice las propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>.  
  
 Para proporcionar al rectángulo esquinas redondeadas, especifique las propiedades opcionales <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A>.  Las propiedades <xref:System.Windows.Shapes.Rectangle.RadiusX%2A> y <xref:System.Windows.Shapes.Rectangle.RadiusY%2A> establecen los radios del eje x y el eje y de la elipse utilizada para redondear las esquinas del rectángulo.  
  
 En el ejemplo siguiente, se dibujan dos elementos <xref:System.Windows.Shapes.Rectangle> en un control <xref:System.Windows.Controls.Canvas>.  El primer rectángulo tiene un interior <xref:System.Windows.Media.Brushes.Blue%2A>.  El segundo rectángulo tiene un interior <xref:System.Windows.Media.Brushes.Blue%2A>, un contorno <xref:System.Windows.Media.Brushes.Black%2A> y las esquinas redondeadas.  
  
## Ejemplo  
 [!code-xml[drawingwithshapeelements#Rectangle1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/rectangleexample.xaml#rectangle1)]  
  
 Aunque en este ejemplo se utiliza <xref:System.Windows.Controls.Canvas> para contener los rectángulos, puede utilizar los elementos rectángulo \(y todos los demás elementos de formas\) con cualquier control <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea texto.  De hecho, los rectángulos son particularmente útiles para proporcionar fondos para partes de paneles de controles <xref:System.Windows.Controls.Grid>.  Para obtener un ejemplo, vea [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md).  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Vea también  
 <xref:System.Windows.Shapes.Rectangle>   
 [Ejemplo Shape Elements](http://go.microsoft.com/fwlink/?LinkID=160037)   
 [Información general sobre formas y dibujo básico en WPF](../../../../docs/framework/wpf/graphics-multimedia/shapes-and-basic-drawing-in-wpf-overview.md)   
 [Información general sobre tablas](../../../../docs/framework/wpf/advanced/table-overview.md)