---
title: Procedimiento para dibujar una línea en un formulario Windows Forms
description: Para obtener información sobre cómo dibujar una línea en un formulario, controle el evento Paint y, a continuación, realice el dibujo con la propiedad Graphics de PaintEventArgs.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Graphics.DrawLine
helpviewer_keywords:
- examples [Windows Forms], drawing lines on forms
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- drawing lines
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
ms.openlocfilehash: c8e92dc265c63413275561d0e2e3aa820eaec724
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85621631"
---
# <a name="how-to-draw-a-line-on-a-windows-form"></a>Procedimiento para dibujar una línea en un formulario Windows Forms
En este ejemplo se dibuja una línea en un formulario. Normalmente, cuando se dibuja en un formulario, se controla el evento del formulario <xref:System.Windows.Forms.Control.Paint> y se realiza el dibujo mediante la <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> propiedad de <xref:System.Windows.Forms.PaintEventArgs> , como se muestra en este ejemplo.  
  
## <a name="example"></a>Ejemplo  
 [!code-csharp[System.Drawing.UsingAPen#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro del controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  
  
## <a name="robust-programming"></a>Programación sólida  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en todos los objetos que consumen recursos del sistema, como los <xref:System.Drawing.Pen> objetos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Graphics.DrawLine%2A>
- <xref:System.Windows.Forms.Control.OnPaint%2A>
- [Introducción a la programación de gráficos](getting-started-with-graphics-programming.md)
- [Uso de un lápiz para dibujar líneas y formas](using-a-pen-to-draw-lines-and-shapes.md)
- [Gráficos y dibujos en Windows Forms](graphics-and-drawing-in-windows-forms.md)
