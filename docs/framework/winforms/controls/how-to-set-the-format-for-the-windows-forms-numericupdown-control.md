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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="a0c83-102">Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0c83-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="a0c83-103">Puede configurar cómo se muestran los valores en el control Windows Forms <xref:System.Windows.Forms.NumericUpDown>.</span><span class="sxs-lookup"><span data-stu-id="a0c83-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="a0c83-104">La propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="a0c83-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="a0c83-105">La propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a0c83-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="a0c83-106">El control puede mostrar valores en formato hexadecimal en lugar de decimal, si la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> está establecida en `true`; el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="a0c83-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="a0c83-107">Para dar formato al valor numérico</span><span class="sxs-lookup"><span data-stu-id="a0c83-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="a0c83-108">Para mostrar un valor decimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> en un entero y establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> en `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="a0c83-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="a0c83-109">O bien,</span><span class="sxs-lookup"><span data-stu-id="a0c83-109">-or-</span></span>  
  
- <span data-ttu-id="a0c83-110">Para mostrar un valor hexadecimal, establezca la propiedad <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="a0c83-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="a0c83-111">Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas que realice en la propiedad <xref:System.Windows.Forms.NumericUpDown.Value%2A> comprobarán su valor decimal.</span><span class="sxs-lookup"><span data-stu-id="a0c83-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0c83-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="a0c83-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="a0c83-113">NumericUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="a0c83-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="a0c83-114">Información general sobre el control NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="a0c83-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
