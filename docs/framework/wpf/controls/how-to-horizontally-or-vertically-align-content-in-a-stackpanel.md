---
title: "C&#243;mo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel | Microsoft Docs"
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
  - "alinear, contenido"
  - "alineación de contenido"
  - "StackPanel (control), alineación de contenido"
ms.assetid: c1e8f962-72c8-4e7a-8670-7a2d7e021791
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Alinear horizontal o verticalmente el contenido de un elemento StackPanel
En este ejemplo se muestra cómo ajustar la propiedad <xref:System.Windows.Controls.StackPanel.Orientation%2A> del contenido de un elemento <xref:System.Windows.Controls.StackPanel> y también cómo ajustar las propiedades <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> de contenido secundario.  
  
## Ejemplo  
 En el ejemplo siguiente se crean tres elementos <xref:System.Windows.Controls.ListBox> en [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)].  Cada <xref:System.Windows.Controls.ListBox> representa los valores posibles de las propiedades <xref:System.Windows.Controls.StackPanel.Orientation%2A>, <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> y <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> de un elemento <xref:System.Windows.Controls.StackPanel>.  Cuando un usuario selecciona un valor en alguno de los elementos <xref:System.Windows.Controls.ListBox>, cambia la propiedad asociada de <xref:System.Windows.Controls.StackPanel> y sus elementos <xref:System.Windows.Controls.Button> secundarios.  
  
 [!code-xml[StackPanelIntroSamp#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml#1)]  
  
 El archivo de código subyacente siguiente define los cambios que se producen en los eventos asociados a los cambios de selección de <xref:System.Windows.Controls.ListBox>.  <xref:System.Windows.Controls.StackPanel> se identifica mediante <xref:System.Windows.FrameworkElement.Name%2A> `sp1`.  
  
 [!code-csharp[StackPanelIntroSamp#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/StackPanelIntroSamp/CSharp/Window1.xaml.cs#2)]
 [!code-vb[StackPanelIntroSamp#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/StackPanelIntroSamp/VisualBasic/Window1.xaml.vb#2)]  
  
## Vea también  
 <xref:System.Windows.Controls.StackPanel>   
 <xref:System.Windows.Controls.ListBox>   
 <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A>   
 <xref:System.Windows.FrameworkElement.VerticalAlignment%2A>   
 [Información general sobre elementos Panel](../../../../docs/framework/wpf/controls/panels-overview.md)