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
ms.openlocfilehash: 209f2c5645758aba4d1e10fc36fe773faa975e6b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Cómo: Mejorar el rendimiento de un control TreeView
Si un <xref:System.Windows.Controls.TreeView> contiene muchos elementos, la cantidad de tiempo que se tarda en cargar puede provocar un retraso importante en la interfaz de usuario. Puede mejorar el tiempo de carga estableciendo la `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta `true`.  La interfaz de usuario también puede ser lenta para reaccionar cuando un usuario se desplaza por la <xref:System.Windows.Controls.TreeView> con la rueda del mouse o arrastrando el cuadro de desplazamiento de una barra de desplazamiento. Puede mejorar el rendimiento de la <xref:System.Windows.Controls.TreeView> cuando el usuario se desplaza estableciendo la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="description"></a>Descripción  
En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView> que establece el `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta en true y la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para optimizar su rendimiento.  
  
## <a name="code"></a>Código  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 En el ejemplo siguiente se muestra los datos que utiliza el ejemplo anterior.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Vea también  
 [Controles](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
