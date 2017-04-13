---
title: "C&#243;mo: Dibujar texto en Windows Forms | Microsoft Docs"
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
  - "formularios, dibujar texto"
  - "texto, dibujar"
ms.assetid: 5d2447a9-21a1-4adc-b954-5516f2bb9b2c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Dibujar texto en Windows Forms
En el ejemplo de código siguiente se muestra cómo utilizar el método <xref:System.Drawing.Graphics.DrawString%2A> de <xref:System.Drawing.Graphics> para dibujar texto en un formulario.  Por otra parte, puede utilizar <xref:System.Windows.Forms.TextRenderer> para dibujar texto en un formulario.  Para obtener más información, vea [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md).  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#7)]
 [!code-csharp[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#7)]
 [!code-vb[System.Drawing.ConceptualHowTos#7](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#7)]  
  
## Compilar el código  
 No puede llamar al método <xref:System.Drawing.Graphics.DrawString%2A> en el controlador de eventos <xref:System.Windows.Forms.Form.Load>.  El contenido representado no se representa de nuevo si el formulario cambia de tamaño o se ve obscurecido por otro formulario.  Para que el contenido se redibuje automáticamente, es recomendable reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La fuente Arial no está instalada.  
  
## Vea también  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Windows.Forms.TextRenderer.DrawText%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.TextFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)