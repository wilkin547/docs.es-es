---
title: "Cómo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms"
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
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7cab9bf4445c7322c1b4824f26c0821de8c58657
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a><span data-ttu-id="02d4b-102">Cómo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="02d4b-102">How to: Remove Items from Windows Forms DomainUpDown Controls</span></span>
<span data-ttu-id="02d4b-103">Puede quitar los elementos de los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control mediante una llamada a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase.</span><span class="sxs-lookup"><span data-stu-id="02d4b-103">You can remove items from the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control by calling the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class.</span></span> <span data-ttu-id="02d4b-104">El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método quita un elemento específico, mientras que la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método quita un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="02d4b-104">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method removes a specific item, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method removes an item by its position.</span></span>  
  
### <a name="to-remove-an-item"></a><span data-ttu-id="02d4b-105">Para quitar un elemento</span><span class="sxs-lookup"><span data-stu-id="02d4b-105">To remove an item</span></span>  
  
-   <span data-ttu-id="02d4b-106">Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para quitar un elemento por su nombre.</span><span class="sxs-lookup"><span data-stu-id="02d4b-106">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to remove an item by name.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     <span data-ttu-id="02d4b-107">O bien</span><span class="sxs-lookup"><span data-stu-id="02d4b-107">-or-</span></span>  
  
-   <span data-ttu-id="02d4b-108">Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método para quitar un elemento por su posición.</span><span class="sxs-lookup"><span data-stu-id="02d4b-108">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> method to remove an item by its position.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="02d4b-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="02d4b-109">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="02d4b-110">DomainUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="02d4b-110">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="02d4b-111">Información general sobre el control DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="02d4b-111">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
