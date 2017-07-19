---
title: "C&#243;mo: Devolver resultados de una funci&#243;n de p&#225;gina | Microsoft Docs"
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
  - "funciones, devolver"
  - "funciones de página, devolver"
  - "devolver desde funciones de página"
ms.assetid: 87804905-7e8f-417b-b0e3-5622da686396
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Devolver resultados de una funci&#243;n de p&#225;gina
En este ejemplo se muestra cómo devolver un resultado de una función de página.  
  
## Ejemplo  
 Para realizar una devolución desde una función de página, es preciso llamar a <xref:System.Windows.Navigation.PageFunction%601.OnReturn%2A> y pasar una instancia de <xref:System.Windows.Navigation.ReturnEventArgs%601>.  
  
 [!code-xml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml1)]  
[!code-xml[HOWTOPageFunctionSnippets#PageFunctionReturnAResultXAML2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml#pagefunctionreturnaresultxaml2)]  
  
 [!code-csharp[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/csharp/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/CSharp/GetStringPageFunction.xaml.cs#pagefunctionreturnaresultcodebehind)]
 [!code-vb[HOWTOPageFunctionSnippets#PageFunctionReturnAResultCODEBEHIND](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOPageFunctionSnippets/VisualBasic/GetStringPageFunction.xaml.vb#pagefunctionreturnaresultcodebehind)]  
  
## Vea también  
 <xref:System.Windows.Navigation.PageFunction%601>