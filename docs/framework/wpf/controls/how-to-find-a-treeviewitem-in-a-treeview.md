---
title: "Cómo: Buscar un TreeViewItem en un TreeView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 696a9e2d92b9c44e4aedbcc200b41e5548cd7411
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="688e2-102">Cómo: Buscar un TreeViewItem en un TreeView</span><span class="sxs-lookup"><span data-stu-id="688e2-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="688e2-103">El <xref:System.Windows.Controls.TreeView> control proporciona una manera cómoda para mostrar datos jerárquicos.</span><span class="sxs-lookup"><span data-stu-id="688e2-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="688e2-104">Si su <xref:System.Windows.Controls.TreeView> está enlazado a un origen de datos, la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> propiedad proporciona una manera cómoda para que pueda recuperar rápidamente el objeto de datos seleccionado.</span><span class="sxs-lookup"><span data-stu-id="688e2-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="688e2-105">Normalmente es mejor trabajar con el objeto de datos subyacente, pero en ocasiones puede que necesite manipular mediante programación los datos que contiene <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="688e2-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="688e2-106">Por ejemplo, deberá expandir mediante programación el <xref:System.Windows.Controls.TreeViewItem>, o seleccione otro elemento en el <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="688e2-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="688e2-107">Para buscar un <xref:System.Windows.Controls.TreeViewItem> que contiene un objeto de datos específicos, debe recorrer cada nivel de la <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="688e2-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="688e2-108">Los elementos de un <xref:System.Windows.Controls.TreeView> también se pueden virtualizar para mejorar el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="688e2-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="688e2-109">En el caso donde se pueden virtualizar elementos, también debe tener en cuenta un <xref:System.Windows.Controls.TreeViewItem> para comprobar si contiene el objeto de datos.</span><span class="sxs-lookup"><span data-stu-id="688e2-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="688e2-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="688e2-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="688e2-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="688e2-111">Description</span></span>  
 <span data-ttu-id="688e2-112">El siguiente ejemplo se buscan un <xref:System.Windows.Controls.TreeView> para un objeto específico y devuelve el objeto contenedor del <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="688e2-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="688e2-113">El ejemplo se asegura que cada <xref:System.Windows.Controls.TreeViewItem> se crea una instancia para que sus elementos secundarios se pueden buscar.</span><span class="sxs-lookup"><span data-stu-id="688e2-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="688e2-114">En este ejemplo también funciona si el <xref:System.Windows.Controls.TreeView> no utiliza elementos virtualizados.</span><span class="sxs-lookup"><span data-stu-id="688e2-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="688e2-115">El ejemplo siguiente funciona para cualquier <xref:System.Windows.Controls.TreeView>, independientemente del modelo de datos subyacente y búsquedas cada <xref:System.Windows.Controls.TreeViewItem> hasta que se encuentra el objeto.</span><span class="sxs-lookup"><span data-stu-id="688e2-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="688e2-116">Otra técnica que tiene un mejor rendimiento consiste en Buscar en el modelo de datos para el objeto especificado, realizar un seguimiento de su ubicación dentro de la jerarquía de datos y, a continuación, busque el correspondiente <xref:System.Windows.Controls.TreeViewItem> en el <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="688e2-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="688e2-117">Sin embargo, la técnica que tiene un mejor rendimiento requiere un conocimiento del modelo de datos y no se puede generalizar para cualquier <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="688e2-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="688e2-118">Código</span><span class="sxs-lookup"><span data-stu-id="688e2-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="688e2-119">El código anterior se basa en un personalizado <xref:System.Windows.Controls.VirtualizingStackPanel> que expone un método denominado `BringIntoView`.</span><span class="sxs-lookup"><span data-stu-id="688e2-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="688e2-120">El código siguiente define la opción de instalación <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="688e2-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="688e2-121">El código XAML siguiente muestra cómo crear un <xref:System.Windows.Controls.TreeView> que usa la opción de instalación <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="688e2-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="688e2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="688e2-122">See Also</span></span>  
 [<span data-ttu-id="688e2-123">Mejorar el rendimiento de un control TreeView</span><span class="sxs-lookup"><span data-stu-id="688e2-123">Improve the Performance of a TreeView</span></span>](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
