---
title: Procedimiento para dibujar un rectángulo con relleno en un formulario Windows Forms
description: Obtenga información sobre cómo dibujar mediante programación un rectángulo relleno en Windows Forms. Obtenga también información sobre cómo compilar el código.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- Graphics.FillRectangle
helpviewer_keywords:
- drawing [Windows Forms], rectangles
- rectangles [Windows Forms], drawing
- drawing rectangles
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
ms.openlocfilehash: 0ad8ec97000e29b2194a9eda713aa43d5557b44c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621644"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Procedimiento para dibujar un rectángulo con relleno en un formulario Windows Forms
En este ejemplo se dibuja un rectángulo relleno en un formulario.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 No se puede llamar a este método en el <xref:System.Windows.Forms.Form.Load> controlador de eventos. El contenido dibujado no se volverá a dibujar si el formulario cambia de tamaño o está oculto en otro formulario. Para que el contenido se vuelva a dibujar automáticamente, debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en todos los objetos que consumen recursos del sistema, como los <xref:System.Drawing.Brush> <xref:System.Drawing.Graphics> objetos y.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
- [Uso de un lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Pinceles y formas rellenas en GDI+](brushes-and-filled-shapes-in-gdi.md)
