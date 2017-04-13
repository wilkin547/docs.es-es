---
title: "C&#243;mo: Buscar un elemento por su nombre | Microsoft Docs"
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
  - "elementos, buscar por nombre"
  - "FindName (método)"
ms.assetid: cfa7cf35-8aa2-4060-9454-872ed4af3f0e
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Buscar un elemento por su nombre
En este ejemplo se describe cómo utilizar el método <xref:System.Windows.FrameworkElement.FindName%2A> para buscar un elemento por su valor de <xref:System.Windows.FrameworkElement.Name%2A>.  
  
## Ejemplo  
 En este ejemplo, el método para buscar un elemento determinado por su nombre se escribe como el controlador de eventos de un botón.  `stackPanel` es la propiedad <xref:System.Windows.FrameworkElement.Name%2A> del elemento <xref:System.Windows.FrameworkElement> raíz donde se realiza la búsqueda; a continuación, el método de ejemplo indica visualmente cuál es el elemento buscado convirtiéndolo en un <xref:System.Windows.Controls.TextBlock> y cambiando una de las propiedades de <xref:System.Windows.Controls.TextBlock> visibles de [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)].  
  
 [!code-csharp[FEFindName#Find](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FEFindName/CSharp/default.xaml.cs#find)]
 [!code-vb[FEFindName#Find](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FEFindName/VisualBasic/default.xaml.vb#find)]