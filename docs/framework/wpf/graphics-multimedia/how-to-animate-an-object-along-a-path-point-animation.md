---
title: "C&#243;mo: Animar un objeto a lo largo de un trazado (animaci&#243;n en punto) | Microsoft Docs"
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
  - "animación de objetos a lo largo del trazado (animación en punto)"
  - "animación en punto"
ms.assetid: 1fa3f817-35bc-41a1-b366-f5a20b70da0c
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Animar un objeto a lo largo de un trazado (animaci&#243;n en punto)
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> objeto para animar un <xref:System.Windows.Point> a lo largo de un trazado curvo.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se mueve una <xref:System.Windows.Media.EllipseGeometry> a lo largo de una ruta de acceso definida por un <xref:System.Windows.Media.PathGeometry>. La geometría de elipse <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad, que toma un <xref:System.Windows.Point> valor, especifica su posición; para mover la geometría de elipse, puede animar sus <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad. El ejemplo utiliza un <xref:System.Windows.Media.Animation.PointAnimationUsingPath> para animar el <xref:System.Windows.Media.EllipseGeometry> del objeto <xref:System.Windows.Media.EllipseGeometry.Center%2A> propiedad.  
  
 [!code-xml[PathAnimationGallery_snippet#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/pointanimationusingpathexample.xaml#pointanimationusingpathwholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/PointAnimationUsingPathExample.cs#pointanimationusingpathwholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#PointAnimationUsingPathWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/PointAnimationUsingPathExample.vb#pointanimationusingpathwholepage)]  
  
 Para obtener un ejemplo completo, vea [ejemplo Path Animation](http://go.microsoft.com/fwlink/?LinkID=160028).  
  
 La versión de código del ejemplo anterior utiliza un <xref:System.Windows.Media.Animation.Storyboard> para animar el <xref:System.Windows.Media.EllipseGeometry>, aunque se aplicó sólo una animación. Un <xref:System.Windows.Media.Animation.Storyboard> suele ser la manera más fácil de aplicar varias animaciones, porque estas animaciones pueden controlarse por el mismo <xref:System.Windows.Media.Animation.Storyboard>. Sin embargo, es una manera más fácil de aplicar una sola animación a una propiedad cuando se utiliza código usar el <xref:System.Windows.Media.Animation.Animatable.BeginAnimation%2A> método. Para obtener un ejemplo, vea [animar una propiedad sin utilizar un guión gráfico](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-a-property-without-using-a-storyboard.md).  
  
## <a name="see-also"></a>Vea también  
 [Ejemplo de animación de trazado](http://go.microsoft.com/fwlink/?LinkID=160028)   
 [Información general de animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)