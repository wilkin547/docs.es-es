---
title: "C&#243;mo: Obtener el valor devuelto por una funci&#243;n de p&#225;gina | Microsoft Docs"
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
  - "funciones, obtener valores devueltos de"
  - "obtener, valores devueltos de funciones de página"
  - "funciones de página, obtener valores devueltos de"
  - "valores devueltos de funciones de página"
ms.assetid: 75470af6-256c-4c46-87e7-705080723a1c
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Obtener el valor devuelto por una funci&#243;n de p&#225;gina
En este ejemplo se muestra cómo obtener el resultado devuelto por una función de página.  
  
## Ejemplo  
 Para obtener el resultado devuelto por una función de página, es preciso controlar el evento <xref:System.Windows.Navigation.PageFunction%601.Return> de la función de página a la que llama.  
  
 [!code-xml[HOWTOPageFunctionSnippets#CallAPageFunctionXAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml#callapagefunctionxaml)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/CallingPage.xaml.cs#getpagefunctionresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#GetPageFunctionResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/CallingPage.xaml.vb#getpagefunctionresultcodebehind)]  
  
## Vea también  
 <xref:System.Windows.Navigation.PageFunction%601>