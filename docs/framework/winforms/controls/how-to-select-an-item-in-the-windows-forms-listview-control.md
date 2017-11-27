---
title: "Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: e7acbda541000655ff96b70a2188169b7e8ccd9a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="282af-102">Cómo: Seleccionar un elemento del control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="282af-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="282af-103">Este ejemplo muestra cómo seleccionar mediante programación un elemento en un formulario Windows Forms <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="282af-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="282af-104">Seleccionar un elemento mediante programación no cambia automáticamente el foco a la <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="282af-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="282af-105">Por esta razón, normalmente también deberá establecer el elemento como enfocado al seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="282af-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="282af-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="282af-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="282af-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="282af-107">Compiling the Code</span></span>  
 <span data-ttu-id="282af-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="282af-108">This example requires:</span></span>  
  
-   <span data-ttu-id="282af-109">A <xref:System.Windows.Forms.ListView> control denominado `listView1` que contiene al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="282af-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
-   <span data-ttu-id="282af-110">Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="282af-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282af-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="282af-111">See Also</span></span>  
 <xref:System.Windows.Forms.ListView>  
 <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
