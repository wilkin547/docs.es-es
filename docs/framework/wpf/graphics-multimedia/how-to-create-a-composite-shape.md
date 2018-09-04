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
ms.openlocfilehash: 9892120d13a067586dbf6472a6873b6a52c2d8b4
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515169"
---
# <a name="how-to-create-a-composite-shape"></a>Cómo: Crear una forma compuesta
En este ejemplo se muestra cómo crear formas compuestas mediante <xref:System.Windows.Media.Geometry> objetos y mostrarlas con un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente, un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>y un <xref:System.Windows.Media.RectangleGeometry> se usan con un <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta. A continuación, se dibujan las geometrías utilizando un <xref:System.Windows.Shapes.Path> elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 La siguiente ilustración muestra la forma creada en el ejemplo anterior.  
  
 ![Geometría compuesta creada mediante GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Geometría compuesta  
  
 Las formas más complejas, tales como polígonos y formas con segmentos curvados, pueden crearse mediante un <xref:System.Windows.Media.PathGeometry>. Para obtener un ejemplo que muestra cómo crear una forma mediante una <xref:System.Windows.Media.PathGeometry>, consulte [crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Aunque este ejemplo representa una forma en la pantalla mediante una <xref:System.Windows.Shapes.Path> elemento, <xref:System.Windows.Media.Geometry> objetos también pueden utilizarse para describir el contenido de un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>. También puede usarse para el recorte y la prueba de posicionamiento.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](https://go.microsoft.com/fwlink/?LinkID=159989).
