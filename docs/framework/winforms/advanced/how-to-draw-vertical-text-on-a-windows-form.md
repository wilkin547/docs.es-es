---
title: "C&#243;mo: Dibujar texto vertical en Windows Forms | Microsoft Docs"
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
  - "StringFormat.FormatFlags"
  - "Graphics.DrawString"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "cadenas [formularios Windows Forms], dibujar en vertical"
  - "texto [Windows Forms], dibujar"
  - "texto [Windows Forms], dibujar en vertical"
  - "texto [Windows Forms], texto vertical"
ms.assetid: 717a6131-00f6-4373-b574-9894e8317799
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Dibujar texto vertical en Windows Forms
En el ejemplo de código siguiente se muestra cómo dibujar texto vertical en un formulario mediante el método <xref:System.Drawing.Graphics.DrawString%2A> de <xref:System.Drawing.Graphics>.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#8)]
 [!code-csharp[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#8)]
 [!code-vb[System.Drawing.ConceptualHowTos#8](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#8)]  
  
## Compilar el código  
 No es posible llamar a este método en el controlador de eventos <xref:System.Windows.Forms.Form.Load>.  El contenido representado no se representa de nuevo si el formulario cambia de tamaño o se ve obscurecido por otro formulario.  Para que el contenido se redibuje automáticamente, es recomendable reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Programación eficaz  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   La fuente Arial no está instalada.  
  
## Vea también  
 <xref:System.Drawing.Graphics.DrawString%2A>   
 <xref:System.Drawing.StringFormat.FormatFlags%2A>   
 <xref:System.Drawing.StringFormatFlags>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)