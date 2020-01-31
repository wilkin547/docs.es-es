---
title: Establecer y devolver valores numéricos con el control NumericUpDown
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
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743020"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a><span data-ttu-id="03258-102">Cómo: Establecer y devolver valores numéricos con el control NumericUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="03258-102">How to: Set and Return Numeric Values with the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="03258-103">El valor numérico de la Windows Forms control de <xref:System.Windows.Forms.NumericUpDown> está determinado por su propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="03258-103">The numeric value of the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control is determined by its <xref:System.Windows.Forms.NumericUpDown.Value%2A> property.</span></span> <span data-ttu-id="03258-104">Puede escribir pruebas condicionales para el valor del control del mismo modo que con cualquier otra propiedad.</span><span class="sxs-lookup"><span data-stu-id="03258-104">You can write conditional tests for the control's value just as with any other property.</span></span> <span data-ttu-id="03258-105">Una vez establecida la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A>, puede ajustarla directamente escribiendo código para realizar operaciones en ella, o puede llamar a los métodos <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> y <xref:System.Windows.Forms.NumericUpDown.DownButton%2A>.</span><span class="sxs-lookup"><span data-stu-id="03258-105">Once the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property is set, you can adjust it directly by writing code to perform operations on it, or you can call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> and <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> methods.</span></span>  
  
### <a name="to-set-the-numeric-value"></a><span data-ttu-id="03258-106">Para establecer el valor numérico</span><span class="sxs-lookup"><span data-stu-id="03258-106">To set the numeric value</span></span>  
  
1. <span data-ttu-id="03258-107">Asigne un valor a la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> en el código o en el ventana Propiedades.</span><span class="sxs-lookup"><span data-stu-id="03258-107">Assign a value to the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code or in the Properties window.</span></span>  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     <span data-ttu-id="03258-108">O bien,</span><span class="sxs-lookup"><span data-stu-id="03258-108">-or-</span></span>  
  
2. <span data-ttu-id="03258-109">Llame al método <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> o <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> para aumentar o disminuir el valor en la cantidad especificada en la propiedad <xref:System.Windows.Forms.NumericUpDown.Increment%2A>.</span><span class="sxs-lookup"><span data-stu-id="03258-109">Call the <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> or <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> method to increase or decrease the value by the amount specified in the <xref:System.Windows.Forms.NumericUpDown.Increment%2A> property.</span></span>  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a><span data-ttu-id="03258-110">Para devolver el valor numérico</span><span class="sxs-lookup"><span data-stu-id="03258-110">To return the numeric value</span></span>  
  
- <span data-ttu-id="03258-111">Obtenga acceso a la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> en el código.</span><span class="sxs-lookup"><span data-stu-id="03258-111">Access the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property in code.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="03258-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="03258-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [<span data-ttu-id="03258-113">NumericUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="03258-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="03258-114">Información general sobre el control NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="03258-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
