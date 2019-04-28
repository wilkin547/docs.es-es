---
title: Procedimiento para seleccionar un elemento del control ListView de formularios Windows Forms
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
ms.openlocfilehash: b3cfcc6c2873dfb0eb95cf7950adc6b2bb73e74c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013366"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="ace99-102">Procedimiento para seleccionar un elemento del control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ace99-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="ace99-103">En este ejemplo se muestra cómo seleccionar mediante programación un elemento en un formulario Windows Forms <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="ace99-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="ace99-104">Seleccionar un elemento mediante programación no cambia automáticamente el foco a la <xref:System.Windows.Forms.ListView> control.</span><span class="sxs-lookup"><span data-stu-id="ace99-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="ace99-105">Por este motivo, normalmente, también debe establecer el elemento como centrado al seleccionar un elemento.</span><span class="sxs-lookup"><span data-stu-id="ace99-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ace99-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="ace99-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ace99-107">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="ace99-107">Compiling the Code</span></span>  
 <span data-ttu-id="ace99-108">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="ace99-108">This example requires:</span></span>  
  
- <span data-ttu-id="ace99-109">Un <xref:System.Windows.Forms.ListView> control denominado `listView1` que contiene al menos un elemento.</span><span class="sxs-lookup"><span data-stu-id="ace99-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="ace99-110">Referencias a los espacios de nombres <xref:System?displayProperty=nameWithType> y <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ace99-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ace99-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="ace99-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
