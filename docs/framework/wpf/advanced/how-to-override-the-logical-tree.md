---
title: "C&#243;mo: Invalidar el &#225;rbol l&#243;gico | Microsoft Docs"
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
  - "árbol lógico, reemplazar"
  - "invalidar el árbol lógico"
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 8
---
# C&#243;mo: Invalidar el &#225;rbol l&#243;gico
Aunque no es necesario en la mayoría de los casos, los autores de controles avanzados tienen la opción de invalidar el [árbol lógico](GTMT).  
  
## Ejemplo  
 En este ejemplo se describe cómo crear subclases de <xref:System.Windows.Controls.StackPanel> para invalidar el árbol lógico, en este caso se trata de exigir un comportamiento que sólo puede tener el panel y que únicamente representará un solo elemento secundario.  No es un comportamiento necesariamente deseable desde el punto de vista práctico, pero se muestra aquí a fin de ilustrar el escenario de invalidación del árbol lógico normal de un elemento.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](../../../../samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Para obtener más información sobre el árbol lógico, vea [Árboles en WPF](../../../../docs/framework/wpf/advanced/trees-in-wpf.md).