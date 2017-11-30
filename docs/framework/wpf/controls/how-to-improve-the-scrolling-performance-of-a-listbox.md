---
title: "Cómo: Mejorar el rendimiento del desplazamiento de un control ListBox"
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
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46a54c9ed1dff9796506df78d07d7506dfd29cbf
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="1cdad-102">Cómo: Mejorar el rendimiento del desplazamiento de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="1cdad-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="1cdad-103">Si un <xref:System.Windows.Controls.ListBox> contiene muchos elementos, la respuesta de la interfaz de usuario puede ser lenta si un usuario se desplaza por la <xref:System.Windows.Controls.ListBox> con la rueda del mouse o arrastrando el cuadro de desplazamiento de una barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="1cdad-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="1cdad-104">Puede mejorar el rendimiento de la <xref:System.Windows.Controls.ListBox> cuando el usuario se desplaza estableciendo la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1cdad-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1cdad-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1cdad-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="1cdad-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1cdad-106">Description</span></span>  
<span data-ttu-id="1cdad-107">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> y establece la `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para mejorar el rendimiento durante el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="1cdad-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1cdad-108">Código</span><span class="sxs-lookup"><span data-stu-id="1cdad-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="1cdad-109">En el ejemplo siguiente se muestra los datos que utiliza el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="1cdad-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
