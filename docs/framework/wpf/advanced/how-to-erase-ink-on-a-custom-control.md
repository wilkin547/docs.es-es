---
title: "C&#243;mo: Borrar la entrada manuscrita en un control personalizado | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "controles personalizados, borrar entrada manuscrita en"
  - "entrada manuscrita, borrar en controles personalizados"
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Borrar la entrada manuscrita en un control personalizado
<xref:System.Windows.Ink.IncrementalStrokeHitTester> determina si el trazo dibujado actualmente se cruza con otro trazo.  Es útil para crear un control que permita al usuario borrar partes de un trazo de la misma manera que lo hace en un <xref:System.Windows.Controls.InkCanvas> cuando la propiedad <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> está establecida en <xref:System.Windows.Controls.InkCanvasEditingMode>.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un control personalizado que permite al usuario borrar partes de trazos.  En el ejemplo se crea un control que contiene entrada de lápiz cuando se inicializa.  Para crear un control que recopile entradas de lápiz, vea [Creación de un control de entrada manuscrita](../../../../docs/framework/wpf/advanced/creating-an-ink-input-control.md).  
  
 [!code-csharp[HowToEraseInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]