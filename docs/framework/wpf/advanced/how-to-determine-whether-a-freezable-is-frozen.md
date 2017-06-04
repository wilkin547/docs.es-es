---
title: "C&#243;mo: Determinar si un elemento Freezable est&#225; inmovilizado | Microsoft Docs"
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
  - "Freezable (objetos), determinar si están inmovilizados"
  - "IsFrozen (propiedad)"
ms.assetid: 92e58baa-ee12-4a9e-ac3a-ca458807a8b2
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Determinar si un elemento Freezable est&#225; inmovilizado
En este ejemplo se muestra cómo determinar si un objeto <xref:System.Windows.Freezable> está inmovilizado.  Si intenta modificar un objeto <xref:System.Windows.Freezable> inmovilizado, se inicia una excepción <xref:System.InvalidOperationException>.  Para evitarlo, use la propiedad <xref:System.Windows.Freezable.IsFrozen%2A> del objeto <xref:System.Windows.Freezable> para determinar si se encuentra inmovilizado.  
  
## Ejemplo  
 En el ejemplo siguiente se inmoviliza <xref:System.Windows.Media.SolidColorBrush> y, a continuación, se comprueba mediante la propiedad <xref:System.Windows.Freezable.IsFrozen%2A> si se encuentra inmovilizado.  
  
 [!code-csharp[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#checkisfrozenexample)]
 [!code-vb[freezablesample_procedural#CheckIsFrozenExample](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#checkisfrozenexample)]  
  
 Para obtener más información acerca de los objetos <xref:System.Windows.Freezable>, vea [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Vea también  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.IsFrozen%2A>   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)