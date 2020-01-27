---
title: Cambiar el retraso del componente ToolTip
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolTip component [Windows Forms], delay values
- tooltips [Windows Forms], delay values
- examples [Windows Forms], tooltips
ms.assetid: 08979ba7-dd84-477b-ab17-8d06e759be99
ms.openlocfilehash: 8ab0b0760e8c82d752eaada19f14cae57fa63fdc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746586"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="f5460-102">Cómo: Cambiar el retardo del componente ToolTip de Windows Forms</span><span class="sxs-lookup"><span data-stu-id="f5460-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="f5460-103">Hay varios valores de retraso que puede establecer para un componente de <xref:System.Windows.Forms.ToolTip> de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="f5460-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="f5460-104">La unidad de medida para todas estas propiedades es de milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f5460-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="f5460-105">La propiedad <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> determina cuánto tiempo debe apuntar el usuario al control asociado para que aparezca la cadena de información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="f5460-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="f5460-106">La propiedad <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> establece el número de milisegundos que tardan en aparecer las siguientes cadenas de información sobre herramientas cuando el mouse se mueve de un control asociado a la información sobre herramientas a otro.</span><span class="sxs-lookup"><span data-stu-id="f5460-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="f5460-107">La propiedad <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> determina la cantidad de tiempo que se muestra la cadena de información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="f5460-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="f5460-108">Puede establecer estos valores individualmente o estableciendo el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>; las demás propiedades de retraso se establecen en función del valor asignado a la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A>.</span><span class="sxs-lookup"><span data-stu-id="f5460-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="f5460-109">Por ejemplo, cuando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> está establecido en un valor N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> se establece en N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> se establece en el valor de <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividido entre cinco (o N/5) y <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> se establece en un valor que es cinco veces el valor de la propiedad <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> (o cantidad 5 veces).</span><span class="sxs-lookup"><span data-stu-id="f5460-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="f5460-110">Para establecer el retraso</span><span class="sxs-lookup"><span data-stu-id="f5460-110">To set the delay</span></span>  
  
1. <span data-ttu-id="f5460-111">Establezca las siguientes propiedades como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f5460-111">Set the following properties as shown in this example.</span></span>  
  
    ```vb  
    ToolTip1.InitialDelay = 500  
    ToolTip1.ReshowDelay = 100  
    ToolTip1.AutoPopDelay = 5000  
    ```  
  
    ```csharp  
    ToolTip1.InitialDelay = 500;  
    ToolTip1.ReshowDelay = 100;  
    ToolTip1.AutoPopDelay = 5000;  
    ```  
  
    ```cpp  
    toolTip1->InitialDelay = 500;  
    toolTip1->ReshowDelay = 100;  
    toolTip1->AutoPopDelay = 5000;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f5460-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5460-112">See also</span></span>

- [<span data-ttu-id="f5460-113">Información general sobre el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="f5460-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="f5460-114">Establecer información sobre herramientas en controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="f5460-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="f5460-115">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="f5460-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
