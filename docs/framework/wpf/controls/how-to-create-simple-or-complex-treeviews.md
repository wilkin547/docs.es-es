---
title: "C&#243;mo: Crear controles TreeView simples o complejos | Microsoft Docs"
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
  - "Control (clase), TreeView, crear"
  - "TreeView (control), crear"
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Crear controles TreeView simples o complejos
En este ejemplo se muestra cómo crear controles <xref:System.Windows.Controls.TreeView> simples o complejos.  
  
 <xref:System.Windows.Controls.TreeView> está compuesto de una jerarquía de controles <xref:System.Windows.Controls.TreeViewItem>, que pueden contener cadenas de texto simples y también contenido más complejo, como controles <xref:System.Windows.Controls.Button> o un control <xref:System.Windows.Controls.StackPanel> con contenido incrustado.  Puede definir explícitamente el contenido de <xref:System.Windows.Controls.TreeView> o bien proporcionarlo mediante un origen de datos.  En este tema se proporcionan ejemplos de estos conceptos.  
  
## Ejemplo  
 La propiedad <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> de <xref:System.Windows.Controls.TreeViewItem> incluye el contenido que <xref:System.Windows.Controls.TreeView> muestra para ese elemento.  <xref:System.Windows.Controls.TreeViewItem> también puede tener controles <xref:System.Windows.Controls.TreeViewItem> como elementos secundarios y puede definir estos elementos secundarios mediante la propiedad <xref:System.Windows.Controls.ItemsControl.Items%2A>.  
  
 En el ejemplo siguiente se muestra cómo definir explícitamente el contenido de <xref:System.Windows.Controls.TreeViewItem> estableciendo la propiedad <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> en una cadena de texto.  
  
 [!code-xml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 En el ejemplo siguiente se muestra cómo definir los elementos secundarios de <xref:System.Windows.Controls.TreeViewItem> definiendo propiedades <xref:System.Windows.Controls.ItemsControl.Items%2A> que son controles <xref:System.Windows.Controls.Button>.  
  
 [!code-xml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.TreeView> en el que <xref:System.Windows.Data.XmlDataProvider> proporciona el contenido de <xref:System.Windows.Controls.TreeViewItem> y <xref:System.Windows.HierarchicalDataTemplate> define la apariencia del contenido.  
  
 [!code-xml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 En el ejemplo siguiente se muestra cómo crear un control <xref:System.Windows.Controls.TreeView> en el que el contenido de <xref:System.Windows.Controls.TreeViewItem> incluye controles <xref:System.Windows.Controls.DockPanel> con contenido incrustado.  
  
 [!code-xml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## Vea también  
 <xref:System.Windows.Controls.TreeView>   
 <xref:System.Windows.Controls.TreeViewItem>   
 [Introducción a TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)   
 [Temas "Cómo..."](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)