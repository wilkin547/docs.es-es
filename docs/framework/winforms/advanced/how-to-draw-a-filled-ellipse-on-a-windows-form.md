---
title: "C&#243;mo: Dibujar una elipse rellena en Windows Forms | Microsoft Docs"
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
  - "Graphics.FillEllipse"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "círculos, dibujar"
  - "formas circulares"
  - "dibujar, elipses"
  - "elipses, dibujar"
  - "formularios, dibujar elipses"
  - "formas, dibujar"
ms.assetid: 781db806-950d-4c5b-b022-493f7fd0c4a8
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Dibujar una elipse rellena en Windows Forms
En este ejemplo se dibuja una elipse rellena en un formulario.  
  
## Ejemplo  
 [!code-cpp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#1)]
 [!code-csharp[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#1)]
 [!code-vb[System.Drawing.ConceptualHowTos#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#1)]  
  
## Compilar el código  
 No es posible llamar a este método en el controlador de eventos <xref:System.Windows.Forms.Form.Load>.  El contenido representado no se representa de nuevo si el formulario cambia de tamaño o se ve obscurecido por otro formulario.  Para que el contenido se redibuje automáticamente, es recomendable reemplazar el método <xref:System.Windows.Forms.Control.OnPaint%2A>.  
  
## Programación eficaz  
 Siempre debe llamar a <xref:System.IDisposable.Dispose%2A> en los objetos que consuman recursos del sistema, como los objetos <xref:System.Drawing.Brush> y <xref:System.Drawing.Graphics>.  
  
## Vea también  
 [Gráficos y dibujos en Windows Forms](../../../../docs/framework/winforms/advanced/graphics-and-drawing-in-windows-forms.md)   
 [Introducción a la programación de gráficos](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)   
 [Líneas y rellenos con mezcla alfa](../../../../docs/framework/winforms/advanced/alpha-blending-lines-and-fills.md)   
 [Utilizar un pincel para rellenar formas](../../../../docs/framework/winforms/advanced/using-a-brush-to-fill-shapes.md)