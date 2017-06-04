---
title: "C&#243;mo: Crear Windows Forms con forma | Microsoft Docs"
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
  - "formularios, cambiar la forma"
  - "formularios, circular"
  - "formularios, formas personalizadas"
  - "formularios, no rectangulares"
  - "formularios, redondeado"
  - "formularios con forma"
  - "Windows Forms, circular"
  - "Windows Forms, formas personalizadas"
  - "Windows Forms, forma no rectangular"
  - "Windows Forms, redondeado"
  - "Windows Forms, con forma"
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Crear Windows Forms con forma
En este ejemplo se le da a un formulario una forma elíptica capaz de ir cambiando de tamaño con él.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## Compilar el código  
 Para este ejemplo se necesita:  
  
-   Referencias a los espacios de nombres <xref:System.Windows.Forms> y <xref:System.Drawing>.  
  
 En este ejemplo se reemplaza el método <xref:System.Windows.Forms.Control.OnPaint%2A> para cambiar la forma del formulario.  Para utilizar este código, copie la declaración del método y el código de dibujo contenido en el método.  
  
## Vea también  
 <xref:System.Windows.Forms.Control.OnPaint%2A>   
 <xref:System.Drawing.Region>   
 <xref:System.Drawing>   
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>   
 <xref:System.Windows.Forms.Control.Region%2A>   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)