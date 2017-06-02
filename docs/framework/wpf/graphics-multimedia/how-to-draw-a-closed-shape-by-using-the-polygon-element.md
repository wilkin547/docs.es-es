---
title: "C&#243;mo: Dibujar una forma cerrada utilizando el elemento Polygon | Microsoft Docs"
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
  - "formas cerradas, dibujar con elementos Polygon"
  - "dibujar, formas cerradas con elementos Polygon"
  - "gráficos, Polygon (elementos)"
  - "Polygon (elementos)"
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Dibujar una forma cerrada utilizando el elemento Polygon
En este ejemplo se muestra cómo dibujar una forma cerrada utilizando el elemento <xref:System.Windows.Shapes.Polygon>.  Para dibujar una forma cerrada, cree un elemento <xref:System.Windows.Shapes.Polygon> y utilice su propiedad <xref:System.Windows.Shapes.Polygon.Points%2A> para especificar los vértices de una forma.  Se dibuja automáticamente una línea que conecta los puntos primero y último.  Por último, especifique el relleno \(<xref:System.Windows.Shapes.Shape.Fill%2A>\), el trazo \(<xref:System.Windows.Shapes.Shape.Stroke%2A>\) o ambos.  
  
## Ejemplo  
 En el [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista de pares de coordenadas X e Y separadas por comas delimitados por espacios.  
  
 [!code-xml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Aunque en el ejemplo se utiliza <xref:System.Windows.Controls.Canvas> para contener los polígonos, puede utilizar los elementos Polygon \(y todos los demás elementos de formas\) con cualquier control <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).