---
title: Filtrar Mejorar el rendimiento del desplazamiento de un control ListBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox control [WPF], reusing item containers
- ListBox control [WPF], improving scrolling performance
ms.assetid: 1e2bf8f3-c8ce-47f7-a400-a7fe11d1a848
ms.openlocfilehash: a9d1ca1d8ac2ef830984408f3052eb0ed0987c5d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364559"
---
# <a name="how-to-improve-the-scrolling-performance-of-a-listbox"></a><span data-ttu-id="c7d70-102">Filtrar Mejorar el rendimiento del desplazamiento de un control ListBox</span><span class="sxs-lookup"><span data-stu-id="c7d70-102">How to: Improve the Scrolling Performance of a ListBox</span></span>
<span data-ttu-id="c7d70-103">Si un <xref:System.Windows.Controls.ListBox> contiene muchos elementos, la respuesta de la interfaz de usuario puede ser lenta cuando un usuario se desplaza el <xref:System.Windows.Controls.ListBox> con la rueda del mouse o arrastrando la miniatura de una barra de desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="c7d70-103">If a <xref:System.Windows.Controls.ListBox> contains many items, the user interface response can be slow when a user scrolls the <xref:System.Windows.Controls.ListBox> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="c7d70-104">Puede mejorar el rendimiento de la <xref:System.Windows.Controls.ListBox> cuando el usuario se desplaza estableciendo el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="c7d70-104">You can improve the performance of the <xref:System.Windows.Controls.ListBox> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c7d70-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c7d70-105">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="c7d70-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c7d70-106">Description</span></span>  
<span data-ttu-id="c7d70-107">En el ejemplo siguiente se crea un <xref:System.Windows.Controls.ListBox> y establece el `VirtualizingStackPanel.VirtualizationMode` propiedad adjunta <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> para mejorar el rendimiento durante el desplazamiento.</span><span class="sxs-lookup"><span data-stu-id="c7d70-107">The following example creates a <xref:System.Windows.Controls.ListBox> and sets the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to improve performance during scrolling.</span></span>  
  
## <a name="code"></a><span data-ttu-id="c7d70-108">Código</span><span class="sxs-lookup"><span data-stu-id="c7d70-108">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizationMode](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizationmode)]  
  
 <span data-ttu-id="c7d70-109">El ejemplo siguiente muestra los datos que usa el ejemplo anterior.</span><span class="sxs-lookup"><span data-stu-id="c7d70-109">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#listboxdata)]
 [!code-vb[RecycleItemContainerShippets#ListBoxData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#listboxdata)]
