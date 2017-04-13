---
title: "C&#243;mo: Dibujar una l&#237;nea | Microsoft Docs"
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
  - "dibujar, líneas"
  - "gráficos [WPF], líneas"
  - "líneas, dibujar"
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Dibujar una l&#237;nea
En este ejemplo se muestra cómo dibujar líneas mediante el elemento <xref:System.Windows.Shapes.Line>.  
  
 Para dibujar una línea, cree un elemento <xref:System.Windows.Shapes.Line>.  Utilice sus propiedades <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> para establecer el punto de inicio; y utilice sus propiedades <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> para establecer el punto final.  Por último, establezca sus propiedades <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A>, ya que una línea sin trazo no es visible.  
  
 Establecer el elemento <xref:System.Windows.Shapes.Shape.Fill%2A> para una línea no surte ningún efecto, porque una línea no tiene interior.  
  
 En el ejemplo siguiente se dibujan tres líneas dentro de un elemento <xref:System.Windows.Controls.Canvas>.  
  
## Ejemplo  
 [!code-xml[drawingwithshapeelements#LineExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Vea también  
 <xref:System.Windows.Shapes.Line>   
 [Ejemplo Shape Elements](http://go.microsoft.com/fwlink/?LinkID=160037)