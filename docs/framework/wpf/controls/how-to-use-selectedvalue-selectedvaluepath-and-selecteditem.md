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
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="e6701-103">Cómo: Usar SelectedValue, SelectedValuePath y SelectedItem</span><span class="sxs-lookup"><span data-stu-id="e6701-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="e6701-104">En este ejemplo se muestra cómo usar <xref:System.Windows.Controls.TreeView.SelectedValue%2A> las <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedades y para especificar un valor para la propiedad <xref:System.Windows.Controls.TreeView.SelectedItem%2A> de un <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="e6701-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e6701-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e6701-105">Example</span></span>  
 <span data-ttu-id="e6701-106">La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad proporciona una manera de especificar <xref:System.Windows.Controls.TreeView.SelectedValue%2A> para <xref:System.Windows.Controls.TreeView.SelectedItem%2A> en un <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="e6701-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="e6701-107"><xref:System.Windows.Controls.TreeView.SelectedItem%2A>Representa un objeto de la <xref:System.Windows.Controls.ItemsControl.Items%2A> colección y <xref:System.Windows.Controls.TreeView> muestra el valor de una única propiedad del elemento seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e6701-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="e6701-108">La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> propiedad especifica la ruta de acceso a la propiedad que se utiliza para determinar el valor de la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e6701-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="e6701-109">En los ejemplos de este tema se muestra este concepto.</span><span class="sxs-lookup"><span data-stu-id="e6701-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="e6701-110">En el ejemplo siguiente se muestra un <xref:System.Windows.Data.XmlDataProvider> que contiene información de empleado.</span><span class="sxs-lookup"><span data-stu-id="e6701-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="e6701-111">En el ejemplo siguiente se define un <xref:System.Windows.HierarchicalDataTemplate> que muestra `EmployeeName` y `EmployeeWorkDay` de `Employee` .</span><span class="sxs-lookup"><span data-stu-id="e6701-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="e6701-112">Tenga en cuenta que no <xref:System.Windows.HierarchicalDataTemplate> especifica `EmployeeNumber` como parte de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="e6701-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="e6701-113">En el ejemplo siguiente se muestra un <xref:System.Windows.Controls.TreeView> que usa el definido previamente <xref:System.Windows.HierarchicalDataTemplate> y que establece la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> propiedad en `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="e6701-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="e6701-114">Al seleccionar un `EmployeeName` en el <xref:System.Windows.Controls.TreeView> , la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad devuelve el elemento de `EmployeeInfo` datos correspondiente a la seleccionada `EmployeeName` .</span><span class="sxs-lookup"><span data-stu-id="e6701-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="e6701-115">Sin embargo, dado que la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> de <xref:System.Windows.Controls.TreeView> se establece en `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> se establece en `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="e6701-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="e6701-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6701-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="e6701-117">Introducción a TreeView</span><span class="sxs-lookup"><span data-stu-id="e6701-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="e6701-118">Temas "Cómo..."</span><span class="sxs-lookup"><span data-stu-id="e6701-118">How-to Topics</span></span>](treeview-how-to-topics.md)
