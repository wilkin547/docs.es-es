---
title: "C&#243;mo: Insertar un elemento en texto mediante programaci&#243;n | Microsoft Docs"
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
  - "elementos, insertar en el texto"
  - "insertar elementos en el texto"
  - "Text Animation (ejemplo)"
  - "texto, insertar elementos"
  - "TextPointer (objetos)"
ms.assetid: 97bd950a-25ac-4e42-a311-94b6420d4136
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Insertar un elemento en texto mediante programaci&#243;n
En el ejemplo siguiente se muestra cómo utilizar dos objetos <xref:System.Windows.Documents.TextPointer> para especificar un intervalo dentro del texto al que se va a aplicar un elemento <xref:System.Windows.Documents.Span>.  
  
## Ejemplo  
 [!code-csharp[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/CSharp/InsertInlineIntoTextExample.cs#insertinlineintotextexamplewholepage)]
 [!code-vb[FlowMiscSnippets_procedural_snip#InsertInlineIntoTextExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FlowMiscSnippets_procedural_snip/VisualBasic/InsertInlineIntoTextExample.vb#insertinlineintotextexamplewholepage)]  
  
 En la ilustración siguiente se muestra cómo queda este ejemplo.  
  
 ![Elemento Span aplicado a un intervalo de texto](../../../../docs/framework/wpf/advanced/media/flow-insertelementintotextprogrammatically.png "Flow\_InsertElementIntoTextProgrammatically")  
  
## Vea también  
 [Información general sobre documentos dinámicos](../../../../docs/framework/wpf/advanced/flow-document-overview.md)