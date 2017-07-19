---
title: "C&#243;mo: Dibujar un rect&#225;ngulo relleno en Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Graphics.FillRectangle"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "dibujar rectángulos"
  - "dibujar, rectángulos"
  - "rectángulos, dibujar"
ms.assetid: d656a93c-987d-4809-aafd-493fe17450f0
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dibujar un rect&#225;ngulo relleno en Windows Forms
En este ejemplo se dibuja un rectángulo relleno en un formulario.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#2)]
 [!code-csharp[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#2)]
 [!code-vb[System.Drawing.ConceptualHowTos#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#2)]  
  
## Compilar el código  
 No es posible llamar a este método en el controlador de eventos <xref:System.Windows.Forms.Form.Load>.  El contenido representado no se representa de nuevo si el formulario cambia de tamaño o se ve obscurecido por otro formulario.  Para que el contenido se redibuje automáticamente, es recomendable reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Programación eficaz  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como los objetos <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics>.  
  
## Vea también  
 <xref:System.Drawing.Graphics.FillRectangle%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Pinceles y formas rellenas en GDI\+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)