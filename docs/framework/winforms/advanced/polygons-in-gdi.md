---
title: Polígonos en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- polygons
- drawing [Windows Forms], polygons
- GDI+, polygons
ms.assetid: a72213d2-d69a-4c2b-a75c-be7b20390c13
ms.openlocfilehash: 2b1e3d387e4d056d9187c54dcef560544206c370
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641312"
---
# <a name="polygons-in-gdi"></a>Polígonos en GDI+
Un polígono es una forma cerrada con tres o más líneas rectas. Por ejemplo, un triángulo es un polígono con tres lados, un rectángulo es un polígono con cuatro lados y un Pentágono es un polígono con cinco lados. La ilustración siguiente muestra varios polígonos.  
  
 ![Polygons](./media/aboutgdip02-art07.gif "Aboutgdip02_art07")  
  
## <a name="drawing-a-polygon"></a>Dibujar un polígono  
 Para dibujar un polígono, necesita un <xref:System.Drawing.Graphics> objeto, un <xref:System.Drawing.Pen> objeto y una matriz de <xref:System.Drawing.Point> (o <xref:System.Drawing.PointF>) objetos. El <xref:System.Drawing.Graphics> objeto proporciona el <xref:System.Drawing.Graphics.DrawPolygon%2A> método. El <xref:System.Drawing.Pen> objeto almacena atributos, como el ancho y color de la línea utilizada para representar el polígono y la matriz de <xref:System.Drawing.Point> objetos almacena los puntos que estén conectados mediante líneas rectas. El <xref:System.Drawing.Pen> objeto y la matriz de <xref:System.Drawing.Point> objetos se pasan como argumentos para el <xref:System.Drawing.Graphics.DrawPolygon%2A> método. El ejemplo siguiente dibuja un polígono tres lados. Tenga en cuenta que hay sólo tres puntos en `myPointArray`: (0, 0), (50, 30) y (30, 60). El <xref:System.Drawing.Graphics.DrawPolygon%2A> método cierra automáticamente el polígono, dibuje una línea desde (30, 60) hasta el punto de partida (0, 0).  
  
 [!code-csharp[LinesCurvesAndShapes#111](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#111)]
 [!code-vb[LinesCurvesAndShapes#111](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#111)]  
  
 La siguiente ilustración muestra el polígono.  
  
 ![Polygon](./media/aboutgdip02-art08.gif "Aboutgdip02_art08")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Crear un lápiz](how-to-create-a-pen.md)
