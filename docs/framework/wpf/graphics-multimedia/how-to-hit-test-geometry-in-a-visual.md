---
title: "C&#243;mo: Geometr&#237;a de una prueba de seguimiento en un objeto visual | Microsoft Docs"
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
  - "Geometry (objetos), objetos visuales que incluyen"
  - "prueba de visitas, en objetos visuales que incluyen objetos de geometría"
  - "objetos visuales, pruebas de posicionamiento en"
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Geometr&#237;a de una prueba de seguimiento en un objeto visual
En este ejemplo se muestra cómo realizar una [prueba de posicionamiento](GTMT) en un objeto visual compuesto de uno o más objetos <xref:System.Windows.Media.Geometry>.  
  
## Ejemplo  
 En el ejemplo siguiente se muestra cómo recuperar <xref:System.Windows.Media.DrawingGroup> de un objeto visual que utiliza el método <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A>.  A continuación, se realiza una prueba de posicionamiento en el contenido representado de cada dibujo de <xref:System.Windows.Media.DrawingGroup> para determinar a qué geometría se obtuvo acceso.  
  
> [!NOTE]
>  En la mayoría de los casos, se utiliza el método <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> para determinar si un punto interseca con cualquier parte del contenido representado de un objeto visual.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 El método <xref:System.Windows.Media.Geometry.FillContains%2A> es un método sobrecargado que permite realizar las pruebas de posicionamiento mediante un objeto <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry> especificado.  Si se traza una geometría, el trazo puede extenderse fuera del límite del relleno.  En cuyo caso, puede que sea conveniente llamar a <xref:System.Windows.Media.Geometry.StrokeContains%2A> además de a <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 También puede proporcionar un tipo <xref:System.Windows.Media.ToleranceType> que se utiliza para el aplanamiento de curvas Bézier.  
  
> [!NOTE]
>  En este ejemplo no se tiene en cuenta ninguna transformación ni recorte que se puede aplicar a la geometría.  Además, este ejemplo no funcionará con un control con estilo, puesto que no tiene ningún dibujo asociado directamente a él.  
  
## Vea también  
 [Realizar pruebas de posicionamiento en la capa visual](../../../../docs/framework/wpf/graphics-multimedia/hit-testing-in-the-visual-layer.md)   
 [Realizar una prueba de posicionamiento usando Geometry como parámetro](../../../../docs/framework/wpf/graphics-multimedia/how-to-hit-test-using-geometry-as-a-parameter.md)