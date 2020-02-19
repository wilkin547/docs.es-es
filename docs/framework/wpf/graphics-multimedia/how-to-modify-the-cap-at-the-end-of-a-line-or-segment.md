---
title: 'Cómo: Modificar el extremo en el final de una línea o segmento'
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 5f755d7b4d1682755ea461121f91c0666d450ad1
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452784"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Cómo: Modificar el extremo en el final de una línea o segmento
En este ejemplo se muestra cómo modificar la forma al principio o al final de un elemento de <xref:System.Windows.Shapes.Shape> abierto. Para cambiar el extremo al principio de un <xref:System.Windows.Shapes.Shape>abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>. Para cambiar el extremo al final de un <xref:System.Windows.Shapes.Shape>abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>. Para ver los límites de línea disponibles, consulte la enumeración <xref:System.Windows.Media.PenLineCap>.  
  
> [!NOTE]
> Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>o un elemento <xref:System.Windows.Shapes.Path> abierto.  
  
 En el ejemplo siguiente se dibujan cuatro elementos <xref:System.Windows.Shapes.Polyline> y se utiliza un conjunto diferente de formas en los extremos de cada uno de ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
