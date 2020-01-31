---
title: Seleccionar un elemento en el control ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743230"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="16654-102">Cómo: Seleccionar un elemento del control ListView de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="16654-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="16654-103">En este ejemplo se muestra cómo seleccionar un elemento de un control de Windows Forms <xref:System.Windows.Forms.ListView> mediante programación.</span><span class="sxs-lookup"><span data-stu-id="16654-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="16654-104">Al seleccionar un elemento mediante programación, no se cambia automáticamente el foco al control <xref:System.Windows.Forms.ListView>.</span><span class="sxs-lookup"><span data-stu-id="16654-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="16654-105">Por esta razón, normalmente también querrá establecer el elemento como enfocado al seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="16654-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16654-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16654-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="16654-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="16654-107">Compiling the Code</span></span>  
 <span data-ttu-id="16654-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="16654-108">This example requires:</span></span>  
  
- <span data-ttu-id="16654-109">Un control de <xref:System.Windows.Forms.ListView> denominado `listView1` que contiene al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="16654-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="16654-110">Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="16654-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16654-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="16654-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
