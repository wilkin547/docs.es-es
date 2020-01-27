---
title: para agregar elementos a controles DomainUpDown mediante programación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
ms.openlocfilehash: 2e9f51fa051bf9b62e95f289db97bffd83450036
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745579"
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
Puede agregar elementos al control Windows Forms <xref:System.Windows.Forms.DomainUpDown> en el código. Llame al método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> de la clase <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> para agregar elementos a la propiedad <xref:System.Windows.Forms.DomainUpDown.Items%2A> del control. El método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> agrega un elemento al final de una colección, mientras que el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> agrega un elemento en una posición especificada.  
  
### <a name="to-add-a-new-item"></a>Para agregar un nuevo elemento  
  
1. Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> para agregar un elemento al final de la lista de elementos.  
  
    ```vb  
    DomainUpDown1.Items.Add("noodles")  
    ```  
  
    ```csharp  
    domainUpDown1.Items.Add("noodles");  
    ```  
  
    ```cpp  
    domainUpDown1->Items->Add("noodles");  
    ```  
  
     O bien,  
  
2. Use el método <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> para insertar un elemento en la lista en una posición especificada.  
  
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
- [DomainUpDown (Control)](domainupdown-control-windows-forms.md)
- [Información general sobre el control DomainUpDown](domainupdown-control-overview-windows-forms.md)
