---
title: Procedimiento Geometría de una prueba de posicionamiento en un objeto visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: 52b9b99b0af38d797e4a3c98dc0979211c930c1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69923376"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Procedimiento Geometría de una prueba de posicionamiento en un objeto visual
En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual que se compone de uno <xref:System.Windows.Media.Geometry> o más objetos.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se muestra cómo recuperar <xref:System.Windows.Media.DrawingGroup> de un objeto visual que utiliza el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método. Después, se realiza una prueba de posicionamiento en el contenido representado de cada dibujo de <xref:System.Windows.Media.DrawingGroup> para determinar qué geometría se alcanzó.  
  
> [!NOTE]
> En la mayoría de los casos, se <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> usaría el método para determinar si un punto forma una intersección con el contenido representado de un visual.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 El <xref:System.Windows.Media.Geometry.FillContains%2A> método es un método sobrecargado que permite realizar una prueba de posicionamiento mediante un especificado <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>. Si se traza una geometría, el trazo puede extenderse fuera del límite del relleno. En ese caso, puede que desee llamar <xref:System.Windows.Media.Geometry.StrokeContains%2A> a además de a. <xref:System.Windows.Media.Geometry.FillContains%2A>  
  
 También puede proporcionar un <xref:System.Windows.Media.ToleranceType> que se usa para los propósitos del aplanamiento de Bézier.  
  
> [!NOTE]
> Esta muestra no tiene en cuenta ninguna transformación o recorte que pueda aplicarse a la geometría. Además, este ejemplo no funcionará con un control con estilo, puesto que no tiene los dibujos asociados a él.  
  
## <a name="see-also"></a>Vea también

- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Realizar una prueba de posicionamiento usando Geometry como parámetro](how-to-hit-test-using-geometry-as-a-parameter.md)
