---
title: "C&#243;mo: Crear una forma utilizando StreamGeometry | Microsoft Docs"
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
  - "clases, StreamGeometry"
  - "gráficos [WPF], formas"
  - "formas, crear con la clase StreamGeometry"
  - "StreamGeometry (clase)"
ms.assetid: 08f7c8ce-074b-49cd-9aba-cc9592d4ee51
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear una forma utilizando StreamGeometry
<xref:System.Windows.Media.StreamGeometry> es la alternativa ligera a <xref:System.Windows.Media.PathGeometry> para la creación de formas geométricas.  Utilice un objeto <xref:System.Windows.Media.StreamGeometry> cuando necesite describir una geometría compleja pero no desee la sobrecarga que implica la compatibilidad con el enlace de datos, la animación o la modificación.  Por ejemplo, debido a su eficacia, la clase <xref:System.Windows.Media.StreamGeometry> es una buena opción para describir adornos.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza la sintaxis de atributo para crear una <xref:System.Windows.Media.StreamGeometry> triangular en [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  
  
 [!code-xml[GeometriesMiscSnippets_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/xaml/VS_Snippets_Wpf/GeometriesMiscSnippets_snip/XAML/StreamGeometryExample.xaml#streamgeometrytriangleexamplewholepage)]  
  
 Para obtener más información sobre la sintaxis del atributo <xref:System.Windows.Media.StreamGeometry>, consulte la página [Sintaxis de marcado de trazados](../../../../docs/framework/wpf/graphics-multimedia/path-markup-syntax.md).  
  
## Ejemplo  
 El ejemplo siguiente utiliza un objeto <xref:System.Windows.Media.StreamGeometry> para definir un triángulo en el código.  En primer lugar, el ejemplo crea un objeto <xref:System.Windows.Media.StreamGeometry>, a continuación obtiene un objeto <xref:System.Windows.Media.StreamGeometryContext> y lo utiliza para describir el triángulo.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryTriangleExample.cs#streamgeometrytriangleexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryTriangleExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometrytriangleexample.vb#streamgeometrytriangleexamplewholepage)]  
  
## Ejemplo  
 El ejemplo siguiente crea un método que utiliza un objeto <xref:System.Windows.Media.StreamGeometry> y un objeto <xref:System.Windows.Media.StreamGeometryContext> para definir una forma geométrica basada en los parámetros especificados.  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/StreamGeometryExample.cs#streamgeometryexamplewholepage)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#StreamGeometryExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/streamgeometryexample.vb#streamgeometryexamplewholepage)]  
  
## Vea también  
 <xref:System.Windows.Media.PathGeometry>   
 <xref:System.Windows.Media.StreamGeometry>   
 <xref:System.Windows.Media.StreamGeometryContext>   
 [Crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md)   
 [Información general sobre geometría](../../../../docs/framework/wpf/graphics-multimedia/geometry-overview.md)