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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="712c5-102">Cómo: Modificar el extremo en el final de una línea o segmento</span><span class="sxs-lookup"><span data-stu-id="712c5-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="712c5-103">En este ejemplo se muestra cómo modificar la forma al principio o al final de un elemento de <xref:System.Windows.Shapes.Shape> abierto.</span><span class="sxs-lookup"><span data-stu-id="712c5-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="712c5-104">Para cambiar el extremo al principio de un <xref:System.Windows.Shapes.Shape>abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="712c5-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="712c5-105">Para cambiar el extremo al final de un <xref:System.Windows.Shapes.Shape>abierto, utilice su propiedad <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A>.</span><span class="sxs-lookup"><span data-stu-id="712c5-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="712c5-106">Para ver los límites de línea disponibles, consulte la enumeración <xref:System.Windows.Media.PenLineCap>.</span><span class="sxs-lookup"><span data-stu-id="712c5-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="712c5-107">Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, un <xref:System.Windows.Shapes.Polyline>o un elemento <xref:System.Windows.Shapes.Path> abierto.</span><span class="sxs-lookup"><span data-stu-id="712c5-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="712c5-108">En el ejemplo siguiente se dibujan cuatro elementos <xref:System.Windows.Shapes.Polyline> y se utiliza un conjunto diferente de formas en los extremos de cada uno de ellos.</span><span class="sxs-lookup"><span data-stu-id="712c5-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="712c5-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="712c5-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="712c5-110">Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span><span class="sxs-lookup"><span data-stu-id="712c5-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="712c5-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="712c5-111">See also</span></span>

- <xref:System.Windows.Shapes.Polyline>
- <xref:System.Windows.Media.PenLineCap>
