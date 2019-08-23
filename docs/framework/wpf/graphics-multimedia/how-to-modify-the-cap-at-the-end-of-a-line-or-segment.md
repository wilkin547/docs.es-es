---
title: Procedimiento Modificar el extremo en el final de una línea o segmento
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 53487417636dae8d855fe70b7b9255351a2dfb1e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69916135"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedimiento Modificar el extremo en el final de una línea o segmento
En este ejemplo se muestra cómo modificar la forma al principio o al final de un <xref:System.Windows.Shapes.Shape> elemento abierto. Para cambiar el extremo al principio de un abierto <xref:System.Windows.Shapes.Shape>, utilice su <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> propiedad. Para cambiar el extremo al final de un abierto <xref:System.Windows.Shapes.Shape>, utilice su <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> propiedad. Para ver los límites de línea disponibles, vea <xref:System.Windows.Media.PenLineCap> la enumeración.  
  
> [!NOTE]
> Esta propiedad solo afecta a una forma abierta, <xref:System.Windows.Shapes.Line>como <xref:System.Windows.Shapes.Polyline>, o un elemento abierto <xref:System.Windows.Shapes.Path> .  
  
 En el ejemplo siguiente se <xref:System.Windows.Shapes.Polyline> dibujan cuatro elementos y se utiliza un conjunto de formas diferente en los extremos de cada uno de ellos.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
