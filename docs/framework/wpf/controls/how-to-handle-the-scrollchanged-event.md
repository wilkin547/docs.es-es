---
title: "C&#243;mo: Controlar el evento ScrollChanged | Microsoft Docs"
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
  - "ScrollChanged (eventos)"
  - "ScrollViewer (control), provocar eventos ScrollChanged"
ms.assetid: 42c695d8-ee28-49d4-80fd-fc71e9be7f29
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Controlar el evento ScrollChanged
## Ejemplo  
 En este ejemplo se muestra cómo controlar el evento <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> de un objeto <xref:System.Windows.Controls.ScrollViewer>.  
  
 Un elemento <xref:System.Windows.Documents.FlowDocument> con partes <xref:System.Windows.Documents.Paragraph> se define en código [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)].  Cuando se produce el evento <xref:System.Windows.Controls.ScrollViewer.ScrollChanged> debido a la interacción con el usuario, se invoca un controlador y el texto se escribe en <xref:System.Windows.Controls.TextBlock>, que indica que el evento se ha producido.  
  
 [!code-xml[scrollchangedeventargsLayout#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#1)]  
[!code-xml[scrollchangedeventargsLayout#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[scrollchangedeventargsLayout#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/scrollchangedeventargsLayout/CSharp/Window1.xaml.cs#3)]
 [!code-vb[scrollchangedeventargsLayout#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/scrollchangedeventargsLayout/VisualBasic/Window1.xaml.vb#3)]  
  
## Vea también  
 <xref:System.Windows.Controls.ScrollViewer>   
 <xref:System.Windows.Controls.ScrollViewer.ScrollChanged>   
 <xref:System.Windows.Controls.ScrollChangedEventHandler>   
 <xref:System.Windows.Controls.ScrollChangedEventArgs>