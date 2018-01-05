---
title: "Cómo: Dibujar una forma cerrada utilizando el elemento Polygon"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- graphics [WPF], Polygon elements
- closed shapes [WPF], drawing with Polygon elements
- Polygon elements [WPF]
- drawing [WPF], closed shapes with Polygon elements
ms.assetid: 4b0ca008-29ce-48dd-8bc3-f3a20ffca6a6
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cf842c22238105510b13407d55c8c9773f84a70
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-a-closed-shape-by-using-the-polygon-element"></a>Cómo: Dibujar una forma cerrada utilizando el elemento Polygon
Este ejemplo muestra cómo dibujar una forma cerrada utilizando el <xref:System.Windows.Shapes.Polygon> elemento. Para dibujar una forma cerrada, cree un <xref:System.Windows.Shapes.Polygon> elemento y utilice su <xref:System.Windows.Shapes.Polygon.Points%2A> propiedad para especificar los vértices de una forma. Se dibuja automáticamente una línea que conecta los puntos primero y último. Por último, especifique un <xref:System.Windows.Shapes.Shape.Fill%2A>, <xref:System.Windows.Shapes.Shape.Stroke%2A>, o ambos.  
  
## <a name="example"></a>Ejemplo  
 En [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], una sintaxis válida para los puntos es una lista delimitada por espacios de pares de coordenadas x e y separados por comas.  
  
 [!code-xaml[drawingwithshapeelements#PolygonExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/DrawingWithShapeElements/CS/polygonexample.xaml#polygonexample1)]  
  
 Aunque el ejemplo se usa un <xref:System.Windows.Controls.Canvas> para contener los polígonos, puede usar elementos de polígono (y todos los demás elementos de formas) con cualquier <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.Control> que admita contenido no son de texto.  
  
 Este ejemplo forma parte de un ejemplo más extenso; Para obtener un ejemplo completo, vea [Shape Elements Sample](http://go.microsoft.com/fwlink/?LinkID=160037).
