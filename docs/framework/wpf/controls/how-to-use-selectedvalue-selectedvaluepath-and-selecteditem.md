---
title: 'Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem'
description: Aprenda a usar las propiedades SelectedValue y SelectedValuePath para especificar un valor para SelectedItem de una Windows Presentation Foundation TreeView.
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
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166273"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem
En este ejemplo se muestra cómo usar <xref:System.Windows.Controls.TreeView.SelectedValue%2A> las <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades y para especificar un valor para la propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>Ejemplo  
 La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView> . <xref:System.Windows.Controls.TreeView.SelectedItem%2A>Representa un objeto de la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y <xref:System.Windows.Controls.TreeView> muestra el valor de una única propiedad del elemento seleccionado. La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se utiliza para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad. En los ejemplos de este tema se muestra este concepto.  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información de empleado.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra `EmployeeName` y `EmployeeWorkDay` de `Employee` . Tenga en cuenta que no <xref:System.Windows.HierarchicalDataTemplate> especifica `EmployeeNumber` como parte de la plantilla.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.TreeView> que usa el definido previamente <xref:System.Windows.HierarchicalDataTemplate> y que establece la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad en `EmployeeNumber` . Al seleccionar un `EmployeeName` en el <xref:System.Windows.Controls.TreeView> , la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el elemento de `EmployeeInfo` datos correspondiente a la seleccionada `EmployeeName` . Sin embargo, dado que la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de <xref:System.Windows.Controls.TreeView> se establece en `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> se establece en `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Introducción a TreeView](treeview-overview.md)
- [Temas "Cómo..."](treeview-how-to-topics.md)
