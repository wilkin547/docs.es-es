---
title: 'Cómo: Dibujar una línea'
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: a803c1be01086ca8911ef4cc33bd67697239e2c0
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452953"
---
# <a name="how-to-draw-a-line"></a>Cómo: Dibujar una línea
En este ejemplo se muestra cómo dibujar líneas mediante el elemento <xref:System.Windows.Shapes.Line>.  
  
 Para dibujar una línea, cree un elemento <xref:System.Windows.Shapes.Line>. Use sus propiedades <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> para establecer su punto inicial; y usan sus propiedades <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> para establecer su punto final. Por último, establezca su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> porque una línea sin trazo es invisible.  
  
 Establecer el elemento <xref:System.Windows.Shapes.Shape.Fill%2A> para una línea no tiene ningún efecto, ya que una línea no tiene ningún interior.  
  
 En el ejemplo siguiente se dibujan tres líneas dentro de un elemento <xref:System.Windows.Controls.Canvas>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Line>
- [Ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements)
