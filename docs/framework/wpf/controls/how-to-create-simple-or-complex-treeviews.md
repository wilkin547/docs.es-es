---
title: Filtrar Crear controles TreeView simples o complejos
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], creating
- Control class [WPF], TreeView [WPF], creating
ms.assetid: 1defbb78-b8e7-4c0e-b650-576453ac828d
ms.openlocfilehash: 7edb4933ebcc0f0d2cb02754238c2342ee9dd4a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205152"
---
# <a name="how-to-create-simple-or-complex-treeviews"></a>Filtrar Crear controles TreeView simples o complejos
En este ejemplo se muestra cómo crear simples o complejas <xref:System.Windows.Controls.TreeView> controles.  
  
 Un <xref:System.Windows.Controls.TreeView> consta de una jerarquía de <xref:System.Windows.Controls.TreeViewItem> controles, que pueden contener cadenas de texto simple y el contenido también más complejo, tales como <xref:System.Windows.Controls.Button> controles o <xref:System.Windows.Controls.StackPanel> con contenido incrustado. Puede definir explícitamente el <xref:System.Windows.Controls.TreeView> contenido o un origen de datos puede proporcionar el contenido. En este tema se proporciona ejemplos de estos conceptos.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad de la <xref:System.Windows.Controls.TreeViewItem> incluye el contenido que el <xref:System.Windows.Controls.TreeView> muestra para ese elemento. Un <xref:System.Windows.Controls.TreeViewItem> también pueden tener <xref:System.Windows.Controls.TreeViewItem> controles como sus elementos secundarios y pueden definir estos elementos secundarios mediante la <xref:System.Windows.Controls.ItemsControl.Items%2A> propiedad.  
  
 El ejemplo siguiente muestra cómo se definen explícitamente <xref:System.Windows.Controls.TreeViewItem> contenido estableciendo el <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> propiedad en una cadena de texto.  
  
 [!code-xaml[TreeViewSimple#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#1)]  
  
 El ejemplo siguiente se muestra cómo definir los elementos secundarios de un <xref:System.Windows.Controls.TreeViewItem> definiendo <xref:System.Windows.Controls.ItemsControl.Items%2A> que son <xref:System.Windows.Controls.Button> controles.  
  
 [!code-xaml[TreeViewSimple#3](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#3)]  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde un <xref:System.Windows.Data.XmlDataProvider> proporciona <xref:System.Windows.Controls.TreeViewItem> contenido y un <xref:System.Windows.HierarchicalDataTemplate> define la apariencia del contenido.  
  
 [!code-xaml[TreeViewSimple#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#6)]  
  
 [!code-xaml[TreeViewSimple#7](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#7)]  
  
 [!code-xaml[TreeViewSimple#5](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#5)]  
  
 El ejemplo siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> donde el <xref:System.Windows.Controls.TreeViewItem> contiene contenido <xref:System.Windows.Controls.DockPanel> controles con contenido incrustado.  
  
 [!code-xaml[TreeViewSimple#9](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#9)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Introducción a TreeView](treeview-overview.md)
- [Temas "Cómo..."](treeview-how-to-topics.md)
