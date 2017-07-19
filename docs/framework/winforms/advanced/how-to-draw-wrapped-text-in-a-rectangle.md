---
title: "C&#243;mo: Dibujar texto ajustado en un rect&#225;ngulo | Microsoft Docs"
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
  - "cadenas [formularios Windows Forms], dibujar en un rectángulo"
  - "texto [Windows Forms], dibujar en un rectángulo"
  - "Windows Forms, dibujar texto en un rectángulo"
ms.assetid: e1fb432a-dc90-48b5-9b6b-acc14507133d
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Dibujar texto ajustado en un rect&#225;ngulo
Puede dibujar texto ajustado en un rectángulo utilizando el método sobrecargado <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics> que toma como parámetro <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>.  También debe utilizar <xref:System.Drawing.Brush> y <xref:System.Drawing.Font>.  
  
 También puede dibujar texto ajustado en un rectángulo utilizando el método sobrecargado <xref:System.Windows.Forms.TextRenderer.DrawText%2A> de <xref:System.Windows.Forms.TextRenderer> que toma como parámetro <xref:System.Drawing.Rectangle> o <xref:System.Windows.Forms.TextFormatFlags>.  También debe utilizar <xref:System.Drawing.Color> y <xref:System.Drawing.Font>.  
  
 La ilustración siguiente muestra el resultado de un texto dibujado en el rectángulo mediante el método <xref:System.Drawing.Graphics.DrawString%2A>.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext2.png "csfontstext2")  
  
### Para dibujar texto ajustado en un rectángulo con GDI\+  
  
1.  Utilice el método sobrecargado <xref:System.Drawing.Graphics.DrawString%2A>, pasando el texto que desee, <xref:System.Drawing.Rectangle> o <xref:System.Drawing.RectangleF>, <xref:System.Drawing.Font> y <xref:System.Drawing.Brush>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#50)]
     [!code-vb[System.Drawing.AlignDrawnText#50](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#50)]  
  
### Para dibujar texto ajustado en un rectángulo con GDI  
  
1.  Utilice el valor de enumeración de <xref:System.Windows.Forms.TextFormatFlags> para especificar el texto que se va a ajustar con el método sobrecargado <xref:System.Windows.Forms.TextRenderer.DrawText%2A>, pasando el texto que desee, <xref:System.Drawing.Rectangle>, <xref:System.Drawing.Font> y <xref:System.Drawing.Color>.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#60)]
     [!code-vb[System.Drawing.AlignDrawnText#60](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#60)]  
  
## Compilar el código  
 Los ejemplos anteriores requieren:  
  
-   <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)   
 [Cómo: Dibujar texto en una ubicación especificada](../../../../docs/framework/winforms/advanced/how-to-draw-text-at-a-specified-location.md)