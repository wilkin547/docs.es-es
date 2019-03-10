---
title: Filtrar Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 06c2c83ddfba67aaff775065cc2aa4515978bf81
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722716"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Filtrar Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
Puede agregar elementos a los formularios de Windows <xref:System.Windows.Forms.DomainUpDown> control en el código. Llame a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para agregar elementos al control <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad. El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método agrega un elemento al final de una colección, mientras que el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método agrega un elemento en una posición especificada.  
  
### <a name="to-add-a-new-item"></a>Para agregar un nuevo elemento  
  
1.  Use el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método para agregar un elemento al final de la lista de elementos.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     O bien  
  
2.  Use el <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método para insertar un elemento en la lista en una posición especificada.  
  
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
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.DomainUpDown>
- <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>
- <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>
- [DomainUpDown (control)](domainupdown-control-windows-forms.md)
- [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)
