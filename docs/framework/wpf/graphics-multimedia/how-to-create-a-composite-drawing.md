---
title: 'Cómo: Crear un dibujo compuesto'
ms.date: 03/30/2017
helpviewer_keywords:
- drawings [WPF], composite
- composite drawings [WPF]
- graphics [WPF], composite drawings
ms.assetid: 066eb0ab-5f0e-439d-85c6-dca60af269fc
ms.openlocfilehash: bb222fff11c81b491c0413f174539ff0005d11b8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33561598"
---
# <a name="how-to-create-a-composite-drawing"></a>Cómo: Crear un dibujo compuesto
Este ejemplo muestra cómo utilizar un <xref:System.Windows.Media.DrawingGroup> para crear dibujos complejos combinando varias <xref:System.Windows.Media.Drawing> objetos en un único dibujo compuesto.  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un <xref:System.Windows.Media.DrawingGroup> para crear un dibujo compuesto a partir del <xref:System.Windows.Media.GeometryDrawing> y <xref:System.Windows.Media.ImageDrawing> objetos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![DrawingGroup con varios dibujos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-simple.jpg "graphicsmm_simple")  
Un dibujo compuesto que se crea mediante el uso de DrawingGroup  
  
 Tenga en cuenta el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmsimpledrawinggroupexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMSimpleDrawingGroupExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmsimpledrawinggroupexample)]  
  
 Puede usar un <xref:System.Windows.Media.DrawingGroup> para aplicar un <xref:System.Windows.Media.DrawingGroup.Transform%2A>, <xref:System.Windows.Media.DrawingGroup.Opacity%2A> establecer, <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>, <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>, <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>, o <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A> a los dibujos contiene. Dado que un <xref:System.Windows.Media.DrawingGroup> también es un <xref:System.Windows.Media.Drawing>, pueden contener otras <xref:System.Windows.Media.DrawingGroup> objetos.  
  
 En el ejemplo siguiente es similar al ejemplo anterior, salvo que usa adicionales <xref:System.Windows.Media.DrawingGroup> objetos que se va a aplicar efectos de mapa de bits y una máscara de opacidad a algunos de sus dibujos. En la ilustración siguiente se muestra el resultado que genera el ejemplo.  
  
 ![DrawingGroup con varios dibujos](../../../../docs/framework/wpf/graphics-multimedia/media/graphicsmm-multiple.jpg "graphicsmm_multiple")  
Dibujo compuesto que tiene varios objetos DrawingGroup  
  
 Tenga en cuenta el borde gris, que muestra los límites del dibujo.  
  
 [!code-csharp[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingMiscSnippets_snip/CSharp/DrawingGroupExample.cs#graphicsmmmultipledrawinggroupsexample)]
 [!code-xaml[DrawingMiscSnippets_snip#GraphicsMMMultipleDrawingGroupsExample](../../../../samples/snippets/xaml/VS_Snippets_Wpf/DrawingMiscSnippets_snip/XAML/DrawingGroupExample.xaml#graphicsmmmultipledrawinggroupsexample)]  
  
 Para obtener más información acerca de <xref:System.Windows.Media.Drawing> los objetos, vea [información general de objetos de dibujo](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Media.DrawingGroup.BitmapEffect%2A>  
 <xref:System.Windows.Media.DrawingGroup.Transform%2A>  
 <xref:System.Windows.Media.DrawingGroup.OpacityMask%2A>  
 <xref:System.Windows.Media.DrawingGroup.Opacity%2A>  
 <xref:System.Windows.Media.DrawingGroup.ClipGeometry%2A>  
 <xref:System.Windows.Media.DrawingGroup.GuidelineSet%2A>  
 [Información general sobre objetos Drawing](../../../../docs/framework/wpf/graphics-multimedia/drawing-objects-overview.md)
