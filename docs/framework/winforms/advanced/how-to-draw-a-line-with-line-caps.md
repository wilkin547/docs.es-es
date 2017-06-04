---
title: "C&#243;mo: Dibujar una l&#237;nea con extremos de l&#237;nea | Microsoft Docs"
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
  - "dibujar líneas, extremos de línea"
  - "dibujar, líneas"
  - "líneas, dibujar"
  - "lápices, dibujar líneas"
ms.assetid: eb68c3e1-c400-4886-8a04-76978a429cb6
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Dibujar una l&#237;nea con extremos de l&#237;nea
Puede dibujar el inicio o el final de una línea en una de varias formas llamados extremos de línea.  [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] admite varios extremos de línea, como redondo, cuadrado, en forma de diamante y punta de flecha.  
  
## Ejemplo  
 Los extremos de línea se pueden especificar para el inicio de una línea \(extremo inicial\), el final de una línea \(extremo final\) o los guiones de una línea discontinua \(extremo de guión\).  
  
 En el ejemplo siguiente se dibuja una línea con una punta de flecha en un extremo y un extremo redondeado en el otro lado.  En la ilustración se muestra la línea resultante:  
  
 ![Plumas](../../../../docs/framework/winforms/advanced/media/pens4.png "pens4")  
  
 [!code-csharp[System.Drawing.UsingAPen#71](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#71)]
 [!code-vb[System.Drawing.UsingAPen#71](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#71)]  
  
## Compilar el código  
  
-   Cree un Windows Form y controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario.  Pegue el código de ejemplo en el controlador de eventos <xref:System.Windows.Forms.Control.Paint>, pasando `e` como <xref:System.Windows.Forms.PaintEventArgs>.  
  
## Vea también  
 <xref:System.Drawing.Pen?displayProperty=fullName>   
 <xref:System.Drawing.Drawing2D.LineCap?displayProperty=fullName>   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)