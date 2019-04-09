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
ms.openlocfilehash: d9f7a8f04f53b7d38a49dfef2c947dfa1c2d263d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169713"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="9502e-102">Filtrar Usar SelectedValue, SelectedValuePath y SelectedItem</span><span class="sxs-lookup"><span data-stu-id="9502e-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="9502e-103">En este ejemplo se muestra cómo usar el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> y <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades para especificar un valor para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="9502e-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9502e-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9502e-104">Example</span></span>  
 <span data-ttu-id="9502e-105">El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="9502e-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="9502e-106">El <xref:System.Windows.Controls.TreeView.SelectedItem%2A> representa un objeto en el <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y el <xref:System.Windows.Controls.TreeView> muestra el valor de una propiedad única del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="9502e-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="9502e-107">El <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se usa para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="9502e-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="9502e-108">Los ejemplos de este tema ilustran este concepto.</span><span class="sxs-lookup"><span data-stu-id="9502e-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="9502e-109">El ejemplo siguiente se muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información del empleado.</span><span class="sxs-lookup"><span data-stu-id="9502e-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="9502e-110">En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra la `EmployeeName` y `EmployeeWorkDay` de la `Employee`.</span><span class="sxs-lookup"><span data-stu-id="9502e-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="9502e-111">Tenga en cuenta que el <xref:System.Windows.HierarchicalDataTemplate> no especifica la `EmployeeNumber` como parte de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9502e-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="9502e-112">El ejemplo siguiente se muestra un <xref:System.Windows.Controls.TreeView> que usa el definido anteriormente <xref:System.Windows.HierarchicalDataTemplate> y que establece el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad a la `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="9502e-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="9502e-113">Cuando se selecciona un `EmployeeName` en el <xref:System.Windows.Controls.TreeView>, el <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el `EmployeeInfo` elemento de datos que se corresponde con el texto seleccionado `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="9502e-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="9502e-114">Sin embargo, dado que el <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de este <xref:System.Windows.Controls.TreeView> está establecido en `EmployeeNumber`, el <xref:System.Windows.Controls.TreeView.SelectedValue%2A> está establecido en el `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="9502e-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="9502e-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9502e-115">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="9502e-116">Introducción a TreeView</span><span class="sxs-lookup"><span data-stu-id="9502e-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="9502e-117">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="9502e-117">How-to Topics</span></span>](treeview-how-to-topics.md)
