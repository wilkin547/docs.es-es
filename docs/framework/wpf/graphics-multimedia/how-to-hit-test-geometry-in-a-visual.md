---
title: Procedimiento Geometría de una prueba de posicionamiento en un objeto Visual
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [WPF], on visual objects comprising Geometry objects [WPF]
- visual objects [WPF], hit tests on
- Geometry objects [WPF], visual objects comprising
ms.assetid: 8bf2643f-d7f9-4cb4-9ea6-5b893c23200d
ms.openlocfilehash: e51dd73a65666ffee5958325079e8f06f13ac61b
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57363805"
---
# <a name="how-to-hit-test-geometry-in-a-visual"></a>Filtrar Geometría de una prueba de posicionamiento en un objeto Visual
En este ejemplo se muestra cómo realizar una prueba de posicionamiento en un objeto visual que se compone de uno o varios <xref:System.Windows.Media.Geometry> objetos.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo recuperar el <xref:System.Windows.Media.DrawingGroup> desde un objeto visual que utiliza el <xref:System.Windows.Media.VisualTreeHelper.GetDrawing%2A> método. A continuación, se realiza una prueba de posicionamiento en el contenido representado de cada dibujo de la <xref:System.Windows.Media.DrawingGroup> para determinar qué geometría se posicionó.  
  
> [!NOTE]
>  En la mayoría de los casos, se utilizaría el <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> método para determinar si un punto corta el contenido representado de un objeto visual.  
  
 [!code-csharp[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/csharp/VS_Snippets_Wpf/VisualsOverview/CSharp/Window1.xaml.cs#visualsoverviewsnippet4)]
 [!code-vb[VisualsOverview#VisualsOverviewSnippet4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/VisualsOverview/visualbasic/window1.xaml.vb#visualsoverviewsnippet4)]  
  
 El <xref:System.Windows.Media.Geometry.FillContains%2A> método es un método sobrecargado que permite realizar pruebas de posicionamiento mediante el uso de un determinado <xref:System.Windows.Point> o <xref:System.Windows.Media.Geometry>. Si se traza una geometría, el trazo puede extenderse fuera del límite del relleno. En este caso, es posible que desea llamar <xref:System.Windows.Media.Geometry.StrokeContains%2A> además <xref:System.Windows.Media.Geometry.FillContains%2A>.  
  
 También puede proporcionar un <xref:System.Windows.Media.ToleranceType> que se usa para los fines de aplanamiento de Bezier.  
  
> [!NOTE]
>  Esta muestra no tiene en cuenta ninguna transformación o recorte que pueda aplicarse a la geometría. Además, este ejemplo no funcionará con un control con estilo, puesto que no tiene los dibujos asociados a él.  
  
## <a name="see-also"></a>Vea también
- [Realizar pruebas de posicionamiento en la capa visual](hit-testing-in-the-visual-layer.md)
- [Realizar una prueba de posicionamiento usando Geometry como parámetro](how-to-hit-test-using-geometry-as-a-parameter.md)
