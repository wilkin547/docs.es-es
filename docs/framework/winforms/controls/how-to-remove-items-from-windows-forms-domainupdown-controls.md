---
title: Procedimiento para quitar elementos de los controles DomainUpDown de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 0c07365f5be2e419b4049a466949fed2d884d897
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59131409"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="fb049-102">Procedimiento para quitar elementos de los controles DomainUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fb049-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="fb049-103">Se pueden quitar elementos de los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control mediante una llamada a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="fb049-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="fb049-104">El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método quita un elemento específico, mientras que el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método quita un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="fb049-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="fb049-105">Para quitar un elemento</span><span class="sxs-lookup"><span data-stu-id="fb049-105">To remove an item</span></span>  
  
-   <span data-ttu-id="fb049-106">Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para quitar un elemento por su nombre.</span><span class="sxs-lookup"><span data-stu-id="fb049-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="fb049-107">-o bien-</span><span class="sxs-lookup"><span data-stu-id="fb049-107">-or-</span></span>  
  
-   <span data-ttu-id="fb049-108">Use el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método para quitar un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="fb049-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fb049-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb049-109">See also</span></span>

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [<span data-ttu-id="fb049-110">DomainUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="fb049-110">DomainUpDown Control</span></span>](domainupdown-control-windows-forms.md)
- [<span data-ttu-id="fb049-111">Información general sobre el control DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fb049-111">DomainUpDown Control Overview</span></span>](domainupdown-control-overview-windows-forms.md)
