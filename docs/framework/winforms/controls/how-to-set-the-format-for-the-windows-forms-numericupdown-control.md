---
title: 'Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 1cb8f8b7d2f86125736c08cd9eadf4eee30063bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33533964"
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
  
     -o bien-  
  
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
