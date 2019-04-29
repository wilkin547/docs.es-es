---
title: Procedimiento para crear figuras a partir de líneas, curvas y formas
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
ms.openlocfilehash: eeaf478375e08734b20d83b6f3c8030732495013
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937701"
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Procedimiento para crear figuras a partir de líneas, curvas y formas
Para crear una figura, construya un <xref:System.Drawing.Drawing2D.GraphicsPath>y, a continuación, llamar a métodos, como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, para agregar tipos primitivos para la ruta de acceso.  
  
## <a name="example"></a>Ejemplo  
 Los siguientes ejemplos de código crean rutas de acceso que tienen las cifras:  
  
- El primer ejemplo crea una ruta de acceso que tiene una sola figura. La figura consta de un único arco. El arco tiene un ángulo de barrido de-180 grados, que está a la izquierda en el sistema de coordenadas predeterminado.  
  
- El segundo ejemplo crea una ruta de acceso que tiene dos figuras. La primera figura es un arco seguido por una línea. La segunda figura es una línea seguida de una curva seguida de una línea. La primera figura está abierta, y la segunda figura está cerrada.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Drawing2D.GraphicsPath>
- [Crear y dibujar trazados](constructing-and-drawing-paths.md)
- [Utilizar lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
