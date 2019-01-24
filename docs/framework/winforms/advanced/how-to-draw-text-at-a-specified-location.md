---
title: Procedimiento Dibujar texto en una ubicación especificada
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
ms.openlocfilehash: e5a1791e21981f60e008b97a51d10f88b827de8d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660377"
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Procedimiento Dibujar texto en una ubicación especificada
Al realizar dibujos personalizados, puede dibujar texto en una sola línea horizontal a partir de un punto especificado. Puede dibujar texto mediante el uso de esta manera el <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clases que toman un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parámetro. El <xref:System.Drawing.Graphics.DrawString%2A> método también requiere una <xref:System.Drawing.Brush> y <xref:System.Drawing.Font>  
  
 También puede usar el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A> También requiere un <xref:System.Drawing.Color> y un <xref:System.Drawing.Font>.  
  
 La siguiente ilustración muestra el resultado del texto dibujado en un punto especificado cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> método sobrecargado.  
  
 ![Fonts Text](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Para dibujar una línea de texto con GDI +  
  
1.  Use la <xref:System.Drawing.Graphics.DrawString%2A> método, pasando el texto que desee, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### <a name="to-draw-a-line-of-text-with-gdi"></a>Para dibujar una línea de texto con GDI  
  
1.  Use la <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método, pasando el texto que desee, <xref:System.Drawing.Point>, <xref:System.Drawing.Font>, y <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos anteriores requieren:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también
- [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)
- [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
- [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
- [Cómo: Dibujar texto ajustado en un rectángulo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
