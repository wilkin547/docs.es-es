---
title: Procedimiento Establecer el formato del control NumericUpDown de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: e5c387fe593082e08ad39cb4582c946ca986a79e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713935"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>Procedimiento Establecer el formato del control NumericUpDown de formularios de Windows
Puede configurar cómo se muestran los valores en los formularios de Windows <xref:System.Windows.Forms.NumericUpDown> control. El <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0. El <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`. El control puede mostrar valores en formato hexadecimal, en lugar de formato decimal, si la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad está establecida en `true`; el valor predeterminado es `false`.  
  
### <a name="to-format-the-numeric-value"></a>Dar formato al valor numérico  
  
-   Mostrar un valor decimal estableciendo el <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad a un entero y la configuración de la <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad `true` o `false`.  
  
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
  
-   Mostrar un valor hexadecimal estableciendo el <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad `true`.  
  
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
    >  Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas realice en el <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad va a probar su valor decimal.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown (control)](numericupdown-control-windows-forms.md)
- [Información general sobre el control NumericUpDown](numericupdown-control-overview-windows-forms.md)
