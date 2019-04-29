---
title: Procedimiento para cambiar el retardo del componente ToolTip de formularios Windows Forms
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
ms.openlocfilehash: cf257cccd272c16c3d7c3d403456265444fc8ac8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61781243"
---
# <a name="how-to-change-the-delay-of-the-windows-forms-tooltip-component"></a><span data-ttu-id="dbfcb-102">Procedimiento para cambiar el retardo del componente ToolTip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="dbfcb-102">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>
<span data-ttu-id="dbfcb-103">Hay varios valores de retraso que se pueden establecer para un formulario Windows Forms <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-103">There are multiple delay values that you can set for a Windows Forms <xref:System.Windows.Forms.ToolTip> component.</span></span> <span data-ttu-id="dbfcb-104">La unidad de medida para todas estas propiedades es milisegundos.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-104">The unit of measure for all these properties is milliseconds.</span></span> <span data-ttu-id="dbfcb-105">El <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> propiedad determina cuánto tiempo debe apuntar el usuario en el control asociado para que aparezca en la cadena de información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-105">The <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> property determines how long the user must point at the associated control for the ToolTip string to appear.</span></span> <span data-ttu-id="dbfcb-106">El <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> propiedad establece el número de milisegundos que tarda subsiguientes cadenas de información sobre herramientas aparezca como el mouse se mueve desde un control asociado a la información sobre herramientas a otra.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-106">The <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> property sets the number of milliseconds it takes for subsequent ToolTip strings to appear as the mouse moves from one ToolTip-associated control to another.</span></span> <span data-ttu-id="dbfcb-107">El <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> propiedad determina el período de tiempo que se muestra la cadena de información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-107">The <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> property determines the length of time the ToolTip string is shown.</span></span> <span data-ttu-id="dbfcb-108">Puede establecer estos valores individualmente, o estableciendo el valor de la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad; el retraso de otro propiedades se establecen en función del valor asignado a la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-108">You can set these values individually, or by setting the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property; the other delay properties are set based on the value assigned to the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property.</span></span> <span data-ttu-id="dbfcb-109">Por ejemplo, cuando <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> está establecido en un valor N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> se establece en N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> se establece en el valor de <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> dividido por cinco (o N/5) y <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> está establecido en un valor que es cinco veces el valor de la <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> propiedad (o cantidad 5 veces).</span><span class="sxs-lookup"><span data-stu-id="dbfcb-109">For example, when <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> is set to a value N, <xref:System.Windows.Forms.ToolTip.InitialDelay%2A> is set to N, <xref:System.Windows.Forms.ToolTip.ReshowDelay%2A> is set to the value of <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> divided by five (or N/5), and <xref:System.Windows.Forms.ToolTip.AutoPopDelay%2A> is set to a value that is five times the value of the <xref:System.Windows.Forms.ToolTip.AutomaticDelay%2A> property (or 5N).</span></span>  
  
### <a name="to-set-the-delay"></a><span data-ttu-id="dbfcb-110">Para establecer el retraso</span><span class="sxs-lookup"><span data-stu-id="dbfcb-110">To set the delay</span></span>  
  
1. <span data-ttu-id="dbfcb-111">Establezca las siguientes propiedades tal como se muestra en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="dbfcb-111">Set the following properties as shown in this example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbfcb-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="dbfcb-112">See also</span></span>

- [<span data-ttu-id="dbfcb-113">Información general sobre el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="dbfcb-113">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="dbfcb-114">Cómo: Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="dbfcb-114">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>](how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time.md)
- [<span data-ttu-id="dbfcb-115">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="dbfcb-115">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
