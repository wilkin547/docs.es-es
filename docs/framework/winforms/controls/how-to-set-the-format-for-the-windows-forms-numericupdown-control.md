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
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="bdcd7-102">Procedimiento para establecer el formato del control NumericUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="bdcd7-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="bdcd7-103">Puede configurar cómo se muestran los valores en el control <xref:System.Windows.Forms.NumericUpDown> Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="bdcd7-104">La <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="bdcd7-105">La <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad determina si se insertará un separador entre cada tres dígitos decimales; `false`el valor predeterminado es.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="bdcd7-106">El control puede mostrar valores en formato hexadecimal en lugar de decimal, si la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad está establecida en `true`; el valor predeterminado `false`es.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="bdcd7-107">Para dar formato al valor numérico</span><span class="sxs-lookup"><span data-stu-id="bdcd7-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="bdcd7-108">Para mostrar un valor decimal, establezca <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> la propiedad en un entero y establezca la <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad en `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="bdcd7-109">-o bien-</span><span class="sxs-lookup"><span data-stu-id="bdcd7-109">-or-</span></span>  
  
- <span data-ttu-id="bdcd7-110">Para mostrar un valor hexadecimal, establezca <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> la propiedad `true`en.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="bdcd7-111">Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas que realice en la <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad comprobarán su valor decimal.</span><span class="sxs-lookup"><span data-stu-id="bdcd7-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdcd7-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdcd7-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="bdcd7-113">NumericUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="bdcd7-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="bdcd7-114">Información general sobre el control NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="bdcd7-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
