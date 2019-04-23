---
title: Procedimiento Modificar el extremo en el final de una línea o segmento
ms.date: 03/30/2017
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
ms.openlocfilehash: 462e32520393a1c23809cce8eb3c130c13bc882f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977683"
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Procedimiento Modificar el extremo en el final de una línea o segmento
En este ejemplo se muestra cómo modificar la forma al principio o al final de una abierta <xref:System.Windows.Shapes.Shape> elemento. Para cambiar el límite del principio de abierto <xref:System.Windows.Shapes.Shape>, use su <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> propiedad. Para cambiar el límite al final de una abierta <xref:System.Windows.Shapes.Shape>, use su <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> propiedad. Para ver los extremos de línea disponibles, consulte el <xref:System.Windows.Media.PenLineCap> enumeración.  
  
> [!NOTE]
>  Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>, o una apertura <xref:System.Windows.Shapes.Path> elemento.  
  
 En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Polyline> elementos y utiliza un conjunto diferente de las formas en los extremos de cada uno.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](https://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
