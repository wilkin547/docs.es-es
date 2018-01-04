---
title: "Cómo: Dibujar texto en una ubicación especificada"
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
- text [Windows Forms], drawing at specified locations [Windows Forms]
- drawing text
- drawing text [Windows Forms], specified locations [Windows Forms]
- Windows Forms, drawing text at a specified location
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e4ed36740cd7e9478be3b4a7187329fb092c821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-draw-text-at-a-specified-location"></a>Cómo: Dibujar texto en una ubicación especificada
Al realizar un dibujo personalizado, puede dibujar texto en una sola línea horizontal a partir de un punto especificado. Se puede dibujar el texto de esta manera, mediante el uso de la <xref:System.Drawing.Graphics.DrawString%2A> sobrecargar el método de la <xref:System.Drawing.Graphics> clase que toma un <xref:System.Drawing.Point> o <xref:System.Drawing.PointF> parámetro. El <xref:System.Drawing.Graphics.DrawString%2A> método también requiere una <xref:System.Drawing.Brush> y<xref:System.Drawing.Font>  
  
 También puede usar el <xref:System.Windows.Forms.TextRenderer.DrawText%2A> sobrecargar el método de la <xref:System.Windows.Forms.TextRenderer> que toma un <xref:System.Drawing.Point>. <xref:System.Windows.Forms.TextRenderer.DrawText%2A>También requiere un <xref:System.Drawing.Color> y <xref:System.Drawing.Font>.  
  
 En la siguiente ilustración muestra el resultado del texto dibujado en un punto especificado cuando se usa el <xref:System.Drawing.Graphics.DrawString%2A> el método sobrecargado.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
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
 [Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)  
 [Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)  
 [Dibujar texto ajustado en un rectángulo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)
