---
title: Procedimiento Quitar elementos de controles DomainUpDown de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- DomainUpDown control [Windows Forms], removing items from
- spin button control [Windows Forms], removing items
ms.assetid: e70f5cbc-b497-41a9-975a-344c00e56ed2
ms.openlocfilehash: 58c93f478414d24c2fdda0f9662936a8b520e381
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57708969"
---
# <a name="how-to-remove-items-from-windows-forms-domainupdown-controls"></a>Filtrar Quitar elementos de controles DomainUpDown de formularios Windows Forms
Se pueden quitar elementos de los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control mediante una llamada a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase. El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método quita un elemento específico, mientras que el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método quita un elemento por su posición.  
  
### <a name="to-remove-an-item"></a>Para quitar un elemento  
  
-   Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Remove%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para quitar un elemento por su nombre.  
  
    ```vb  
    DomainUpDown1.Items.Remove("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Remove("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Remove("noodles");  
    ```  
  
     O bien  
  
-   Use el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.RemoveAt%2A> método para quitar un elemento por su posición.  
  
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
- [DomainUpDown (control)](domainupdown-control-windows-forms.md)
- [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)
