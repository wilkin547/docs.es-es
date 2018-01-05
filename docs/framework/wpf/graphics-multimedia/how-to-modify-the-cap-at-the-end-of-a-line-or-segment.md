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
# <a name="how-to-modify-the-cap-at-the-end-of-a-line-or-segment"></a>Cómo: Modificar el extremo en el final de una línea o segmento
Este ejemplo muestra cómo modificar la forma al principio o al final de un circuito abierto <xref:System.Windows.Shapes.Shape> elemento. Para cambiar el extremo al principio de un formato de archivo <xref:System.Windows.Shapes.Shape>, usar su <xref:System.Windows.Shapes.Shape.StrokeStartLineCap%2A> propiedad. Para cambiar el extremo al final de un formato de archivo <xref:System.Windows.Shapes.Shape>, usar su <xref:System.Windows.Shapes.Shape.StrokeEndLineCap%2A> propiedad. Para ver los extremos de línea disponibles, vea el <xref:System.Windows.Media.PenLineCap> enumeración.  
  
> [!NOTE]
>  Esta propiedad solo afecta a una forma abierta, como un <xref:System.Windows.Shapes.Line>, <xref:System.Windows.Shapes.Polyline>, o abierto <xref:System.Windows.Shapes.Path> elemento.  
  
 En el ejemplo siguiente se dibuja cuatro <xref:System.Windows.Shapes.Polyline> elementos y utiliza un conjunto diferente de formas en los extremos de cada uno.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[drawingwithshapeelements#ShapeLineCaps1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/linecapsandjoinsexample.xaml#shapelinecaps1)]  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Shapes.Polyline>  
 <xref:System.Windows.Media.PenLineCap>
