---
title: Filtrar para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: d2bca517e98a8258d4f510c64593de2ad9646e13
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157610"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="d4473-102">Filtrar para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="d4473-102">How to: Set ToolTips for Controls on a Windows Form at Design Time</span></span>
<span data-ttu-id="d4473-103">Puede establecer un <xref:System.Windows.Forms.ToolTip> cadena en el código o en el Diseñador de Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d4473-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer.</span></span> <span data-ttu-id="d4473-104">Para obtener más información sobre la <xref:System.Windows.Forms.ToolTip> componente, vea [información general del componente ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="d4473-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4473-105">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="d4473-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="d4473-106">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="d4473-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="d4473-107">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="d4473-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-set-a-tooltip-programmatically"></a><span data-ttu-id="d4473-108">Para establecer una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="d4473-108">To set a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="d4473-109">Agregue el control que se mostrará la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="d4473-109">Add the control that will display the ToolTip.</span></span>  
  
2.  <span data-ttu-id="d4473-110">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="d4473-110">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
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
  
### <a name="to-set-a-tooltip-in-the-designer"></a><span data-ttu-id="d4473-111">Para establecer una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="d4473-111">To set a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="d4473-112">Agregue un componente <xref:System.Windows.Forms.ToolTip> al formulario.</span><span class="sxs-lookup"><span data-stu-id="d4473-112">Add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>  
  
2.  <span data-ttu-id="d4473-113">Seleccione el control que se mostrará la información sobre herramientas, o agréguelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="d4473-113">Select the control that will display the ToolTip, or add it to the form.</span></span>  
  
3.  <span data-ttu-id="d4473-114">En el **propiedades** ventana, establezca el **información sobre herramientas en ToolTip1** valor a una cadena de texto adecuada.</span><span class="sxs-lookup"><span data-stu-id="d4473-114">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>  

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="d4473-115">Para quitar una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="d4473-115">To remove a ToolTip programmatically</span></span>  
  
1.  <span data-ttu-id="d4473-116">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="d4473-116">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>  
  
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
  
### <a name="to-remove-a-tooltip-in-the-designer"></a><span data-ttu-id="d4473-117">Para quitar una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="d4473-117">To remove a ToolTip in the designer</span></span>  
  
1.  <span data-ttu-id="d4473-118">Seleccione el control que muestra la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="d4473-118">Select the control that is displaying the ToolTip.</span></span>  
  
2.  <span data-ttu-id="d4473-119">En el **propiedades** ventana, elimine el texto en el **información sobre herramientas en ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="d4473-119">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d4473-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d4473-120">See also</span></span>

- [<span data-ttu-id="d4473-121">Información general sobre el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="d4473-121">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="d4473-122">Filtrar para cambiar el retardo del componente ToolTip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d4473-122">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="d4473-123">ToolTip</span><span class="sxs-lookup"><span data-stu-id="d4473-123">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
