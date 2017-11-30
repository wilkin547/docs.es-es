---
title: "Cómo: Obtener un elemento ListBoxItem"
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
- ListBox controls [WPF], getting a ListBoxItem
- ListBoxItem [WPF]
ms.assetid: da877c6f-5fd8-40cb-8909-225cbfd99aa5
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e50eed4d205335cf452292e11a27db9e847f28ab
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-get-a-listboxitem"></a><span data-ttu-id="76e37-102">Cómo: Obtener un elemento ListBoxItem</span><span class="sxs-lookup"><span data-stu-id="76e37-102">How to: Get a ListBoxItem</span></span>
<span data-ttu-id="76e37-103">Si necesita obtener un determinado <xref:System.Windows.Controls.ListBoxItem> en un índice determinado en una <xref:System.Windows.Controls.ListBox>, puede usar un <xref:System.Windows.Controls.ItemContainerGenerator>.</span><span class="sxs-lookup"><span data-stu-id="76e37-103">If you need to get a specific <xref:System.Windows.Controls.ListBoxItem> at a particular index in a <xref:System.Windows.Controls.ListBox>, you can use an <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76e37-104">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="76e37-104">Example</span></span>  
 <span data-ttu-id="76e37-105">El ejemplo siguiente muestra un <xref:System.Windows.Controls.ListBox> y sus elementos.</span><span class="sxs-lookup"><span data-stu-id="76e37-105">The following example shows a <xref:System.Windows.Controls.ListBox> and its items.</span></span>  
  
 [!code-xaml[ListBoxItems#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="76e37-106">En el ejemplo siguiente se muestra cómo recuperar el elemento especificando el índice del elemento en el <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> propiedad de la <xref:System.Windows.Controls.ItemContainerGenerator>.</span><span class="sxs-lookup"><span data-stu-id="76e37-106">The following example shows how to retrieve the item by specifying the index of the item in the <xref:System.Windows.Controls.ItemContainerGenerator.ContainerFromIndex%2A> property of the <xref:System.Windows.Controls.ItemContainerGenerator>.</span></span>  
  
 [!code-csharp[ListBoxItems#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#2)]
 [!code-vb[ListBoxItems#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#2)]  
  
 <span data-ttu-id="76e37-107">Después de recuperar el elemento del cuadro de lista, puede mostrar el contenido del elemento, tal como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="76e37-107">After you have retrieved the list box item, you can display the contents of the item, as shown in the following example.</span></span>  
  
 [!code-csharp[ListBoxItems#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListBoxItems/CSharp/Window1.xaml.cs#3)]
 [!code-vb[ListBoxItems#3](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/ListBoxItems/VisualBasic/Window1.xaml.vb#3)]
