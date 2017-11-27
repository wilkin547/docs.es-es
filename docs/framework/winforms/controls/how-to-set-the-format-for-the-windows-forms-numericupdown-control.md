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
ms.openlocfilehash: 001cc32aa9e1f31695f3b349480b6dd5154b31a8
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="5b881-102">Cómo: Establecer el formato del control NumericUpDown de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="5b881-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="5b881-103">Puede configurar cómo se muestran los valores en los formularios Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span><span class="sxs-lookup"><span data-stu-id="5b881-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="5b881-104">El <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad determina cuántos números aparecen después del separador decimal; el valor predeterminado es 0.</span><span class="sxs-lookup"><span data-stu-id="5b881-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="5b881-105">El <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad determina si se insertará un separador entre cada tres dígitos decimales; el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="5b881-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="5b881-106">El control puede mostrar valores en formato hexadecimal en lugar de formato decimal, si la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad está establecida en `true`; el valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="5b881-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="5b881-107">Dar formato al valor numérico</span><span class="sxs-lookup"><span data-stu-id="5b881-107">To format the numeric value</span></span>  
  
-   <span data-ttu-id="5b881-108">Para mostrar un valor decimal estableciendo la <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> propiedad a un entero y establecer el <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> propiedad `true` o `false`.</span><span class="sxs-lookup"><span data-stu-id="5b881-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="5b881-109">O bien</span><span class="sxs-lookup"><span data-stu-id="5b881-109">-or-</span></span>  
  
-   <span data-ttu-id="5b881-110">Para mostrar un valor hexadecimal estableciendo la <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> propiedad `true`.</span><span class="sxs-lookup"><span data-stu-id="5b881-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="5b881-111">Incluso si el valor se muestra en el formulario como hexadecimal, las pruebas realizan en el <xref:System.Windows.Forms.NumericUpDown.Value%2A> propiedad va a probar su valor decimal.</span><span class="sxs-lookup"><span data-stu-id="5b881-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b881-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b881-112">See Also</span></span>  
 <xref:System.Windows.Forms.NumericUpDown>  
 [<span data-ttu-id="5b881-113">NumericUpDown (control)</span><span class="sxs-lookup"><span data-stu-id="5b881-113">NumericUpDown Control</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-windows-forms.md)  
 [<span data-ttu-id="5b881-114">Información general sobre el control NumericUpDown</span><span class="sxs-lookup"><span data-stu-id="5b881-114">NumericUpDown Control Overview</span></span>](../../../../docs/framework/winforms/controls/numericupdown-control-overview-windows-forms.md)
