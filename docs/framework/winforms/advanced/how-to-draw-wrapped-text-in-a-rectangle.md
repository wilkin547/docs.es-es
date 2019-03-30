---
title: Filtrar Dibujar texto ajustado en un rectángulo
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drawing text in a rectangle
- text [Windows Forms], drawing in a rectangle
- strings [Windows Forms], drawing in a rectangle
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
ms.openlocfilehash: 35eca2fc0fe40db1b590f4c599baee01c9a9faf3
ms.sourcegitcommit: 15ab532fd5e1f8073a4b678922d93b68b521bfa0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/29/2019
ms.locfileid: "58654538"
---
# <a name="how-to-draw-wrapped-text-in-a-rectangle"></a>Filtrar Dibujar texto ajustado en un rectángulo
Puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clases que toman un <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF> parámetro. También se puede utilizar un <xref:System.Drawing.Brush> y un <xref:System.Drawing.Font>.  
  
 También puede dibujar texto ajustado en un rectángulo mediante el uso de la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Rectangle> y un <xref:System.Windows.Forms.TextFormatFlags> parámetro. También se puede utilizar un <xref:System.Drawing.Color> y un <xref:System.Drawing.Font>.  
  
 La siguiente ilustración muestra el resultado del texto dibujado en el rectángulo, cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método:
  
 ![Captura de pantalla que muestra el resultado cuando se usa el método DrawString.](./media/how-to-draw-wrapped-text-in-a-rectangle/drawstring-method-font-text.png)  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Para dibujar texto ajustado en un rectángulo con GDI +  
  
1.  Use la <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### <a name="to-draw-wrapped-text-in-a-rectangle-with-gdi"></a>Para dibujar texto ajustado en un rectángulo con GDI  
  
1.  Use la <xref:System.Windows.Forms.TextFormatFlags> se debe ajustar el valor de enumeración para especificar el texto con el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método sobrecargado, pasando el texto que desee, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores requieren:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Dibujar texto con GDI](how-to-draw-text-with-gdi.md)
- [Utilizar fuentes y texto](using-fonts-and-text.md)
- [Cómo: Construir fuentes y familias de fuentes](how-to-construct-font-families-and-fonts.md)
- [Cómo: Dibujar texto en una ubicación especificada](how-to-draw-text-at-a-specified-location.md)
