---
title: "C&#243;mo: Crear un pincel s&#243;lido | Microsoft Docs"
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
  - "pinceles, crear sólidos"
  - "pinceles, ejemplos"
  - "pinceles de color sólido"
ms.assetid: 85c3fe7d-fb1d-4591-8a9f-d75b556b90af
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Crear un pincel s&#243;lido
Este ejemplo crea un objeto <xref:System.Drawing.SolidBrush> que un objeto <xref:System.Drawing.Graphics> puede utilizar para rellenar formas.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## Programación eficaz  
 Es recomendable hacer una llamada a <xref:System.IDisposable.Dispose%2A> en los objetos que consumen recursos del sistema \(por ejemplo, los objetos Brush\), una vez hayan dejado de utilizarse.  
  
## Vea también  
 <xref:System.Drawing.SolidBrush>   
 <xref:System.Drawing.Brush>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Pinceles y formas rellenas en GDI\+](../../../../docs/framework/winforms/advanced/brushes-and-filled-shapes-in-gdi.md)   
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)