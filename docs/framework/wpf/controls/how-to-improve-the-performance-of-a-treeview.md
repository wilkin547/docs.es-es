---
title: "Cómo: Mejorar el rendimiento de un control TreeView"
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
helpviewer_keywords: TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2c13a9c89bdcb149df61f26177ea8705e502402f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="328b0-102">Cómo: Mejorar el rendimiento de un control TreeView</span><span class="sxs-lookup"><span data-stu-id="328b0-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="328b0-103">Si un <xref:System.Windows.Controls.TreeView> contiene muchos elementos, la cantidad de tiempo que se tarda en cargar puede provocar un retraso importante en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="328b0-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="328b0-104">Puede mejorar el tiempo de carga estableciendo la `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta `true`.</span><span class="sxs-lookup"><span data-stu-id="328b0-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="328b0-105">La interfaz de usuario también puede ser lenta para reaccionar cuando un usuario se desplaza por la <xref:System.Windows.Controls.TreeView> con la rueda del mouse o arrastrando el cuadro de desplazamiento de una barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="328b0-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="328b0-106">Puede mejorar el rendimiento de la <xref:System.Windows.Controls.TreeView> cuando el usuario se desplaza estableciendo la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="328b0-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="328b0-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="328b0-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="328b0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="328b0-108">Description</span></span>  
<span data-ttu-id="328b0-109">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView> que establece el `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta en true y la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para optimizar su rendimiento.</span><span class="sxs-lookup"><span data-stu-id="328b0-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="328b0-110">Código</span><span class="sxs-lookup"><span data-stu-id="328b0-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="328b0-111">En el ejemplo siguiente se muestra los datos que utiliza el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="328b0-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="328b0-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="328b0-112">See Also</span></span>  
 [<span data-ttu-id="328b0-113">Controles</span><span class="sxs-lookup"><span data-stu-id="328b0-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
