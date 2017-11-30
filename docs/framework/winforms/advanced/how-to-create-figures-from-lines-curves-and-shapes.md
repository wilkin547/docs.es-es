---
title: "Cómo: Crear figuras a partir de líneas, curvas y formas"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- figures [Windows Forms], creating from shapes
- figures [Windows Forms], creating from lines
ms.assetid: 82fd56c7-b443-4765-9b7c-62ce030656ec
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b382e0e1a627d7f61ce8ac664ac47d98c3725cad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-figures-from-lines-curves-and-shapes"></a>Cómo: Crear figuras a partir de líneas, curvas y formas
Para crear una figura, construya un <xref:System.Drawing.Drawing2D.GraphicsPath>y, a continuación, llamar a métodos, como <xref:System.Drawing.Drawing2D.GraphicsPath.AddLine%2A> y <xref:System.Drawing.Drawing2D.GraphicsPath.AddCurve%2A>, para agregar tipos primitivos a la ruta de acceso.  
  
## <a name="example"></a>Ejemplo  
 Ejemplos de código siguientes crean rutas de acceso que tienen las figuras:  
  
-   El primer ejemplo crea una ruta de acceso que tiene una sola figura. La figura está formada por un único arco. El arco tiene un ángulo de barrido de-180 grados, que está a la izquierda en el sistema de coordenadas de forma predeterminada.  
  
-   El segundo ejemplo crea una ruta de acceso que tiene dos figuras. La primera figura es un arco seguido de una línea. La segunda figura es una línea seguida de una curva seguida de una línea. La primera figura se deja abierta y se cierra la segunda figura.  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#21](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#21)]  
  
 [!code-csharp[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/CS/Class1.cs#22)]
 [!code-vb[System.Drawing.ConstructingDrawingPaths#22](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConstructingDrawingPaths/VB/Class1.vb#22)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de la <xref:System.Windows.Forms.Control.Paint> controlador de eventos.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Drawing2D.GraphicsPath>  
 [Crear y dibujar trazados](../../../../docs/framework/winforms/advanced/constructing-and-drawing-paths.md)  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
