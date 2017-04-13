---
title: "C&#243;mo: Buscar un gui&#243;n gr&#225;fico de forma sincr&#243;nica | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-wpf"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "buscar guiones gráficos de forma sincrónica"
  - "Guiones gráficos, buscar de forma sincrónica"
ms.assetid: 03e06271-a946-4810-88ea-3fb4cfa9e0f1
caps.latest.revision: 8
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Buscar un gui&#243;n gr&#225;fico de forma sincr&#243;nica
En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.SeekAlignedToLastTick%2A> de <xref:System.Windows.Media.Animation.Storyboard> para buscar sincrónicamente hasta cualquier posición de una animación de guión gráfico.  
  
## Ejemplo  
 A continuación se muestra el marcado XAML del ejemplo.  
  
 [!code-xml[SeekStoryboard_snip#SeekStoryboardSynchronouslyExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml#seekstoryboardsynchronouslyexamplewholepage)]  
  
## Ejemplo  
 A continuación, se muestra el código utilizado con el marcado XAML anterior.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardSynchronouslyExample.xaml.cs#seekstoryboardsynchronouslycodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardSynchronouslyCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardSynchronouslyExample.xaml.vb#seekstoryboardsynchronouslycodebehindexamplewholepage)]