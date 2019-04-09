---
title: Filtrar para agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 32f58dc8b8b96a3d8660550d8ce7696839587ddc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080675"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Filtrar para agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
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
  
     -o bien-  
  
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
- [Control DomainUpDown](domainupdown-control-windows-forms.md)
- [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)
