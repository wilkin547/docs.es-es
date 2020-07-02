---
title: Agregar y quitar elementos con el control ListView
description: Obtenga información sobre cómo agregar y quitar un elemento con el control Windows Forms ListView especificando el elemento y asignándoles propiedades.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], populating
- list views [Windows Forms], adding list items
- ListView control [Windows Forms], adding list items
ms.assetid: 1b35a80a-edd8-495f-a807-a28c4aae52c6
ms.openlocfilehash: db374ded69bcbd93527381d75a8ff751a1c9abe6
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85618095"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control"></a><span data-ttu-id="510da-103">Procedimiento para agregar y quitar elementos con el control ListView de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="510da-103">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>
<span data-ttu-id="510da-104">El proceso de agregar un elemento a un control de Windows Forms <xref:System.Windows.Forms.ListView> consiste principalmente en especificar el elemento y asignarle propiedades.</span><span class="sxs-lookup"><span data-stu-id="510da-104">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="510da-105">La adición o eliminación de elementos de lista se puede realizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="510da-105">Adding or removing list items can be done at any time.</span></span>  
  
### <a name="to-add-items-programmatically"></a><span data-ttu-id="510da-106">Para agregar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="510da-106">To add items programmatically</span></span>  
  
1. <span data-ttu-id="510da-107">Use el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> método de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="510da-107">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Add%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#11)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#11)]  
  
### <a name="to-remove-items-programmatically"></a><span data-ttu-id="510da-108">Para quitar elementos mediante programación</span><span class="sxs-lookup"><span data-stu-id="510da-108">To remove items programmatically</span></span>  
  
1. <span data-ttu-id="510da-109">Use el <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método o de la <xref:System.Windows.Forms.ListView.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="510da-109">Use the <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> or <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method of the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span> <span data-ttu-id="510da-110">El <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> método quita un solo elemento; el <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> método quita todos los elementos de la lista.</span><span class="sxs-lookup"><span data-stu-id="510da-110">The <xref:System.Windows.Forms.ListView.ListViewItemCollection.RemoveAt%2A> method removes a single item; the <xref:System.Windows.Forms.ListView.ListViewItemCollection.Clear%2A> method removes all items from the list.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#12)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#12)]  
  
## <a name="see-also"></a><span data-ttu-id="510da-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="510da-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="510da-112">Control ListView</span><span class="sxs-lookup"><span data-stu-id="510da-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="510da-113">Información general sobre el control ListView</span><span class="sxs-lookup"><span data-stu-id="510da-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
