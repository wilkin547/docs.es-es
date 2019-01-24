---
title: Procedimiento Mejorar el rendimiento de un control TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 3c7bd151e1c8a5f318660cc45702b5b9c98534a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54500699"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="4e14a-102">Procedimiento Mejorar el rendimiento de un control TreeView</span><span class="sxs-lookup"><span data-stu-id="4e14a-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="4e14a-103">Si un <xref:System.Windows.Controls.TreeView> contiene muchos elementos, la cantidad de tiempo que tarda en cargar puede provocar un retraso significativo en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4e14a-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="4e14a-104">Puede mejorar el tiempo de carga estableciendo la `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta `true`.</span><span class="sxs-lookup"><span data-stu-id="4e14a-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="4e14a-105">La interfaz de usuario también podría ser lento al reaccionar cuando un usuario se desplaza el <xref:System.Windows.Controls.TreeView> con la rueda del mouse o arrastrando la miniatura de una barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="4e14a-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="4e14a-106">Puede mejorar el rendimiento de la <xref:System.Windows.Controls.TreeView> cuando el usuario se desplaza estableciendo el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e14a-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e14a-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="4e14a-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="4e14a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e14a-108">Description</span></span>  
<span data-ttu-id="4e14a-109">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView> que establece el `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta en true y el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para optimizar su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="4e14a-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="4e14a-110">Código</span><span class="sxs-lookup"><span data-stu-id="4e14a-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="4e14a-111">El ejemplo siguiente muestra los datos que usa el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="4e14a-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="4e14a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e14a-112">See also</span></span>
- [<span data-ttu-id="4e14a-113">Controles</span><span class="sxs-lookup"><span data-stu-id="4e14a-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
