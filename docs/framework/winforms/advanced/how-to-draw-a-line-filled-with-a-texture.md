---
title: "C&#243;mo: Dibujar una l&#237;nea rellena con una textura | Microsoft Docs"
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
  - "dibujar líneas, textura"
  - "dibujar, líneas"
  - "líneas, textura"
ms.assetid: dc9118cc-f3c2-42e5-8173-f46d41d18fd5
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Dibujar una l&#237;nea rellena con una textura
Las líneas se pueden dibujar con una textura en lugar de dibujarse con un color sólido.  Para dibujar líneas y curvas con una textura, cree un objeto <xref:System.Drawing.TextureBrush> y páselo a un constructor <xref:System.Drawing.Pen.%23ctor%2A>.  El mapa de bits asociado al pincel de la textura se utiliza para organizar el plano en mosaico \(de manera invisible\) y, cuando el lápiz dibuja una línea o curva, el trazo del lápiz destapa algunos de los píxeles de la textura con diseño de mosaico.  
  
## Ejemplo  
 En el siguiente ejemplo se crea un objeto <xref:System.Drawing.Bitmap> a partir del archivo `Texture1.jpg`.  Ese mapa de bits se utiliza para construir un objeto <xref:System.Drawing.TextureBrush> que, a continuación, se utiliza para construir un objeto <xref:System.Drawing.Pen>.  La llamada a <xref:System.Drawing.Graphics.DrawImage%2A> dibuja el mapa de bits con la esquina superior izquierda en \(0, 0\).  La llamada a <xref:System.Drawing.Graphics.DrawEllipse%2A> utiliza el objeto <xref:System.Drawing.Pen> para dibujar una elipse con textura.  
  
 En la siguiente ilustración se muestran el mapa de bits y la elipse.  
  
 ![Plumas](../../../../docs/framework/winforms/advanced/media/pens7.png "pens7")  
  
 [!code-csharp[System.Drawing.UsingAPen#61](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.UsingAPen/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.UsingAPen#61](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.UsingAPen/VB/Class1.vb#61)]  
  
## Compilar el código  
 Cree un Windows Form y controle el evento <xref:System.Windows.Forms.Control.Paint> del formulario.  Pegue el código anterior en el controlador de eventos <xref:System.Windows.Forms.Control.Paint>.  Reemplace `Texture.jpg` por una imagen válida en su sistema.  
  
## Vea también  
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)