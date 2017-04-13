---
title: "C&#243;mo: Obtener una copia modificable de un elemento Freezable de s&#243;lo lectura | Microsoft Docs"
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
  - "clonar objetos Freezable"
  - "Freezable (objetos), clones modificables"
ms.assetid: d028de61-bbe9-4d62-b656-8fe3b1b2ca24
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Obtener una copia modificable de un elemento Freezable de s&#243;lo lectura
En este ejemplo se muestra cómo utilizar el método <xref:System.Windows.Freezable.Clone%2A> para crear una copia para escritura de un objeto <xref:System.Windows.Freezable>de sólo lectura.  
  
 Una vez que un objeto <xref:System.Windows.Freezable> se marca como de sólo lectura \("inmovilizado"\),  no es posible modificarlo.  Sin embargo, es posible utilizar el método <xref:System.Windows.Freezable.Clone%2A> para crear un clon modificable del objeto inmovilizado.  
  
## Ejemplo  
 En el ejemplo siguiente se crea un clon modificable de un objeto <xref:System.Windows.Media.SolidColorBrush> inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CloneExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#cloneexample)]
 [!code-vb[freezablesample_procedural#CloneExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#cloneexample)]  
  
 Para obtener más información acerca de los objetos <xref:System.Windows.Freezable>, vea [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Vea también  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CloneCurrentValue%2A>   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)