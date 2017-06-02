---
title: "C&#243;mo: Dibujar texto en una ubicaci&#243;n especificada | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "dibujar texto"
  - "dibujar texto, ubicaciones especificadas [formularios Windows Forms]"
  - "texto, dibujar en ubicación especificada [formularios Windows Forms]"
  - "Windows Forms, dibujar texto en una ubicación especificada"
ms.assetid: 60816423-1c38-465e-980d-2c2b64d74086
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Dibujar texto en una ubicaci&#243;n especificada
Cuando realiza un dibujo personalizado, puede dibujar texto en una sola línea horizontal a partir de un punto especificado.  Para dibujar texto de esta manera, utilice el método sobrecargado <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics> que toma como parámetro <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>.  El método <xref:System.Drawing.Graphics.DrawString%2A> también requiere <xref:System.Drawing.Brush> y <xref:System.Drawing.Font>  
  
 También puede utilizar el método sobrecargado <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de <xref:System.Windows.Forms.TextRenderer>, que toma <xref:System.Drawing.Point>.  <xref:System.Windows.Forms.TextRenderer.DrawText%2A> también requiere <xref:System.Drawing.Color> y <xref:System.Drawing.Font>.  
  
 En la ilustración siguiente se muestra el resultado de un texto dibujado en un punto especificado mediante el método sobrecargado <xref:System.Drawing.Graphics.DrawString%2A>.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext1.png "csfontstext1")  
  
### Para dibujar una línea de texto con GDI\+  
  
1.  Utilice el método <xref:System.Drawing.Graphics.DrawString%2A>, pasando el texto que desee, <xref:System.Drawing.Point> o <xref:System.Drawing.PointF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#30)]
     [!code-vb[System.Drawing.AlignDrawnText#30](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#30)]  
  
### Para dibujar una línea de texto con GDI  
  
1.  Utilice el método <xref:System.Windows.Forms.TextRenderer.DrawText%2A>, pasando el texto que desee, <xref:System.Drawing.Point>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#40)]
     [!code-vb[System.Drawing.AlignDrawnText#40](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#40)]  
  
## Compilar el código  
 Los ejemplos anteriores requieren:  
  
-   <xref:System.Windows.Forms.PaintEventArgs>  `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Cómo: Dibujar texto ajustado en un rectángulo](../../../../docs/framework/winforms/advanced/how-to-draw-wrapped-text-in-a-rectangle.md)