---
title: Filtrar Mejorar el rendimiento de un control TreeView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153444"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Filtrar Mejorar el rendimiento de un control TreeView
Si un <xref:System.Windows.Controls.TreeView> contiene muchos elementos, la cantidad de tiempo que tarda en cargar puede provocar un retraso significativo en la interfaz de usuario. Puede mejorar el tiempo de carga estableciendo la `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta `true`.  La interfaz de usuario también podría ser lento al reaccionar cuando un usuario se desplaza el <xref:System.Windows.Controls.TreeView> con la rueda del mouse o arrastrando la miniatura de una barra de desplazamiento. Puede mejorar el rendimiento de la <xref:System.Windows.Controls.TreeView> cuando el usuario se desplaza estableciendo el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Ejemplo  
  
## <a name="description"></a>Descripción  
En el ejemplo siguiente se crea un <xref:System.Windows.Controls.TreeView> que establece el `VirtualizingStackPanel.IsVirtualizing` propiedad adjunta en true y el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para optimizar su rendimiento.  
  
## <a name="code"></a>Código  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 El ejemplo siguiente muestra los datos que usa el ejemplo anterior.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Vea también

- [Controles](../advanced/optimizing-performance-controls.md)
