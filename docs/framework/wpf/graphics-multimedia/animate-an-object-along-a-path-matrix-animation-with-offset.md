---
title: "C&#243;mo: Animar un objeto a lo largo de un trazado (animaci&#243;n en matriz con acumulaci&#243;n de desplazamiento) | Microsoft Docs"
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
  - "acumulación de desplazamiento"
  - "animación de objetos a lo largo del trazado (animación en matriz con acumulación de desplazamiento)"
  - "animación en matriz con acumulación de desplazamiento"
ms.assetid: 1bca90ef-9832-4128-8ed6-62908e7ec146
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Animar un objeto a lo largo de un trazado (animaci&#243;n en matriz con acumulaci&#243;n de desplazamiento)
Este ejemplo muestra cómo utilizar el <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> clase animar un objeto a lo largo de una ruta de acceso y hacer que esa animación se acumulan su desplazamiento valores de medida que se repite.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se utiliza la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath> objeto que desea animar el <xref:System.Windows.Media.MatrixTransform.Matrix%2A> propiedad de un <xref:System.Windows.Media.MatrixTransform> aplicada a un botón. Como resultado, un botón se mueve a lo largo de un trazado curvo.  
  
 Además, el ejemplo establece la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> propiedad `true`, lo que hace que el desplazamiento de la matriz animada a acumular a medida que se repite la animación. Dado que el desplazamiento se acumula, el botón se va alejando por la pantalla cuando se repite la animación, en lugar de restablecer la posición inicial.  
  
 [!code-xml[PathAnimationGallery_snippet#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_snippet/CS/matrixanimationusingpathexampleoffsetcumulative.xaml#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 [!code-csharp[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/CSharp/MatrixAnimationUsingPathExampleOffsetCumulative.cs#matrixanimationusingpathoffsetcumulativewholepage)]
 [!code-vb[PathAnimationGallery_procedural_snip#MatrixAnimationUsingPathOffsetCumulativeWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PathAnimationGallery_procedural_snip/VisualBasic/MatrixAnimationUsingPathExampleOffsetCumulative.vb#matrixanimationusingpathoffsetcumulativewholepage)]  
  
 Tenga en cuenta que, aunque la <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsOffsetCumulative%2A> propiedad hace que los valores de desplazamiento a acumular en las repeticiones, no hace que se acumulan los valores de rotación. Para hacer que los valores de rotación se acumulan, establezca la animación <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.DoesRotateWithTangent%2A> y <xref:System.Windows.Media.Animation.MatrixAnimationUsingPath.IsAngleCumulative%2A> propiedades `true`.  
  
 Para obtener un ejemplo completo, vea [ejemplo Path Animation](http://go.microsoft.com/fwlink/?LinkID=160028). Para obtener un ejemplo que muestra cómo animar un <xref:System.Windows.Media.Matrix> valor a lo largo de una ruta de acceso sin acumulación de desplazamiento, consulte [animar un objeto a lo largo de una ruta de acceso (animación en matriz)](../../../../docs/framework/wpf/graphics-multimedia/how-to-animate-an-object-along-a-path-matrix-animation.md).  
  
## <a name="see-also"></a>Vea también  
 [Información general de animación](../../../../docs/framework/wpf/graphics-multimedia/animation-overview.md)   
 [Temas de procedimientos de animación de trazado](../../../../docs/framework/wpf/graphics-multimedia/path-animation-how-to-topics.md)