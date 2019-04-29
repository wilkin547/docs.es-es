---
title: Curvas abiertas y cerradas en GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- curves [Windows Forms], filling
- GDI+, curves
- curves [Windows Forms], drawing
- curves
ms.assetid: 08d2cc9a-dc9d-4eed-bcbb-2c8e2ca5d3ae
ms.openlocfilehash: 33a8954296a7e63637ad5e210fb30fba1a3fdd53
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61641482"
---
# <a name="open-and-closed-curves-in-gdi"></a>Curvas abiertas y cerradas en GDI+
La siguiente ilustración muestra dos curvas: una abierta y otra cerrada.  
  
 ![Curvas abiertas y cerradas](./media/aboutgdip02-art24.gif "Aboutgdip02_art24")  
  
## <a name="managed-interface-for-curves"></a>Interfaz administrada para curvas  
 Curvas cerradas tienen un interior y por lo tanto, se pueden rellenar con un pincel. El <xref:System.Drawing.Graphics> clase [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] proporciona los siguientes métodos para rellenar curvas y formas cerradas: <xref:System.Drawing.Graphics.FillRectangle%2A>, <xref:System.Drawing.Graphics.FillEllipse%2A>, <xref:System.Drawing.Graphics.FillPie%2A>, <xref:System.Drawing.Graphics.FillPolygon%2A>, <xref:System.Drawing.Graphics.FillClosedCurve%2A>, <xref:System.Drawing.Graphics.FillPath%2A>, y <xref:System.Drawing.Graphics.FillRegion%2A>. Cuando llame a uno de estos métodos, debe pasar uno de los tipos de pincel (<xref:System.Drawing.SolidBrush>, <xref:System.Drawing.Drawing2D.HatchBrush>, <xref:System.Drawing.TextureBrush>, <xref:System.Drawing.Drawing2D.LinearGradientBrush>, o <xref:System.Drawing.Drawing2D.PathGradientBrush>) como argumento.  
  
 El <xref:System.Drawing.Graphics.FillPie%2A> método es un complemento para el <xref:System.Drawing.Graphics.DrawArc%2A> método. Al igual que el <xref:System.Drawing.Graphics.DrawArc%2A> método dibuja una parte del contorno de una elipse, la <xref:System.Drawing.Graphics.FillPie%2A> método rellena una parte del interior de una elipse. El ejemplo siguiente dibuja un arco y rellena la parte correspondiente del interior de la elipse:  
  
 [!code-csharp[LinesCurvesAndShapes#21](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#21)]
 [!code-vb[LinesCurvesAndShapes#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#21)]  
  
 La siguiente ilustración muestra el arco y el sector relleno.  
  
 ![Curvas abiertas y cerradas](./media/aboutgdip02-art25.gif "Aboutgdip02_art25")  
  
 El <xref:System.Drawing.Graphics.FillClosedCurve%2A> método es un complemento para el <xref:System.Drawing.Graphics.DrawClosedCurve%2A> método. Ambos métodos cerrará automáticamente la curva conectando el punto final para el punto de partida. En el ejemplo siguiente se dibuja una curva que pasa a través de (0, 0), (60, 20) y (40, 50). A continuación, la curva se cierra automáticamente mediante la conexión (40, 50) hasta el punto inicial (0, 0), y el interior se rellena con un color sólido.  
  
 [!code-csharp[LinesCurvesAndShapes#22](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#22)]
 [!code-vb[LinesCurvesAndShapes#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#22)]  
  
 El <xref:System.Drawing.Graphics.FillPath%2A> método rellena el interior de las partes independientes de una ruta de acceso. Si una parte de una ruta de acceso no forma una curva cerrada o una forma, el <xref:System.Drawing.Graphics.FillPath%2A> método cierra automáticamente esa parte de la ruta de acceso antes de llenarlo. El ejemplo siguiente se dibuja y rellena una ruta de acceso que consta de un arco, una curva spline cardinal, una cadena y un gráfico circular:  
  
 [!code-csharp[LinesCurvesAndShapes#23](~/samples/snippets/csharp/VS_Snippets_Winforms/LinesCurvesAndShapes/CS/Class1.cs#23)]
 [!code-vb[LinesCurvesAndShapes#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/LinesCurvesAndShapes/VB/Class1.vb#23)]  
  
 La siguiente ilustración muestra la ruta de acceso con y sin el relleno sólido. Tenga en cuenta que el texto de la cadena que se describen, pero no se rellena, por el <xref:System.Drawing.Graphics.DrawPath%2A> método. Es el <xref:System.Drawing.Graphics.FillPath%2A> método que pinta el interior de los caracteres de la cadena.  
  
 ![Cadena en una ruta de acceso](./media/aboutgdip02-art26.gif "Aboutgdip02_art26")  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.GraphicsPath?displayProperty=nameWithType>
- <xref:System.Drawing.Pen?displayProperty=nameWithType>
- <xref:System.Drawing.Point?displayProperty=nameWithType>
- [Líneas, curvas y formas](lines-curves-and-shapes.md)
- [Cómo: Crear objetos Graphics para dibujar](how-to-create-graphics-objects-for-drawing.md)
- [Crear y dibujar trazados](constructing-and-drawing-paths.md)
