---
title: "C&#243;mo: Crear un l&#225;piz | Microsoft Docs"
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
  - "gráficos, crear lápices"
  - "Pen (objeto)"
  - "lápices, crear"
ms.assetid: 7fbea8b7-7ac1-4413-9c17-733a850381e3
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Crear un l&#225;piz
Este ejemplo crea un objeto <xref:System.Drawing.Pen>.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#3)]
 [!code-csharp[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#3)]
 [!code-vb[System.Drawing.ConceptualHowTos#3](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#3)]  
  
## Programación eficaz  
 Cuando haya dejado de utilizar objetos que consumen recursos del sistema, como <xref:System.Drawing.Pen>, debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en dichos objetos.  
  
## Vea también  
 <xref:System.Drawing.Pen>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Lápices, líneas y rectángulos en GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)