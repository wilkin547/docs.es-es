---
title: "C&#243;mo: Establecer el color de un l&#225;piz | Microsoft Docs"
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
  - "lápices con color"
  - "lápices, establecer color"
ms.assetid: a9df06f9-a6d5-4d9b-a2d1-583943540775
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Establecer el color de un l&#225;piz
En este ejemplo se cambia el color de un objeto <xref:System.Drawing.Pen> ya existente.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#9)]
 [!code-csharp[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#9)]
 [!code-vb[System.Drawing.ConceptualHowTos#9](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#9)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Un objeto <xref:System.Drawing.Pen> llamado  `myPen`.  
  
## Programación eficaz  
 Debe llamar a <xref:System.Drawing.Pen.Dispose%2A> en objetos que consuman recursos del sistema \(como objetos <xref:System.Drawing.Pen>\) cuando haya terminado de utilizarlos.  
  
## Vea también  
 <xref:System.Drawing.Pen>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Cómo: Crear un lápiz](../../../../docs/framework/winforms/advanced/how-to-create-a-pen.md)   
 [Utilizar lápiz para dibujar líneas y formas](../../../../docs/framework/winforms/advanced/using-a-pen-to-draw-lines-and-shapes.md)   
 [Lápices, líneas y rectángulos en GDI\+](../../../../docs/framework/winforms/advanced/pens-lines-and-rectangles-in-gdi.md)