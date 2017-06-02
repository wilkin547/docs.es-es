---
title: "C&#243;mo: Enumerar las fuentes instaladas | Microsoft Docs"
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
  - "ejemplos [Windows Forms], fuentes"
  - "fuentes, enumerar fuentes instaladas"
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Enumerar las fuentes instaladas
La clase <xref:System.Drawing.Text.InstalledFontCollection> hereda de la clase base abstracta <xref:System.Drawing.Text.FontCollection>.  Se puede usar un objeto <xref:System.Drawing.Text.InstalledFontCollection> para enumerar las fuentes instaladas en el equipo.  La propiedad <xref:System.Drawing.Text.FontCollection.Families%2A> de un objeto <xref:System.Drawing.Text.InstalledFontCollection> contiene una matriz de objetos <xref:System.Drawing.FontFamily>.  
  
## Ejemplo  
 En el ejemplo siguiente se enumeran los nombres de todas las familias de fuentes instaladas en el equipo.  El código recupera la propiedad <xref:System.Drawing.FontFamily.Name%2A> de cada objeto <xref:System.Drawing.FontFamily> en la matriz devuelta por la propiedad <xref:System.Drawing.Text.FontCollection.Families%2A>.  Según se van recuperando los nombres de las familias, se concatenan para formar una lista separada por comas.  Después, el método <xref:System.Drawing.Graphics.DrawString%2A> de la clase <xref:System.Drawing.Graphics> dibuja la lista separada por comas en un rectángulo.  
  
 Si se ejecuta el código de ejemplo, el resultado será similar al que se muestra en la siguiente ilustración.  
  
 ![Fuentes instaladas](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## Compilar el código  
 El ejemplo anterior está diseñado para formularios Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  Además, debería importar el espacio de nombres <xref:System.Drawing.Text>.  
  
## Vea también  
 [Utilizar fuentes y texto](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)