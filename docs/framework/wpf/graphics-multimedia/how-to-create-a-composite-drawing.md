---
title: Procedimiento Crear un dibujo compuesto
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: 0af7fbca593627ebe8cd102a02617a27eac50aa5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910005"
---
# <a name="how-to-create-a-composite-drawing"></a>Procedimiento Crear un dibujo compuesto
En este ejemplo se muestra cómo usar un <xref:System.Windows.Media.DrawingGroup> para crear dibujos complejos combinando varias <xref:System.Windows.Media.Drawing> objetos en un solo dibujo compuesto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingGroup> para crear un dibujo compuesto a partir del <xref:System.Windows.Media.GeometryDrawing> y <xref:System.Windows.Media.ImageDrawing> objetos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto que se crea mediante el uso de DrawingGroup  
  
 Tenga en cuenta el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Puede usar un <xref:System.Windows.Media.DrawingGroup> para aplicar un <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> establecer, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> a la contiene los dibujos. Dado que un <xref:System.Windows.Media.DrawingGroup> es también un <xref:System.Windows.Media.Drawing>, pueden contener otros <xref:System.Windows.Media.DrawingGroup> objetos.  
  
 El ejemplo siguiente es similar al ejemplo anterior, salvo que usa adicionales <xref:System.Windows.Media.DrawingGroup> objetos que se va a aplicar efectos de imagen y una máscara de opacidad a algunos de sus planos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![DrawingGroup con varios dibujos](./media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
Dibujo compuesto que tiene varios objetos de DrawingGroup  
  
 Tenga en cuenta el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](~/samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Drawing> objetos, vea [información general sobre objetos de dibujo](drawing-objects-overview.md).  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>
- <xref:System.Windows.Media.DrawingGroup.Transform%2A>
- <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>
- <xref:System.Windows.Media.DrawingGroup.Opacity%2A>
- <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>
- <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>
- [Información general sobre objetos Drawing](drawing-objects-overview.md)
