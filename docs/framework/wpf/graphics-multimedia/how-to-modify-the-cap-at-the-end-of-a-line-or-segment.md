---
title: "C&#243;mo: Modificar el extremo en el final de una l&#237;nea o segmento | Microsoft Docs"
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
  - "gráficos, Shape (extremos)"
  - "Shape (elementos), extremos"
  - "Shape (elementos), extremos"
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Modificar el extremo en el final de una l&#237;nea o segmento
En este ejemplo se muestra cómo modificar la forma al principio o al fin de un elemento <xref:System.Windows.Shapes.Shape> abierto.  Para cambiar el remate inicial de un objeto <xref:System.Windows.Shapes.Shape> abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>.  Para cambiar el remate final de un objeto <xref:System.Windows.Shapes.Shape> abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>.  Para ver los remates de línea disponibles, vea la enumeración <xref:System.Windows.Media.PenLineCap>.  
  
> [!NOTE]
>  Esta propiedad sólo afecta a una forma abierta, como un elemento <xref:System.Windows.Shapes.Line>, un elemento <xref:System.Windows.Shapes.Polyline>o un elemento <xref:System.Windows.Shapes.Path> abierto.  
  
 En el ejemplo siguiente se dibujan cuatro elementos <xref:System.Windows.Shapes.Polyline> y utiliza un conjunto diferente de formas en los extremos de cada uno.  
  
## Ejemplo  
 [!code-xml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## Vea también  
 <xref:System.Windows.Shapes.Polyline>   
 <xref:System.Windows.Media.PenLineCap>