---
title: 'Cómo: Establecer y devolver valores numéricos con el control NumericUpDown de formularios Windows Forms'
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
ms.openlocfilehash: e214f556224577c3029b2b742784e58932d792f3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33535566"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="f684e-102">Cómo: Establecer y devolver valores numéricos con el control NumericUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f684e-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="f684e-103">El valor numérico de formularios Windows Forms <xref:System.Windows.Forms.NumericUpDown> control viene determinado por su <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f684e-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="f684e-104">Puede escribir pruebas condicionales para el valor del control, como ocurre con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="f684e-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="f684e-105">Una vez el <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad está establecida, se puede ajustarla directamente si escribe código para llevar a cabo operaciones en él o se puede llamar a la <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> métodos.</span><span class="sxs-lookup"><span data-stu-id="f684e-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="f684e-106">Para establecer el valor numérico</span><span class="sxs-lookup"><span data-stu-id="f684e-106">To set the numeric value</span></span>  
  
1.  <span data-ttu-id="f684e-107">Asignar un valor a la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad en el código o en la ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="f684e-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="f684e-108">-o bien-</span><span class="sxs-lookup"><span data-stu-id="f684e-108">-or-</span></span>  
  
2.  <span data-ttu-id="f684e-109">Llame a la <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> método para aumentar o disminuir el valor en la cantidad especificada en el <xref:System.Windows.Forms.NumericUpDown.Increment%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="f684e-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="f684e-110">Para devolver el valor numérico</span><span class="sxs-lookup"><span data-stu-id="f684e-110">To return the numeric value</span></span>  
  
-   <span data-ttu-id="f684e-111">Acceso a la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad en el código.</span><span class="sxs-lookup"><span data-stu-id="f684e-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="f684e-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f684e-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="f684e-113">NumericUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="f684e-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="f684e-114">Información general sobre el control NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="f684e-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
