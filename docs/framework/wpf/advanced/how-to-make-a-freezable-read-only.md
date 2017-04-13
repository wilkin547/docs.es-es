---
title: "C&#243;mo: Hacer que un elemento Freezable sea de s&#243;lo lectura | Microsoft Docs"
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
  - "Freezable (objetos), convertir en sólo lectura"
ms.assetid: 6c544b7d-d3c9-4736-aa90-4b8728234ccb
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Hacer que un elemento Freezable sea de s&#243;lo lectura
En este ejemplo se muestra cómo convertir <xref:System.Windows.Freezable> en un elemento de sólo lectura mediante una llamada al método <xref:System.Windows.Freezable.Freeze%2A>.  
  
 No se puede inmovilizar un objeto <xref:System.Windows.Freezable> si alguna de las condiciones siguientes es `true` para el objeto:  
  
-   Tiene propiedades animadas o enlazadas a datos.  
  
-   Tiene propiedades que establece un recurso dinámico.  Para obtener más información acerca de los recursos dinámicos, consulte [Recursos XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
-   Contiene subobjetos <xref:System.Windows.Freezable> que no se pueden inmovilizar.  
  
 Si estas condiciones son `false` para el objeto <xref:System.Windows.Freezable> y no piensa modificarlo, puede inmovilizarlo para obtener mejoras de rendimiento.  
  
## Ejemplo  
 En el ejemplo siguiente se inmoviliza un objeto <xref:System.Windows.Media.SolidColorBrush>, que es un tipo de objeto <xref:System.Windows.Freezable>.  
  
 [!code-csharp[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/freezablesample_procedural/CSharp/freezablesample.cs#freezeexample1)]
 [!code-vb[freezablesample_procedural#FreezeExample1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/freezablesample_procedural/visualbasic/freezablesample.vb#freezeexample1)]  
  
 Para obtener más información acerca de los objetos <xref:System.Windows.Freezable>, vea [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md).  
  
## Vea también  
 <xref:System.Windows.Freezable>   
 <xref:System.Windows.Freezable.CanFreeze%2A>   
 <xref:System.Windows.Freezable.Freeze%2A>   
 [Información general sobre objetos Freezable](../../../../docs/framework/wpf/advanced/freezable-objects-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)