---
title: Filtrar Obtener un elemento ListBoxItem
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
ms.openlocfilehash: 27a435feb4a941c77af221ab25bd63ea98b16e92
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360503"
---
# <a name="how-to-get-a-listboxitem"></a><span data-ttu-id="3d611-102">Procedimiento Obtener un elemento ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="3d611-102">How to: Get a ListBoxItem</span></span>
<span data-ttu-id="3d611-103">Si necesita obtener un determinado <xref:System.Windows.Controls.ListBoxItem> en un índice determinado en un <xref:System.Windows.Controls.ListBox>, puede usar un <xref:System.Windows.Controls.ItemContainerGenerator>.</span><span class="sxs-lookup"><span data-stu-id="3d611-103">If you need to get a specific <xref:System.Windows.Controls.ListBoxItem> at a particular index in a <xref:System.Windows.Controls.ListBox>, you can use an <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d611-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="3d611-104">Example</span></span>  
 <span data-ttu-id="3d611-105">El ejemplo siguiente se muestra un <xref:System.Windows.Controls.ListBox> y sus elementos.</span><span class="sxs-lookup"><span data-stu-id="3d611-105">The following example shows a <xref:System.Windows.Controls.ListBox> and its items.</span></span>  
  
 [!code-xaml[ListBoxItems#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="3d611-106">El ejemplo siguiente muestra cómo recuperar el elemento especificando el índice del elemento en el <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> propiedad de la <xref:System.Windows.Controls.ItemContainerGenerator>.</span><span class="sxs-lookup"><span data-stu-id="3d611-106">The following example shows how to retrieve the item by specifying the index of the item in the <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> property of the <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
 [!code-csharp[ListBoxItems#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="3d611-107">Después de recuperar el elemento de cuadro de lista, puede mostrar el contenido del elemento, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3d611-107">After you have retrieved the list box item, you can display the contents of the item, as shown in the following example.</span></span>  
  
 [!code-csharp[ListBoxItems#3](~/samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
