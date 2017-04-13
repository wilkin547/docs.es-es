---
title: "C&#243;mo: Analizar entradas manuscritas con sugerencias de an&#225;lisis | Microsoft Docs"
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
  - "AnalysisHintNode (objetos)"
  - "analizar la entrada manuscrita"
  - "entrada manuscrita, AnalysisHintNode (objetos)"
  - "entrada manuscrita, analizar"
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
caps.latest.revision: 4
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 4
---
# C&#243;mo: Analizar entradas manuscritas con sugerencias de an&#225;lisis
<xref:System.Windows.Ink.AnalysisHintNode> proporciona una sugerencia para el objeto <xref:System.Windows.Ink.InkAnalyzer> al que está asociado.  La sugerencia se aplica al área especificada por la propiedad <xref:System.Windows.Ink.ContextNode.Location%2A> del objeto <xref:System.Windows.Ink.AnalysisHintNode> y proporciona un contexto adicional al analizador de entradas de lápiz para mejorar la exactitud del reconocimiento.  <xref:System.Windows.Ink.InkAnalyzer> aplica esta información contextual al analizar la entrada de lápiz obtenida desde el área de la sugerencia.  
  
## Ejemplo  
 El ejemplo siguiente es una aplicación que usa varios objetos <xref:System.Windows.Ink.AnalysisHintNode> en un formulario que acepta entradas de lápiz.  La aplicación usa la propiedad <xref:System.Windows.Ink.AnalysisHintNode.Factoid%2A> para proporcionar información contextual para cada entrada del formulario.  La aplicación analiza las entradas de lápiz en segundo plano y las borra completamente del formulario cinco segundos después de que el usuario deja de agregar entradas de lápiz.  
  
 [!code-xml[HowToAnalyzeInk#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]