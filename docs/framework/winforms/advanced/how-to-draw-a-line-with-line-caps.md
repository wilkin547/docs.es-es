---
title: 'Cómo: Dibujar una línea con extremos de línea'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drawing [Windows Forms], lines
- lines [Windows Forms], drawing
- pens [Windows Forms], drawing lines
- drawing lines [Windows Forms], line caps
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
ms.openlocfilehash: be492f2317d4677776cc9f89f546c935d271019b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33523226"
---
# <a name="how-to-draw-a-line-with-line-caps"></a>Cómo: Dibujar una línea con extremos de línea
Puede dibujar el inicio o el final de una línea en una de varias formas llamadas extremos de línea. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] admite varios extremos de línea, como redondo, cuadrado, rombo y punta de flecha.  
  
## <a name="example"></a>Ejemplo  
 Puede especificar extremos de línea para el inicio de una línea (extremo inicial), el final de una línea (extremo final) o los guiones de una línea discontinua (extremo de guión).  
  
 En el ejemplo siguiente se dibuja una línea con una punta de flecha en un extremo y un extremo redondeado en el otro extremo. La ilustración muestra la línea resultante:  
  
 ![Lápices](../../../../docs/framework/winforms/advanced/media/pens4.gif "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
  
-   Crear un formulario Windows Forms y controlar el formato <xref:System.Windows.Forms.Control.Paint> eventos. Pegue el código de ejemplo en el <xref:System.Windows.Forms.Control.Paint> controlador de eventos pasando `e` como <xref:System.Windows.Forms.PaintEventArgs>.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Drawing.Pen?displayProperty=nameWithType>  
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=nameWithType>  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)
