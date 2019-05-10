---
title: Procedimiento para establecer información sobre herramientas en controles de formularios Windows Forms en tiempo de diseño
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], for controls
- examples [Windows Forms], tooltips
ms.assetid: c4b60637-4c0a-44c2-a103-f66dff887936
ms.openlocfilehash: 0d6725fc1a00826870e6400bffce63a1788e802c
ms.sourcegitcommit: 0d0a6e96737dfe24d3257b7c94f25d9500f383ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "65211686"
---
# <a name="how-to-set-tooltips-for-controls-on-a-windows-form-at-design-time"></a><span data-ttu-id="83266-102">Procedimiento Establecer componentes ToolTip en controles de Windows Forms en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="83266-102">How to: Set ToolTips for controls on a Windows Form at design time</span></span>

<span data-ttu-id="83266-103">Puede establecer un <xref:System.Windows.Forms.ToolTip> cadena en el código o en el Diseñador de Windows Forms en Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="83266-103">You can set a <xref:System.Windows.Forms.ToolTip> string in code or in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="83266-104">Para obtener más información sobre la <xref:System.Windows.Forms.ToolTip> componente, vea [información general del componente ToolTip](tooltip-component-overview-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="83266-104">For more information about the <xref:System.Windows.Forms.ToolTip> component, see [ToolTip Component Overview](tooltip-component-overview-windows-forms.md).</span></span>

## <a name="set-a-tooltip-programmatically"></a><span data-ttu-id="83266-105">Establecer una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="83266-105">Set a ToolTip programmatically</span></span>

1. <span data-ttu-id="83266-106">Agregue el control que se mostrará la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="83266-106">Add the control that will display the ToolTip.</span></span>

2. <span data-ttu-id="83266-107">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="83266-107">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="set-a-tooltip-in-the-designer"></a><span data-ttu-id="83266-108">Establecer una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="83266-108">Set a ToolTip in the designer</span></span>

1. <span data-ttu-id="83266-109">En Visual Studio, agregue un <xref:System.Windows.Forms.ToolTip> componente al formulario.</span><span class="sxs-lookup"><span data-stu-id="83266-109">In Visual Studio, add a <xref:System.Windows.Forms.ToolTip> component to the form.</span></span>

2. <span data-ttu-id="83266-110">Seleccione el control que se mostrará la información sobre herramientas, o agréguelo al formulario.</span><span class="sxs-lookup"><span data-stu-id="83266-110">Select the control that will display the ToolTip, or add it to the form.</span></span>

3. <span data-ttu-id="83266-111">En el **propiedades** ventana, establezca el **información sobre herramientas en ToolTip1** valor a una cadena de texto adecuada.</span><span class="sxs-lookup"><span data-stu-id="83266-111">In the **Properties** window, set the **ToolTip on ToolTip1** value to an appropriate string of text.</span></span>

### <a name="to-remove-a-tooltip-programmatically"></a><span data-ttu-id="83266-112">Para quitar una información sobre herramientas mediante programación</span><span class="sxs-lookup"><span data-stu-id="83266-112">To remove a ToolTip programmatically</span></span>

1. <span data-ttu-id="83266-113">Use la <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> método de la <xref:System.Windows.Forms.ToolTip> componente.</span><span class="sxs-lookup"><span data-stu-id="83266-113">Use the <xref:System.Windows.Forms.ToolTip.SetToolTip%2A> method of the <xref:System.Windows.Forms.ToolTip> component.</span></span>

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

## <a name="remove-a-tooltip-in-the-designer"></a><span data-ttu-id="83266-114">Quitar una información sobre herramientas en el diseñador</span><span class="sxs-lookup"><span data-stu-id="83266-114">Remove a ToolTip in the designer</span></span>

1. <span data-ttu-id="83266-115">En Visual Studio, seleccione el control que muestra la información sobre herramientas.</span><span class="sxs-lookup"><span data-stu-id="83266-115">In Visual Studio, select the control that is displaying the ToolTip.</span></span>

2. <span data-ttu-id="83266-116">En el **propiedades** ventana, elimine el texto en el **información sobre herramientas en ToolTip1**.</span><span class="sxs-lookup"><span data-stu-id="83266-116">In the **Properties** window, delete the text in the **ToolTip on ToolTip1**.</span></span>

## <a name="see-also"></a><span data-ttu-id="83266-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="83266-117">See also</span></span>

- [<span data-ttu-id="83266-118">Información general sobre el componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="83266-118">ToolTip Component Overview</span></span>](tooltip-component-overview-windows-forms.md)
- [<span data-ttu-id="83266-119">Cómo: Cambiar el retardo del componente ToolTip de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="83266-119">How to: Change the Delay of the Windows Forms ToolTip Component</span></span>](how-to-change-the-delay-of-the-windows-forms-tooltip-component.md)
- [<span data-ttu-id="83266-120">ToolTip (componente)</span><span class="sxs-lookup"><span data-stu-id="83266-120">ToolTip Component</span></span>](tooltip-component-windows-forms.md)
