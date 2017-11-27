---
title: "Cómo: Alinear texto dibujado"
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
- text [Windows Forms], aligning
- Windows Forms, aligning drawn text
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a2f2f6bd088ad58277839cf7e32a98d67ca3bd15
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-align-drawn-text"></a>Cómo: Alinear texto dibujado
Al realizar un dibujo personalizado, a menudo puede Centrar el texto dibujado en un formulario o control. Puede alinear texto dibujado con facilidad el <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A> métodos al crear el objeto de formato correcto y establecer las marcas de formato adecuado.  
  
### <a name="to-draw-centered-text-with-gdi-drawstring"></a>Para dibujar texto centrado con GDI + (DrawString)  
  
1.  Use un <xref:System.Drawing.StringFormat> con el adecuado <xref:System.Drawing.Graphics.DrawString%2A> método para especificar el texto centrado.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### <a name="to-draw-centered-text-with-gdi-drawtext"></a>Para dibujar texto centrado con GDI (DrawText)  
  
1.  Use la <xref:System.Windows.Forms.TextFormatFlags> enumeración para el ajuste, así como verticalmente y horizontalmente centrar el texto con el adecuado <xref:System.Windows.Forms.TextRenderer.DrawText%2A> método.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 Los ejemplos de código anteriores están diseñados para su uso con Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también  
 [Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)
