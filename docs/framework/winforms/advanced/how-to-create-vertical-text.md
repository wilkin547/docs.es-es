---
title: "C&#243;mo: Crear texto vertical | Microsoft Docs"
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
  - "cadenas [formularios Windows Forms], dibujar en vertical"
  - "texto [Windows Forms], dibujar en vertical"
  - "texto vertical, dibujar"
  - "Windows Forms, dibujar texto vertical"
ms.assetid: 50c69046-4188-47d9-b949-cc2610ffd337
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Crear texto vertical
Se puede utilizar un objeto <xref:System.Drawing.StringFormat> para especificar que el texto se dibuje en vertical y no en horizontal.  
  
## Ejemplo  
 En el ejemplo siguiente se asigna el valor <xref:System.Drawing.StringFormatFlags> a la propiedad <xref:System.Drawing.StringFormat.FormatFlags%2A> de un objeto <xref:System.Drawing.StringFormat>.  Ese objeto <xref:System.Drawing.StringFormat> se pasa al método <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics>.  El valor <xref:System.Drawing.StringFormatFlags> es un miembro de la enumeración <xref:System.Drawing.StringFormatFlags>.  
  
 En la siguiente ilustración se muestra el texto vertical.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/csfontstext5.png "csfontstext5")  
  
 [!code-csharp[System.Drawing.FontsAndText#31](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.FontsAndText#31](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#31)]  
  
## Compilar el código  
  
-   El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e` , que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)