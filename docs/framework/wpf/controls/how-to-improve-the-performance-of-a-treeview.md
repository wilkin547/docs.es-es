---
title: "C&#243;mo: Mejorar el rendimiento de un control TreeView | Microsoft Docs"
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
  - "TreeView (control) [WPF], mejorar el rendimiento"
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Mejorar el rendimiento de un control TreeView
Si un objeto <xref:System.Windows.Controls.TreeView> contiene gran cantidad de elementos, el tiempo que se tarda en cargarse puede producir un retraso significativo en la interfaz de usuario.  Puede mejorar el tiempo de carga estableciendo la propiedad adjunta <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> en `true`.  La interfaz de usuario también puede reaccionar con lentitud cuando un usuario se desplaza por <xref:System.Windows.Controls.TreeView> utilizando la rueda del mouse o arrastrando el cuadro de una barra de desplazamiento.  Puede mejorar el rendimiento de <xref:System.Windows.Controls.TreeView> cuando el usuario se desplaza estableciendo la propiedad adjunta <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> en <xref:System.Windows.Controls.VirtualizationMode>.  
  
## Ejemplo  
  
## Descripción  
 En el ejemplo siguiente se crea un objeto <xref:System.Windows.Controls.TreeView> que establece la propiedad <xref:System.Windows.Controls.VirtualizingStackPanel.IsVirtualizing%2A?displayProperty=fullName> en true y la propiedad <xref:System.Windows.Controls.VirtualizingStackPanel.VirtualizationMode%2A?displayProperty=fullName> en <xref:System.Windows.Controls.VirtualizationMode>, para optimizar su rendimiento.  
  
## Código  
 [!code-xml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 En el ejemplo siguiente se muestran los datos que se utilizan en el ejemplo anterior.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## Vea también  
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)