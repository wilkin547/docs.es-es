---
title: "C&#243;mo: Crear un arco el&#237;ptico | Microsoft Docs"
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
  - "arcos, elípticos"
  - "arcos elípticos, crear"
  - "gráficos [WPF], arcos elípticos"
ms.assetid: 3dcfe502-3485-45de-99fb-d53a1367c484
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear un arco el&#237;ptico
En este ejemplo se muestra cómo dibujar un arco elíptico.  Para crear un arco elíptico, utilice las clases <xref:System.Windows.Media.PathGeometry>, <xref:System.Windows.Media.PathFigure> y <xref:System.Windows.Media.ArcSegment>.  
  
## Ejemplo  
 En el ejemplo siguiente, se dibuja un arco elíptico desde \(10,100\) hasta \(200,100\).  Para este arco, el valor de <xref:System.Windows.Media.ArcSegment.Size%2A> es de 100 por 50 píxeles independientes del dispositivo, el valor de <xref:System.Windows.Media.ArcSegment.RotationAngle%2A> es de 45 grados, la propiedad <xref:System.Windows.Media.ArcSegment.IsLargeArc%2A> se establece en `true` y la propiedad <xref:System.Windows.Media.ArcSegment.SweepDirection%2A> se establece en <xref:System.Windows.Media.SweepDirection>.  
  
 \[xaml\]  
  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], puede utilizar la sintaxis de atributo para describir un trazado.  
  
 [!code-xml[GeometrySample#56](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/geometryattributesyntaxexample.xaml#56)]  
  
 \[xaml\]  
  
 \(Tenga en cuenta que, en realidad, esta sintaxis de atributo crea un objeto <xref:System.Windows.Media.StreamGeometry>, que es una versión ligera de <xref:System.Windows.Media.PathGeometry>.  Para obtener más información, vea la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).\)  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], también puede dibujar un arco elíptico utilizando explícitamente las etiquetas de objeto.  El código siguiente es equivalente al marcado [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] anterior.  
  
 [!code-xml[GeometrySample#36](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/pathgeometryexample.xaml#36)]  
  
 Este ejemplo forma parte de un ejemplo mayor.  Para obtener el ejemplo completo, vea [Geometries Sample](http://go.microsoft.com/fwlink/?LinkID=159989).  
  
## Vea también  
 [Crea una curva Bézier cuadrática.](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-quadratic-bezier-curve.md)   
 [Crear una curva Bézier cúbica](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-cubic-bezier-curve.md)