---
title: "Cómo: Modificar el extremo en el final de una línea o segmento"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Shape elements [WPF], ends
- Shape elements [WPF], caps
- graphics [WPF], Shape caps
ms.assetid: f4bf3416-b3d8-4568-b98e-3eda8f6dbf7a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0d2cd55de403b766344749259068ccd313558f89
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a><span data-ttu-id="a4914-102">Cómo: Modificar el extremo en el final de una línea o segmento</span><span class="sxs-lookup"><span data-stu-id="a4914-102">How to: Modify the Cap at the End of a Line or Segment</span></span>
<span data-ttu-id="a4914-103">Este ejemplo muestra cómo modificar la forma al principio o al final de un circuito abierto <xref:System.Windows.Shapes.Shape> elemento.</span><span class="sxs-lookup"><span data-stu-id="a4914-103">This example shows how to modify the shape at the start or end of an open <xref:System.Windows.Shapes.Shape> element.</span></span> <span data-ttu-id="a4914-104">Para cambiar el extremo al principio de un formato de archivo <xref:System.Windows.Shapes.Shape>, usar su <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a4914-104">To change the cap at the beginning of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> property.</span></span> <span data-ttu-id="a4914-105">Para cambiar el extremo al final de un formato de archivo <xref:System.Windows.Shapes.Shape>, usar su <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="a4914-105">To change the cap at the end of an open <xref:System.Windows.Shapes.Shape>, use its <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> property.</span></span> <span data-ttu-id="a4914-106">Para ver los extremos de línea disponibles, vea el <xref:System.Windows.Media.PenLineCap> enumeración.</span><span class="sxs-lookup"><span data-stu-id="a4914-106">To view the available line caps, see the <xref:System.Windows.Media.PenLineCap> enumeration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4914-107">Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, o abierto <xref:System.Windows.Shapes.Path> elemento.</span><span class="sxs-lookup"><span data-stu-id="a4914-107">This property only affects an open shape, such as a <xref:System.Windows.Shapes.Line>, a <xref:System.Windows.Shapes.Polyline>, or an open <xref:System.Windows.Shapes.Path> element.</span></span>  
  
 <span data-ttu-id="a4914-108">En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Polyline> elementos y utiliza un conjunto diferente de formas en los extremos de cada uno.</span><span class="sxs-lookup"><span data-stu-id="a4914-108">The following example draws four <xref:System.Windows.Shapes.Polyline> elements and uses a different set of shapes on the ends of each.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4914-109">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="a4914-109">Example</span></span>  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 <span data-ttu-id="a4914-110">Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span><span class="sxs-lookup"><span data-stu-id="a4914-110">This example is part of a larger sample; for the complete sample, see [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4914-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="a4914-111">See Also</span></span>  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
