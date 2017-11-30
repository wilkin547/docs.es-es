---
title: "Cómo: Crear controles TreeView simples o complejos"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5e09f0f39d0c9a40a0e91299d308921917067166
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>Cómo: Crear controles TreeView simples o complejos
Este ejemplo muestra cómo crear simples o complejas <xref:System.Windows.Controls.TreeView> controles.  
  
 A <xref:System.Windows.Controls.TreeView> consta de una jerarquía de <xref:System.Windows.Controls.TreeViewItem> controles, que pueden contener cadenas de texto simple y también contenido más complejo, como <xref:System.Windows.Controls.Button> controles o <xref:System.Windows.Controls.StackPanel> con contenido incrustado. Puede definir explícitamente el <xref:System.Windows.Controls.TreeView> contenido o un origen de datos puede proporcionar el contenido. Este tema ofrecen ejemplos de estos conceptos.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad de la <xref:System.Windows.Controls.TreeViewItem> incluye el contenido que el <xref:System.Windows.Controls.TreeView> muestra para ese elemento. A <xref:System.Windows.Controls.TreeViewItem> también pueden tener <xref:System.Windows.Controls.TreeViewItem> controles como sus elementos secundarios y pueden definir estos elementos secundarios mediante la <xref:System.Windows.Controls.ItemsControl.Items%2A> propiedad.  
  
 En el ejemplo siguiente se muestra cómo definir explícitamente <xref:System.Windows.Controls.TreeViewItem> contenido estableciendo la <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad en una cadena de texto.  
  
 [!code-xaml[TreeViewSimple#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 En el ejemplo siguiente se muestra cómo definir los elementos secundarios de un <xref:System.Windows.Controls.TreeViewItem> definiendo <xref:System.Windows.Controls.ItemsControl.Items%2A> que están <xref:System.Windows.Controls.Button> controles.  
  
 [!code-xaml[TreeViewSimple#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde un <xref:System.Windows.Data.XmlDataProvider> proporciona <xref:System.Windows.Controls.TreeViewItem> contenido y un <xref:System.Windows.HierarchicalDataTemplate> define la apariencia del contenido.  
  
 [!code-xaml[TreeViewSimple#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 En el ejemplo siguiente se muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde el <xref:System.Windows.Controls.TreeViewItem> contiene contenido <xref:System.Windows.Controls.DockPanel> controles con contenido incrustado.  
  
 [!code-xaml[TreeViewSimple#9](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Introducción a TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [Temas de procedimientos](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
