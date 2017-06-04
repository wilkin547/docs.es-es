---
title: "C&#243;mo: Alinear texto dibujado | Microsoft Docs"
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
  - "texto, alinear"
  - "Windows Forms, alinear texto dibujado"
ms.assetid: 83c10a81-1a90-4b5c-98aa-2c6c4b280079
caps.latest.revision: 18
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 18
---
# C&#243;mo: Alinear texto dibujado
Cuando realiza el dibujo personalizado, puede que a menudo desee centrar el texto dibujado en un formulario o control.  Para alinear con facilidad el texto dibujado con los métodos <xref:System.Drawing.Graphics.DrawString%2A> o <xref:System.Windows.Forms.TextRenderer.DrawText%2A>, cree el objeto de formato correcto y establezca los marcadores de formato adecuados.  
  
### Para dibujar texto centrado con GDI\+ \(DrawString\)  
  
1.  Utilice <xref:System.Drawing.StringFormat> con el método <xref:System.Drawing.Graphics.DrawString%2A> adecuado para especificar el texto centrado.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#10)]
     [!code-vb[System.Drawing.AlignDrawnText#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#10)]  
  
### Para dibujar texto centrado con GDI \(DrawText\)  
  
1.  Utilice la enumeración <xref:System.Windows.Forms.TextFormatFlags> para ajustar así como centrar vertical y horizontalmente el texto con el método <xref:System.Windows.Forms.TextRenderer.DrawText%2A> adecuado.  
  
     [!code-csharp[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/CS/Form1.cs#20)]
     [!code-vb[System.Drawing.AlignDrawnText#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlignDrawnText/VB/Form1.vb#20)]  
  
## Compilar el código  
 Los ejemplos de código anteriores están diseñados para formularios Windows Forms y requieren <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Cómo: Construir fuentes y familias de fuentes](../../../../docs/framework/winforms/advanced/how-to-construct-font-families-and-fonts.md)