---
title: Procedimiento Dibujar un rectángulo relleno en un formulario de Windows
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
ms.openlocfilehash: a9722b2939e77282453743a4dea165a340412a21
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587039"
---
# <a name="how-to-draw-a-filled-rectangle-on-a-windows-form"></a>Procedimiento Dibujar un rectángulo relleno en un formulario de Windows
En este ejemplo se dibuja un rectángulo relleno en un formulario.  
  
## <a name="example"></a>Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 No se puede llamar a este método el <xref:System.Windows.Forms.Form.Load> controlador de eventos. No se volverá a dibujar el contenido dibujado si el formulario cambia de tamaño u ocultado por otro formulario. Para que el contenido automáticamente volver a dibujar, se debe reemplazar el <xref:System.Windows.Forms.Control.OnPaint%2A> método.  
  
## <a name="robust-programming"></a>Programación sólida  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics> objetos.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Drawing.Graphics.FillRectangle%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
- [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)
- [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
- [Pinceles y formas rellenas en GDI+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)
