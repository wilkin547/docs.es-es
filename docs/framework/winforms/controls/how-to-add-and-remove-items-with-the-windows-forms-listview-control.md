---
title: Procedimiento Agregar y quitar elementos con el Control ListView de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: cfa6690db464f432c9082278627a03cd43df6834
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57717250"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="d9b01-102">Procedimiento Agregar y quitar elementos con el Control ListView de formularios de Windows</span><span class="sxs-lookup"><span data-stu-id="d9b01-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="d9b01-103">El proceso de agregar un elemento a un formulario Windows Forms <xref:System.Windows.Forms.ListView> control consta principalmente de especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="d9b01-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="d9b01-104">Agregar o quitar elementos de lista puede realizarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="d9b01-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="d9b01-105">Para agregar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="d9b01-105">To add items programmatically</span></span>  
  
1.  <span data-ttu-id="d9b01-106">Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9b01-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="d9b01-107">Para quitar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="d9b01-107">To remove items programmatically</span></span>  
  
1.  <span data-ttu-id="d9b01-108">Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="d9b01-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="d9b01-109">El <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método quita un elemento único; el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método quita todos los elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="d9b01-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="d9b01-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9b01-110">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="d9b01-111">ListView (Control)</span><span class="sxs-lookup"><span data-stu-id="d9b01-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="d9b01-112">Información general del control ListView</span><span class="sxs-lookup"><span data-stu-id="d9b01-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
