---
title: Procedimiento Dibujar una línea
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [WPF], lines
- graphics [WPF], lines
- lines [WPF], drawing
ms.assetid: 0513ee01-6b27-4bb3-85f3-3a3e6710d80e
ms.openlocfilehash: c11dfb9523834ec2e622cb2e62bd6982a1a78fd4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947659"
---
# <a name="how-to-draw-a-line"></a>Procedimiento Dibujar una línea
En este ejemplo se muestra cómo dibujar líneas con el <xref:System.Windows.Shapes.Line> elemento.  
  
 Para dibujar una línea, cree un <xref:System.Windows.Shapes.Line> elemento. Use su <xref:System.Windows.Shapes.Line.X1%2A> y <xref:System.Windows.Shapes.Line.Y1%2A> propiedades para establecer su punto inicial; y utilice su <xref:System.Windows.Shapes.Line.X2%2A> y <xref:System.Windows.Shapes.Line.Y2%2A> propiedades para establecer su punto de conexión. Por último, establezca su <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> porque una línea sin un trazo es invisible.  
  
 Establecer el <xref:System.Windows.Shapes.Shape.Fill%2A> (elemento) para una línea no tiene ningún efecto, porque una línea no tiene interior.  
  
 El ejemplo siguiente dibuja tres líneas dentro de un <xref:System.Windows.Controls.Canvas> elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#LineExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/lineexample.xaml#lineexample1)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Line>
- [Ejemplo de los elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037)
