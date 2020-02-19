---
title: 'Cómo: Crear una forma compuesta'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
ms.openlocfilehash: c56053f2b07d6055deac5097a68fd7b80ad704ba
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452102"
---
# <a name="how-to-create-a-composite-shape"></a>Cómo: Crear una forma compuesta
En este ejemplo se muestra cómo crear formas compuestas mediante <xref:System.Windows.Media.Geometry> objetos y cómo mostrarlas mediante un elemento <xref:System.Windows.Shapes.Path>. En el ejemplo siguiente, se usa un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>y un <xref:System.Windows.Media.RectangleGeometry> con un <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta. A continuación, las geometrías se dibujan utilizando un elemento <xref:System.Windows.Shapes.Path>.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GeometrySample#19](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 La siguiente ilustración muestra la forma creada en el ejemplo anterior.  
  
 ![Geometría compuesta creada con GeometryGroup](./media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Geometría compuesta  
  
 Las formas más complejas, como polígonos y formas con segmentos curvos, se pueden crear con un <xref:System.Windows.Media.PathGeometry>. Para ver un ejemplo en el que se muestra cómo crear una forma mediante un <xref:System.Windows.Media.PathGeometry>, vea [crear una forma mediante una PathGeometry](how-to-create-a-shape-by-using-a-pathgeometry.md).  Aunque en este ejemplo se representa una forma en la pantalla mediante un elemento <xref:System.Windows.Shapes.Path>, <xref:System.Windows.Media.Geometry> objetos también se pueden usar para describir el contenido de un <xref:System.Windows.Media.GeometryDrawing> o de un <xref:System.Windows.Media.DrawingContext>. También se pueden usar para el recorte y la prueba de posicionamiento.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/Geometry).
