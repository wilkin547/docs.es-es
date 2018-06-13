---
title: 'Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 7359310b092e84b250c09153ef86d44c70d413fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33526183"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a><span data-ttu-id="fe074-102">Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación</span><span class="sxs-lookup"><span data-stu-id="fe074-102">How to: Add Items to Windows Forms DomainUpDown Controls Programmatically</span></span>
<span data-ttu-id="fe074-103">Puede agregar elementos a los formularios Windows Forms <xref:System.Windows.Forms.DomainUpDown> control en el código.</span><span class="sxs-lookup"><span data-stu-id="fe074-103">You can add items to the Windows Forms <xref:System.Windows.Forms.DomainUpDown> control in code.</span></span> <span data-ttu-id="fe074-104">Llame a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para agregar elementos al control <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fe074-104">Call the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> or <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method of the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> class to add items to the control's <xref:System.Windows.Forms.DomainUpDown.Items%2A> property.</span></span> <span data-ttu-id="fe074-105">El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método agrega un elemento al final de una colección, mientras que la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método agrega un elemento en una posición especificada.</span><span class="sxs-lookup"><span data-stu-id="fe074-105">The <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method adds an item to the end of a collection, while the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method adds an item at a specified position.</span></span>  
  
### <a name="to-add-a-new-item"></a><span data-ttu-id="fe074-106">Para agregar un nuevo elemento</span><span class="sxs-lookup"><span data-stu-id="fe074-106">To add a new item</span></span>  
  
1.  <span data-ttu-id="fe074-107">Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método para agregar un elemento al final de la lista de elementos.</span><span class="sxs-lookup"><span data-stu-id="fe074-107">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> method to add an item to the end of the list of items.</span></span>  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     <span data-ttu-id="fe074-108">-o bien-</span><span class="sxs-lookup"><span data-stu-id="fe074-108">-or-</span></span>  
  
2.  <span data-ttu-id="fe074-109">Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método para insertar un elemento en la lista en una posición especificada.</span><span class="sxs-lookup"><span data-stu-id="fe074-109">Use the <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> method to insert an item into the list at a specified position.</span></span>  
  
    ```vb  
    ' Inserts an item at the third position in the list  
    DomainUpDown1.Items.Insert(2, "rice")  
    ```  
  
    ```csharp  
    // Inserts an item at the third position in the list  
    domainUpDown1.Items.Insert(2, "rice");  
    ```  
  
    ```cpp  
    // Inserts an item at the third position in the list  
    domainUpDown1->Items->Insert(2, "rice");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fe074-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe074-110">See Also</span></span>  
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>  
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="fe074-111">DomainUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="fe074-111">DomainUpDown Control</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [<span data-ttu-id="fe074-112">Información general sobre el control DomainUpDown</span><span class="sxs-lookup"><span data-stu-id="fe074-112">DomainUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
