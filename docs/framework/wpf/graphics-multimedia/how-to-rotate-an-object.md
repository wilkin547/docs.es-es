---
title: 'Cómo: Girar un objeto'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], rotating objects [WPF]
- rotating objects [WPF]
ms.assetid: ee3466cd-e66f-4e8f-8a5a-71d77bc1e390
ms.openlocfilehash: e17d3b7b9986b477df198480129edaf4c139c6bc
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "80112068"
---
# <a name="how-to-rotate-an-object"></a>Cómo: Girar un objeto
Este ejemplo muestra cómo girar un objeto. El ejemplo primero <xref:System.Windows.Media.RotateTransform> crea a <xref:System.Windows.Media.RotateTransform.Angle%2A> y, a continuación, especifica su en grados.  
  
 En el ejemplo <xref:System.Windows.Shapes.Polyline> siguiente se gira un objeto 45 grados alrededor de su esquina superior izquierda.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[Transforms_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineabouttopleft)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineabouttopleft)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutTopLeft](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineabouttopleft)]  
  
 Las <xref:System.Windows.Media.RotateTransform.CenterX%2A> <xref:System.Windows.Media.RotateTransform.CenterY%2A> propiedades y <xref:System.Windows.Media.RotateTransform> las propiedades del especificar el punto sobre el que se gira el objeto. Este punto central se expresa en el espacio de coordenadas del elemento que se transforma. De forma predeterminada, la rotación se aplica a (0,0), que es la esquina superior izquierda del objeto que transformar.  
  
 En el ejemplo <xref:System.Windows.Shapes.Polyline> siguiente se gira un objeto en el sentido de las agujas del reloj 45 grados sobre el punto (25,50).  
  
 [!code-xaml[Transforms_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_snip/CS/RotateTransformExample.xaml#rotatepolylineaboutcenter)]  
  
 [!code-csharp[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/csharp/VS_Snippets_Wpf/Transforms_Procedural_snip/CSharp/RotateTransformExample.cs#rotatepolylineaboutcenter)]
 [!code-vb[Transforms_Procedural_snip#RotatePolylineAboutCenter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Transforms_Procedural_snip/VisualBasic/RotateTransformExample.vb#rotatepolylineaboutcenter)]  
  
 En la ilustración siguiente se <xref:System.Windows.Media.Transform> muestran los resultados de aplicar a los dos objetos.  
  
 ![Rotaciones de 45 grados con diferentes centros](./media/wcpsdk-graphicsmm-rotatetransform45degrees.gif "wcpsdk_graphicsmm_rotatetransform45degrees")  
Dos objetos que se giran 45 grados desde distintos centros de giro  
  
 El <xref:System.Windows.Shapes.Polyline> ejemplo anterior es <xref:System.Windows.UIElement>un archivo . Al aplicar <xref:System.Windows.Media.Transform> a <xref:System.Windows.UIElement.RenderTransform%2A> la propiedad <xref:System.Windows.UIElement>de un <xref:System.Windows.UIElement.RenderTransformOrigin%2A> , puede utilizar la <xref:System.Windows.Media.Transform> propiedad para especificar un origen para cada uno de los que aplique al elemento. Dado <xref:System.Windows.UIElement.RenderTransformOrigin%2A> que la propiedad utiliza coordenadas relativas, puede aplicar una transformación al centro del elemento incluso si no conoce su tamaño. Para obtener más información y un ejemplo, vea [Especificar el origen de una transformación mediante valores relativos](how-to-specify-the-origin-of-a-transform-by-using-relative-values.md).  
  
 Para ver el ejemplo completo, consulte Ejemplo de [transformaciones 2D](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/2DTransforms).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Media.Transform>
- [Información general sobre transformaciones](transforms-overview.md)
- [Temas de información](transformations-how-to-topics.md)
