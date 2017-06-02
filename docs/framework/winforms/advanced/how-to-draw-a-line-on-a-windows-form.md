---
title: "C&#243;mo: Dibujar una l&#237;nea en Windows Forms | Microsoft Docs"
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
  - "Graphics.DrawLine"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "dibujar líneas"
  - "dibujar, líneas"
  - "ejemplos [Windows Forms], dibujar líneas en formularios"
  - "líneas, dibujar"
ms.assetid: 55c1dbeb-75d0-430c-9814-a24b8971ad8c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Dibujar una l&#237;nea en Windows Forms
En este ejemplo se dibuja una línea en un formulario.  Normalmente, cuando se dibuja en un formulario, se controla el evento <xref:System.Windows.Forms.Control.Paint> del formulario y se realiza el gráfico mediante la propiedad <xref:System.Windows.Forms.PaintEventArgs.Graphics%2A> de <xref:System.Windows.Forms.PaintEventArgs>, como se muestra en este ejemplo.  
  
## Ejemplo  
 [!code-csharp[System.Drawing.UsingAPen#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.UsingAPen#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro del controlador del evento <xref:System.Windows.Forms.Control.Paint>.  
  
## Programación eficaz  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como los objetos <xref:System.Drawing.Pen>.  
  
## Vea también  
 <xref:System.Drawing.Graphics.DrawLine%2A>   
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)