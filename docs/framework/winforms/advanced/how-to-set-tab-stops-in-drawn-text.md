---
title: "C&#243;mo: Establecer posiciones de tabulaci&#243;n en texto dibujado | Microsoft Docs"
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
  - "pestañas, texto dibujado"
  - "texto, dibujar con posiciones de tabulación"
ms.assetid: 64878f98-39ba-4303-b63f-0859ab682eeb
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer posiciones de tabulaci&#243;n en texto dibujado
Se pueden establecer posiciones de tabulaciones para el texto llamando al método <xref:System.Drawing.StringFormat.SetTabStops%2A> de un objeto <xref:System.Drawing.StringFormat> y luego pasar dicho objeto <xref:System.Drawing.StringFormat> al método <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics>.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.TextRenderer?displayProperty=fullName> no admite la adición de posiciones de tabulaciones para representar texto, aunque se pueden ampliar las tabulaciones existentes mediante el marcador <xref:System.Windows.Forms.TextFormatFlags?displayProperty=fullName>.  
  
## Ejemplo  
 En el ejemplo siguiente se establecen tabulaciones en 150, 250 y 350.  A continuación, el código muestra una lista tabulada de nombres y resultados de pruebas.  
  
 En la siguiente ilustración se muestra el texto tabulado.  
  
 ![Texto de las fuentes](../../../../docs/framework/winforms/advanced/media/fontstext4.png "fontstext4")  
  
 El código siguiente pasa dos argumentos al método <xref:System.Drawing.StringFormat.SetTabStops%2A>.  El segundo argumento es una matriz que contiene los desplazamientos de las tabulaciones.  El primer argumento que se pasa al método <xref:System.Drawing.StringFormat.SetTabStops%2A> es 0, lo que indica que el primer desplazamiento de la matriz se mide desde la posición 0, el borde izquierdo del rectángulo delimitador.  
  
 [!code-csharp[System.Drawing.FontsAndText#41](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.FontsAndText#41](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#41)]  
  
## Compilar el código  
  
-   El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)   
 [Cómo: Dibujar texto con GDI](../../../../docs/framework/winforms/advanced/how-to-draw-text-with-gdi.md)