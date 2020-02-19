---
title: 'Cómo: Dibujar una forma cerrada utilizando el elemento Polygon'
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
ms.openlocfilehash: 324a5623ee658789b8600a43a89ce26cab7cd6cd
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452979"
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Cómo: Dibujar una forma cerrada utilizando el elemento Polygon
En este ejemplo se muestra cómo dibujar una forma cerrada utilizando el elemento <xref:System.Windows.Shapes.Polygon>. Para dibujar una forma cerrada, cree un elemento <xref:System.Windows.Shapes.Polygon> y utilice su propiedad <xref:System.Windows.Shapes.Polygon.Points%2A> para especificar los vértices de una forma. Se dibuja automáticamente una línea que conecta los puntos primero y último. Por último, especifique un <xref:System.Windows.Shapes.Shape.Fill%2A>, un <xref:System.Windows.Shapes.Shape.Stroke%2A>o ambos.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], la sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separadas por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](~/samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Aunque en el ejemplo se usa una <xref:System.Windows.Controls.Canvas> para contener los polígonos, puede utilizar elementos Polygon (y todos los demás elementos de forma) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido que no sea de texto.  
  
 Este ejemplo forma parte de un ejemplo más grande; para obtener el ejemplo completo, vea [ejemplo de elementos de forma](https://github.com/Microsoft/WPF-Samples/tree/master/Graphics/ShapeElements).
