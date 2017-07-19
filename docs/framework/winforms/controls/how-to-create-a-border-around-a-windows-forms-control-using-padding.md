---
title: "C&#243;mo: Crear un borde alrededor de un control de formularios Windows Forms con relleno | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "controles [Windows Forms], Margin (propiedad)"
  - "controles [Windows Forms], esquematizar"
  - "controles [Windows Forms], Padding (propiedad)"
  - "Margin (propiedad) [Windows Forms]"
  - "márgenes"
  - "márgenes, Windows Forms"
  - "Padding (propiedad) [Windows Forms]"
  - "relleno, Windows Forms"
ms.assetid: bac7ed4d-a163-4259-98bd-155a36345890
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Crear un borde alrededor de un control de formularios Windows Forms con relleno
En el ejemplo de código siguiente se muestra cómo crear un borde o un contorno alrededor de un control <xref:System.Windows.Forms.RichTextBox>.  En el ejemplo se establece el valor de la propiedad <xref:System.Windows.Forms.Padding> del control <xref:System.Windows.Forms.Panel> en 5 y se establece la propiedad <xref:System.Windows.Forms.Control.Dock%2A> de un control <xref:System.Windows.Forms.RichTextBox> secundario a <xref:System.Windows.Forms.DockStyle>.  La propiedad <xref:System.Windows.Forms.Control.BackColor%2A> del control <xref:System.Windows.Forms.Panel> se establece en <xref:System.Drawing.Color.Blue%2A>, que crea un borde azul alrededor del control <xref:System.Windows.Forms.RichTextBox>.  
  
## Ejemplo  
 [!code-csharp[System.Windows.Forms.Padding#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.Padding/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.Padding#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.Padding/VB/Form1.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Forms.Padding>   
 [Márgenes y relleno en controles de formularios Windows Forms](../../../../docs/framework/winforms/controls/margin-and-padding-in-windows-forms-controls.md)