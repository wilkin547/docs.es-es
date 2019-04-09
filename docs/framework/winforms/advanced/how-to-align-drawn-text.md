---
title: Filtrar para alinear texto dibujado
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
ms.openlocfilehash: 5214ef2c69349514f05ba68cc023a7622e119e3a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59210456"
---
# <a name="how-to-align-drawn-text"></a>Filtrar para alinear texto dibujado
Al realizar dibujos personalizados, a menudo es posible que desee centrar el texto dibujado en un formulario o control. Alinear texto dibujado con facilidad el <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> métodos al crear el objeto de formato correcto y establecer las marcas de formato adecuado.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Para dibujar texto con GDI + (DrawString) centrado  
  
1.  Use un <xref:System.Drawing.StringFormat> con los valores adecuados <xref:System.Drawing.Graphics.DrawString%2A> método para especificar el texto centrado.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Para dibujar texto con GDI (DrawText) centrado  
  
1.  Use la <xref:System.Windows.Forms.TextFormatFlags> enumeración para el ajuste, así como para centrar el texto con los valores adecuados en vertical y horizontalmente <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos de código anteriores están diseñados para su uso con Windows Forms y necesitan <xref:System.Windows.Forms.PaintEventArgs>`e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- [Filtrar para dibujar texto con GDI](how-to-draw-text-with-gdi.md)
- [Utilizar fuentes y texto](using-fonts-and-text.md)
- [Filtrar para construir fuentes y familias de fuentes](how-to-construct-font-families-and-fonts.md)
