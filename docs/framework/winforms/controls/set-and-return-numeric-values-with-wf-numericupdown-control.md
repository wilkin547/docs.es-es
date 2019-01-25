---
title: Procedimiento Establecer y devolver valores numéricos con el Control NumericUpDown de formularios de Windows
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: 4fd995e5f7694616d7b6be7aa9a2eab6611997b0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688966"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>Procedimiento Establecer y devolver valores numéricos con el Control NumericUpDown de formularios de Windows
El valor numérico de los formularios de Windows <xref:System.Windows.Forms.NumericUpDown> control viene determinada por su <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad. Puede escribir pruebas condicionales para el valor del control al igual que con cualquier otra propiedad. Una vez el <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad está establecida, se puede ajustar directamente al escribir código para realizar operaciones en él o puede llamar a la <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> métodos.  
  
### <a name="to-set-the-numeric-value"></a>Para establecer el valor numérico  
  
1.  Asignar un valor a la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad en el código o en la ventana Propiedades.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     O bien  
  
2.  Llame a la <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> método para aumentar o disminuir el valor en la cantidad especificada en el <xref:System.Windows.Forms.NumericUpDown.Increment%2A> propiedad.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>Para devolver el valor numérico  
  
-   Acceso a la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad en el código.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown (control)](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)
- [Información general sobre el control NumericUpDown](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
