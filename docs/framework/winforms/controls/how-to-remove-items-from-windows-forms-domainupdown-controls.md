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
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Cómo: Quitar elementos de los controles DomainUpDown de formularios Windows Forms
Puede quitar elementos del control de <xref:System.Windows.Forms.DomainUpDown> de Windows Forms llamando al método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection>. El método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> quita un elemento específico, mientras que el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> quita un elemento por su posición.  
  
### <a name="to-remove-an-item"></a>Para quitar un elemento  
  
- Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> para quitar un elemento por nombre.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     O bien,  
  
- Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> para quitar un elemento por su posición.  
  
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
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A?displayProperty=nameWithType>
- [DomainUpDown (Control)](domainupdown-control-windows-forms.md)
- [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)
