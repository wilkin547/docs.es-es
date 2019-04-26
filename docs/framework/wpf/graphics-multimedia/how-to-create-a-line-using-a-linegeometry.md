---
title: Procedimiento Crear una línea mediante la clase LineGeometry
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [WPF], lines
ms.assetid: 41231b22-1f74-4c26-a8e7-a55b29f8f6bd
ms.openlocfilehash: f8c334a54f78aec7af91064a447fd18f23dcfbdc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905208"
---
# <a name="how-to-create-a-line-using-a-linegeometry"></a>Procedimiento Crear una línea mediante la clase LineGeometry
En este ejemplo se muestra cómo usar el <xref:System.Windows.Media.LineGeometry> clase para describir una línea. Un <xref:System.Windows.Media.LineGeometry> se define por sus puntos inicial y final.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente muestra cómo crear y representar un <xref:System.Windows.Media.LineGeometry>.  Un <xref:System.Windows.Shapes.Path> elemento se usa para representar la línea.  Dado que una línea no tiene ninguna área, el <xref:System.Windows.Shapes.Path> del objeto <xref:System.Windows.Shapes.Shape.Fill%2A> no se ha especificado; en su lugar el <xref:System.Windows.Shapes.Shape.Stroke%2A> y <xref:System.Windows.Shapes.Shape.StrokeThickness%2A> se usan las propiedades.  
  
 [!code-xaml[GeometryOverviewSamples_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_snip/CS/GeometryExamples.xaml#graphicsmmlinegeometryexample)]  
  
 [!code-csharp[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/CSharp/GeometryExamples.cs#graphicsmmlinegeometryexample)]
 [!code-vb[GeometryOverviewSamples_procedural_snip#GraphicsMMLineGeometryExample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometryOverviewSamples_procedural_snip/visualbasic/geometryexamples.vb#graphicsmmlinegeometryexample)]  
  
 ![LineGeometry](./media/graphicsmm-line.gif "graphicsmm_line")  
Objeto LineGeometry dibujado desde (10,20) hasta (100,130)  
  
 Otras clases de geometría simple incluyen <xref:System.Windows.Media.LineGeometry> y <xref:System.Windows.Media.EllipseGeometry>. Estas geometrías, así como otras más complejas, también se pueden crear mediante un <xref:System.Windows.Media.PathGeometry> o <xref:System.Windows.Media.StreamGeometry>. Para obtener más información, consulte el [información general sobre geometría](geometry-overview.md).  
  
## <a name="see-also"></a>Vea también

- [Información general sobre geometría](geometry-overview.md)
- [Crear una forma compuesta](how-to-create-a-composite-shape.md)
- [Crear una forma mediante una clase PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md)
