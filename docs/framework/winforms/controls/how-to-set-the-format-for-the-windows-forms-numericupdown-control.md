---
title: Establecer el formato del control NumericUpDown
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742177"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms
Puede configurar cómo se muestran los valores en el control Windows Forms <xref:System.Windows.Forms.NumericUpDown>. La propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0. La propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`. El control puede mostrar valores en formato hexadecimal en lugar de decimal, si la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> está establecida en `true`; el valor predeterminado es `false`.  
  
### <a name="to-format-the-numeric-value"></a>Para dar formato al valor numérico  
  
- Para mostrar un valor decimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> en un entero y establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> en `true` o `false`.  
  
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
  
- Para mostrar un valor hexadecimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> en `true`.  
  
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
    > Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas que realice en la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> comprobarán su valor decimal.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown (control)](numericupdown-control-windows-forms.md)
- [Información general sobre el control NumericUpDown](numericupdown-control-overview-windows-forms.md)
