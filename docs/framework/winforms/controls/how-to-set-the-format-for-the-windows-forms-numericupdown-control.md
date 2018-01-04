---
title: "Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms"
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
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b4ff6d8e584e65482285012af351ebd1a669b806
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms
Puede configurar cómo se muestran los valores en los formularios Windows Forms <xref:System.Windows.Forms.NumericUpDown> control. El <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0. El <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`. El control puede mostrar valores en formato hexadecimal en lugar de formato decimal, si la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad está establecida en `true`; el valor predeterminado es `false`.  
  
### <a name="to-format-the-numeric-value"></a>Dar formato al valor numérico  
  
-   Para mostrar un valor decimal estableciendo la <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad a un entero y establecer el <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad `true` o `false`.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     O bien  
  
-   Para mostrar un valor hexadecimal estableciendo la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad `true`.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas realizan en el <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad va a probar su valor decimal.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.NumericUpDown>  
 [NumericUpDown (control)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [Información general sobre el control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
