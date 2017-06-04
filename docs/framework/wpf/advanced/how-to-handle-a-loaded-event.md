---
title: "C&#243;mo: Controlar un evento cargado | Microsoft Docs"
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
  - "eventos, Cargado"
  - "Loaded (eventos)"
  - "XAML, Loaded (eventos)"
ms.assetid: 0cf8d003-8441-4df4-807a-6db09347e829
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Controlar un evento cargado
En este ejemplo se muestra cómo controlar el evento <xref:System.Windows.FrameworkElement.Loaded?displayProperty=fullName> y se facilita un escenario adecuado para ello.  El controlador crea un control <xref:System.Windows.Controls.Button> al cargarse la página.  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] junto con un archivo de código subyacente.  
  
 [!code-xml[FELoaded#XAML](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml#xaml)]  
  
 [!code-csharp[FELoaded#Handler](../../../../samples/snippets/csharp/VS_Snippets_Wpf/FELoaded/CSharp/default.xaml.cs#handler)]
 [!code-vb[FELoaded#Handler](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/FELoaded/VisualBasic/default.xaml.vb#handler)]  
  
## Vea también  
 <xref:System.Windows.FrameworkElement>   
 [Eventos de duración de objetos](../../../../docs/framework/wpf/advanced/object-lifetime-events.md)   
 [Información general sobre eventos enrutados](../../../../docs/framework/wpf/advanced/routed-events-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/base-elements-how-to-topics.md)