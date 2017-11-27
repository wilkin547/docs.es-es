---
title: "Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: fdc478d62ca97f8f61c26fbbf1ee6c3ea8b4e189
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="8abe4-102">Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem</span><span class="sxs-lookup"><span data-stu-id="8abe4-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="8abe4-103">Este ejemplo muestra cómo utilizar el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> y <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades para especificar un valor para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="8abe4-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8abe4-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="8abe4-104">Example</span></span>  
 <span data-ttu-id="8abe4-105">El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="8abe4-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="8abe4-106">El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> representa un objeto en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y <xref:System.Windows.Controls.TreeView> muestra el valor de una propiedad única del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8abe4-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="8abe4-107">El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se usa para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="8abe4-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="8abe4-108">Los ejemplos de este tema muestran este concepto.</span><span class="sxs-lookup"><span data-stu-id="8abe4-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="8abe4-109">El ejemplo siguiente muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información del empleado.</span><span class="sxs-lookup"><span data-stu-id="8abe4-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="8abe4-110">En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra la `EmployeeName` y `EmployeeWorkDay` de la `Employee`.</span><span class="sxs-lookup"><span data-stu-id="8abe4-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="8abe4-111">Tenga en cuenta que la <xref:System.Windows.HierarchicalDataTemplate> no especifica la `EmployeeNumber` como parte de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="8abe4-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="8abe4-112">El siguiente ejemplo se muestra un <xref:System.Windows.Controls.TreeView> que usa definida previamente <xref:System.Windows.HierarchicalDataTemplate> y que establece la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad a la `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="8abe4-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="8abe4-113">Cuando se selecciona un `EmployeeName` en el <xref:System.Windows.Controls.TreeView>, el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el `EmployeeInfo` elemento de datos que corresponde a la seleccionada `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="8abe4-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="8abe4-114">Sin embargo, dado que la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de este <xref:System.Windows.Controls.TreeView> está establecido en `EmployeeNumber`, el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> está establecido en el `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="8abe4-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="8abe4-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8abe4-115">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="8abe4-116">Introducción a TreeView</span><span class="sxs-lookup"><span data-stu-id="8abe4-116">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [<span data-ttu-id="8abe4-117">Temas de procedimientos</span><span class="sxs-lookup"><span data-stu-id="8abe4-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
