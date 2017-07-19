---
title: "C&#243;mo: Dibujar una forma con contorno | Microsoft Docs"
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
  - "Graphics.DrawEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "círculos"
  - "círculos, dibujar"
  - "formas circulares"
  - "dibujar, formas circulares"
  - "dibujar, formas"
  - "elipses, dibujar"
  - "formularios, dibujar formas circulares"
  - "formas con contorno, dibujar"
  - "formas con contorno, ejemplos"
  - "formas, dibujar"
ms.assetid: f4f9214c-607e-407d-8cdd-6549f0278451
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dibujar una forma con contorno
En este ejemplo se dibujan contornos de elipses y rectángulos en un formulario.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#6)]
 [!code-csharp[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#6)]
 [!code-vb[System.Drawing.ConceptualHowTos#6](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#6)]  
  
## Compilar el código  
 No es posible llamar a este método en el controlador de eventos <xref:System.Windows.Forms.Form.Load>.  El contenido representado no se representa de nuevo si el formulario cambia de tamaño o se ve obscurecido por otro formulario.  Para que el contenido se redibuje automáticamente, es recomendable reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Programación eficaz  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como los objetos <xref:System.Drawing.Pen> y <xref:System.Drawing.Graphics>.  
  
## Vea también  
 <xref:System.Drawing.Graphics.DrawEllipse%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Graphics.DrawRectangle%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)