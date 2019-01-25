---
title: Procedimiento Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: ebefe596728b5cabd9d24720d8c39f13c8836bd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609413"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="38498-102">Procedimiento Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="38498-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="38498-103">Puede establecer un <xref:System.Windows.Forms.ToolTip> cadena en el código o en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="38498-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="38498-104">Para obtener más información sobre la <xref:System.Windows.Forms.ToolTip> componente, vea [información general del componente ToolTip](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="38498-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38498-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="38498-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="38498-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="38498-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="38498-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="38498-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="38498-108">Para establecer una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="38498-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="38498-109">Agregue el control que se mostrará la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="38498-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="38498-110">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="38498-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control to display the ToolTip.  
    ToolTip1.SetToolTip(Button1, "Save changes")  
    ```  
  
    ```csharp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1.SetToolTip(button1, "Save changes");  
    ```  
  
    ```cpp  
    // In this example, button1 is the control to display the ToolTip.  
    toolTip1->SetToolTip(button1, "Save changes");  
    ```  
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="38498-111">Para establecer una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="38498-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="38498-112">Agregue un componente <xref:System.Windows.Forms.ToolTip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="38498-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="38498-113">Seleccione el control que se mostrará la información sobre herramientas, o agréguelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="38498-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="38498-114">En el **propiedades** ventana, establezca el **información sobre herramientas en ToolTip1** valor a una cadena de texto adecuada.</span><span class="sxs-lookup"><span data-stu-id="38498-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="38498-115">Para quitar una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="38498-115">To remove a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="38498-116">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="38498-116">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
    ```vb  
    ' In this example, Button1 is the control displaying the ToolTip.  
    ToolTip1.SetToolTip(Button1, Nothing)  
    ```  
  
    ```csharp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1.SetToolTip(button1, null);  
    ```  
  
    ```cpp  
    // In this example, button1 is the control displaying the ToolTip.  
    toolTip1->SetToolTip(button1, NULL);  
    ```  
  
### <a name="to-remove-a-tooltip-in-the-designer"></a><span data-ttu-id="38498-117">Para quitar una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="38498-117">To remove a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="38498-118">Seleccione el control que muestra la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="38498-118">Select the control that is displaying the ToolTip.</span></span>  
  
2.  <span data-ttu-id="38498-119">En el **propiedades** ventana, elimine el texto en el **información sobre herramientas en ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="38498-119">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="38498-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="38498-120">See also</span></span>
- [<span data-ttu-id="38498-121">Información general sobre el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="38498-121">ToolTip Component Overview</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="38498-122">Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="38498-122">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="38498-123">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="38498-123">ToolTip Component</span></span>](../../../../docs/framework/winforms/controls/tooltip-component-windows-forms.md)
