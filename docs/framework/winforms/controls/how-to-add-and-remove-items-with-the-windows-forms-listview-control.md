---
title: Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: ef0275b3cbc79f22b4fa573f41e4cbdbc3d58990
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104655"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="f8a41-102">Filtrar para agregar y quitar elementos con el control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f8a41-102">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="f8a41-103">El proceso de agregar un elemento a un formulario Windows Forms <xref:System.Windows.Forms.ListView> control consta principalmente de especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="f8a41-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="f8a41-104">Agregar o quitar elementos de lista puede realizarse en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="f8a41-104">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="f8a41-105">Para agregar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="f8a41-105">To add items programmatically</span></span>  
  
1.  <span data-ttu-id="f8a41-106">Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8a41-106">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="f8a41-107">Para quitar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="f8a41-107">To remove items programmatically</span></span>  
  
1.  <span data-ttu-id="f8a41-108">Use la <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> o <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f8a41-108">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="f8a41-109">El <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método quita un elemento único; el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método quita todos los elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="f8a41-109">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="f8a41-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8a41-110">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="f8a41-111">Control ListView</span><span class="sxs-lookup"><span data-stu-id="f8a41-111">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="f8a41-112">Información general sobre el control ListView</span><span class="sxs-lookup"><span data-stu-id="f8a41-112">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
