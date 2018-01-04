---
title: "Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación"
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
- spin button control [Windows Forms], adding items
- DomainUpDown control [Windows Forms], adding items to
ms.assetid: fd31d314-33eb-4181-90f8-d32ed0c4e072
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e540e394226f20c40915f4d9de31afcffdf6e35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-items-to-windows-forms-domainupdown-controls-programmatically"></a>Cómo: Agregar elementos a controles DomainUpDown de formularios Windows Forms mediante programación
Puede agregar elementos a los formularios Windows Forms <xref:System.Windows.Forms.DomainUpDown> control en el código. Llame a la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> o <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método de la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection> clase para agregar elementos al control <xref:System.Windows.Forms.DomainUpDown.Items%2A> propiedad. El <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método agrega un elemento al final de una colección, mientras que la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método agrega un elemento en una posición especificada.  
  
### <a name="to-add-a-new-item"></a>Para agregar un nuevo elemento  
  
1.  Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A> método para agregar un elemento al final de la lista de elementos.  
  
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
  
2.  Use la <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Insert%2A> método para insertar un elemento en la lista en una posición especificada.  
  
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
 <xref:System.Windows.Forms.DomainUpDown>  
 <xref:System.Windows.Forms.DomainUpDown.DomainUpDownItemCollection.Add%2A?displayProperty=nameWithType>  
 <xref:System.Collections.ArrayList.Insert%2A?displayProperty=nameWithType>  
 [DomainUpDown (control)](../../../../docs/framework/winforms/controls/domainupdown-control-windows-forms.md)  
 [Información general sobre el control DomainUpDown](../../../../docs/framework/winforms/controls/domainupdown-control-overview-windows-forms.md)
