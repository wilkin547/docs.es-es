---
title: Filtrar Usar SelectedValue, SelectedValuePath y SelectedItem
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: e3f4e5e6a51426581082ab24a1c3a962e38846bd
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373834"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Filtrar Usar SelectedValue, SelectedValuePath y SelectedItem
En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> y <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades para especificar un valor para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Ejemplo  
 El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView>. El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> representa un objeto en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y el <xref:System.Windows.Controls.TreeView> muestra el valor de una propiedad única del elemento seleccionado. El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se usa para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad. Los ejemplos de este tema ilustran este concepto.  
  
 El ejemplo siguiente se muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información del empleado.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra la `EmployeeName` y `EmployeeWorkDay` de la `Employee`. Tenga en cuenta que el <xref:System.Windows.HierarchicalDataTemplate> no especifica la `EmployeeNumber` como parte de la plantilla.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 El ejemplo siguiente se muestra un <xref:System.Windows.Controls.TreeView> que usa el definido anteriormente <xref:System.Windows.HierarchicalDataTemplate> y que establece el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad a la `EmployeeNumber`. Cuando se selecciona un `EmployeeName` en el <xref:System.Windows.Controls.TreeView>, el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el `EmployeeInfo` elemento de datos que se corresponde con el texto seleccionado `EmployeeName`. Sin embargo, dado que el <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de este <xref:System.Windows.Controls.TreeView> está establecido en `EmployeeNumber`, el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> está establecido en el `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Introducción a TreeView](treeview-overview.md)
- [Temas "Cómo..."](treeview-how-to-topics.md)
