---
title: "Cómo: Crear una forma compuesta"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- shapes [WPF], composite
- composite shapes [WPF]
- graphics [WPF], composite shapes
ms.assetid: 8e5c7ef4-d7ed-4c43-afc9-ca01325c300b
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 9ded7bd25f7f416bc512051f883b4ae12b2fa56d
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-create-a-composite-shape"></a>Cómo: Crear una forma compuesta
Este ejemplo muestra cómo crear formas compuestas mediante <xref:System.Windows.Media.Geometry> objetos y mostrarlos mediante un <xref:System.Windows.Shapes.Path> elemento. En el ejemplo siguiente, un <xref:System.Windows.Media.LineGeometry>, <xref:System.Windows.Media.EllipseGeometry>y un <xref:System.Windows.Media.RectangleGeometry> se usan con una <xref:System.Windows.Media.GeometryGroup> para crear una forma compuesta. A continuación, se dibujan las geometrías mediante un <xref:System.Windows.Shapes.Path> elemento.  
  
## <a name="example"></a>Ejemplo  
 [!code-xaml[GeometrySample#19](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometrySample/CS/combininggeometriesexample.xaml#19)]  
  
 [!code-csharp[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/CSharp/CompositeShapeExample.cs#compositeshapecodeexampleinline1)]
 [!code-vb[GeometriesMiscSnippets_procedural_snip#CompositeShapeCodeExampleInline1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GeometriesMiscSnippets_procedural_snip/visualbasic/compositeshapeexample.vb#compositeshapecodeexampleinline1)]  
  
 La siguiente ilustración muestra la forma creada en el ejemplo anterior.  
  
 ![Una geometría compuesta creada mediante GeometryGroup](../../../../docs/framework/wpf/graphics-multimedia/media/wcpsdk-graphicsmm-compositegeometryexample1.jpg "wcpsdk_graphicsmm_compositegeometryexample1")  
Geometría compuesta  
  
 Formas más complejas, como polígonos y formas con segmentos de curvados, pueden crearse mediante un <xref:System.Windows.Media.PathGeometry>. Para obtener un ejemplo que muestra cómo crear una forma mediante una <xref:System.Windows.Media.PathGeometry>, consulte [crear una forma mediante una clase PathGeometry](../../../../docs/framework/wpf/graphics-multimedia/how-to-create-a-shape-by-using-a-pathgeometry.md).  Aunque en este ejemplo se representa una forma en la pantalla mediante una <xref:System.Windows.Shapes.Path> elemento, <xref:System.Windows.Media.Geometry> objetos también pueden utilizarse para describir el contenido de un <xref:System.Windows.Media.GeometryDrawing> o <xref:System.Windows.Media.DrawingContext>. Se puede usar también para el recorte y la prueba de posicionamiento.  
  
 Este ejemplo forma parte de un ejemplo más extenso; para obtener el ejemplo completo, vea [Ejemplo de geometrías](http://go.microsoft.com/fwlink/?LinkID=159989).
