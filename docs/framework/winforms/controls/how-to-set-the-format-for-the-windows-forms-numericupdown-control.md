---
title: Procedimiento para establecer el formato del control NumericUpDown de formularios Windows Forms
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 6db7a1b2aeb7282c3ac827cb8319706ed348fc22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949161"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedimiento para establecer el formato del control NumericUpDown de formularios Windows Forms
Puede configurar cómo se muestran los valores en el control <xref:System.Windows.Forms.NumericUpDown> Windows Forms. La <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0. La <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad determina si se insertará un separador entre cada tres dígitos decimales; `false`el valor predeterminado es. El control puede mostrar valores en formato hexadecimal en lugar de decimal, si la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad está establecida en `true`; el valor predeterminado `false`es.  
  
### <a name="to-format-the-numeric-value"></a>Para dar formato al valor numérico  
  
- Para mostrar un valor decimal, establezca <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> la propiedad en un entero y establezca la <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad en `true` o `false`.  
  
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
  
- Para mostrar un valor hexadecimal, establezca <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> la propiedad `true`en.  
  
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
    > Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas que realice en la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad comprobarán su valor decimal.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown (control)](numericupdown-control-windows-forms.md)
- [Información general sobre el control NumericUpDown](numericupdown-control-overview-windows-forms.md)
