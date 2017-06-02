---
title: "C&#243;mo: Crear una curva B&#233;zier cuadr&#225;tica | Microsoft Docs"
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
  - "curvas Bézier, crear"
  - "gráficos [WPF], curvas Bézier cuadráticas"
  - "curvas Bézier cuadráticas, crear"
ms.assetid: cd8fca4a-504e-4fd8-92ea-2969065a6e02
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear una curva B&#233;zier cuadr&#225;tica
En este ejemplo se muestra cómo crear una curva Bézier cuadrática.  Para crear una curva Bézier cuadrática, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> y <xref:System.Windows.Media.QuadraticBezierSegment>.  
  
## Ejemplo  
 En los ejemplos siguientes, se dibuja una curva Bézier cuadrática desde \(10,100\) hasta \(300,100\).  El punto de control de la curva es \(200,200\).  
  
 \[xaml\]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de atributo para describir un trazado.  
  
 [!code-xml[GeometrySample#54](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#54)]  
  
 \[xaml\]  
  
 \(Tenga en cuenta que, en realidad, esta sintaxis de atributo crea un objeto <xref:System.Windows.Media.StreamGeometry>, que es una versión ligera de <xref:System.Windows.Media.PathGeometry>.  Para obtener más información, vea la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede dibujar también una curva Bézier cuadrática mediante la sintaxis de elementos de objeto.  El código siguiente equivale al ejemplo de [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-xml[GeometrySample#34](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#34)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Vea también  
 [Crear un arco elíptico](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-an-elliptical-arc.md)   
 [Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)