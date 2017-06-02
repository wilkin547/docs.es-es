---
title: "C&#243;mo: Buscar un gui&#243;n gr&#225;fico | Microsoft Docs"
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
  - "buscar guiones gráficos"
  - "Guiones gráficos, buscar"
ms.assetid: 887bb39a-0c2a-4ae8-956d-1d9f6f8ebbfc
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 3
---
# C&#243;mo: Buscar un gui&#243;n gr&#225;fico
En el ejemplo siguiente se muestra cómo utilizar el método <xref:System.Windows.Media.Animation.Storyboard.Seek%2A> de <xref:System.Windows.Media.Animation.Storyboard> para saltar a cualquier posición en una animación de guión gráfico.  
  
## Ejemplo  
 A continuación se muestra el marcado XAML del ejemplo.  
  
 [!code-xml[SeekStoryboard_snip#SeekStoryboardExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml#seekstoryboardexamplewholepage)]  
  
## Ejemplo  
 A continuación, se muestra el código utilizado con el marcado XAML anterior.  
  
 [!code-csharp[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SeekStoryboard_snip/CSharp/SeekStoryboardExample.xaml.cs#seekstoryboardcodebehindexamplewholepage)]
 [!code-vb[SeekStoryboard_snip#SeekStoryboardCodeBehindExampleWholePage](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SeekStoryboard_snip/VisualBasic/SeekStoryboardExample.xaml.vb#seekstoryboardcodebehindexamplewholepage)]  
  
## Vea también  
 [Buscar guiones gráficos de forma sincrónica](../../../../docs/framework/wpf/graphics-multimedia/how-to-seek-a-storyboard-synchronously.md)