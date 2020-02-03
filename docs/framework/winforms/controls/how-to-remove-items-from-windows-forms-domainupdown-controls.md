---
title: Quitar elementos de los controles DomainUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: e52af5c5add4fda93e2b51c8afdb90c92e8d2f62
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735768"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="664ce-102">Cómo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="664ce-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="664ce-103">Puede quitar elementos del control de <xref:System.Windows.Forms.DomainUpDown> de Windows Forms llamando al método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>.</span><span class="sxs-lookup"><span data-stu-id="664ce-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="664ce-104">El método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> quita un elemento específico, mientras que el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> quita un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="664ce-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="664ce-105">Para quitar un elemento</span><span class="sxs-lookup"><span data-stu-id="664ce-105">To remove an item</span></span>  
  
- <span data-ttu-id="664ce-106">Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> para quitar un elemento por nombre.</span><span class="sxs-lookup"><span data-stu-id="664ce-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="664ce-107">O bien</span><span class="sxs-lookup"><span data-stu-id="664ce-107">-or-</span></span>  
  
- <span data-ttu-id="664ce-108">Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> para quitar un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="664ce-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
    ```vb  
    ' Removes the first item in the list.  
    DomainUpDown1.Items.RemoveAt(0)  
    ```  
  
    ```csharp  
    // Removes the first item in the list.  
    domainUpDown1.Items.RemoveAt(0);  
    ```  
  
    ```cpp  
    // Removes the first item in the list.  
    domainUpDown1->Items->RemoveAt(0);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="664ce-109">Consulte también</span><span class="sxs-lookup"><span data-stu-id="664ce-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="664ce-110">DomainUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="664ce-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="664ce-111">Información general sobre el control DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="664ce-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
