---
title: para objetos de capa
description: Obtenga información sobre cómo disponer objetos en capas Windows Forms controles y formularios secundarios para crear interfaces de usuario más complejas.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, layering
- controls [Windows Forms], layering
- z order
- controls [Windows Forms], positioning
- z-order
ms.assetid: 1acc4281-2976-4715-86f4-bda68134baaf
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 6269b09c56963fefd500b9e1e6c9d7f51f9619cf
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174515"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="46f63-103">Cómo: disponer objetos en capas en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46f63-103">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="46f63-104">Cuando se crea una interfaz de usuario compleja, o cuando se trabaja con un formulario de interfaz de múltiples documentos (MDI), a menudo se desea disponer en capas los controles y los formularios secundarios para crear interfaces de usuario (UI) más complejas.</span><span class="sxs-lookup"><span data-stu-id="46f63-104">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="46f63-105">Para trasladar y realizar un seguimiento de los controles y ventanas dentro del contexto de un grupo, puede manipular su *orden z*.</span><span class="sxs-lookup"><span data-stu-id="46f63-105">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="46f63-106">El orden z es el nivel visual de los controles en un formulario a lo largo del eje z (profundidad) del formulario.</span><span class="sxs-lookup"><span data-stu-id="46f63-106">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="46f63-107">La ventana situada en la parte superior del orden z se superpone a todas las demás ventanas.</span><span class="sxs-lookup"><span data-stu-id="46f63-107">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="46f63-108">Todas las demás ventanas se superponen a la ventana en la parte inferior del orden z.</span><span class="sxs-lookup"><span data-stu-id="46f63-108">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="46f63-109">Para capas de controles en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="46f63-109">To layer controls at design time</span></span>

1. <span data-ttu-id="46f63-110">En Visual Studio, seleccione un control que desee capas.</span><span class="sxs-lookup"><span data-stu-id="46f63-110">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="46f63-111">En el menú **formato** , seleccione **pedido**y, a continuación, seleccione **traer al frente** o **enviar al fondo**.</span><span class="sxs-lookup"><span data-stu-id="46f63-111">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="46f63-112">Para capas de controles mediante programación</span><span class="sxs-lookup"><span data-stu-id="46f63-112">To layer controls programmatically</span></span>

<span data-ttu-id="46f63-113">Utilice los <xref:System.Windows.Forms.Control.BringToFront%2A> <xref:System.Windows.Forms.Control.SendToBack%2A> métodos y para manipular el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="46f63-113">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="46f63-114">Por ejemplo, si un <xref:System.Windows.Forms.TextBox> control, `txtFirstName` , está bajo otro control y desea que esté en primer lugar, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="46f63-114">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

```vb
txtFirstName.BringToFront()
```

```csharp
txtFirstName.BringToFront();
```

```cpp
txtFirstName->BringToFront();
```

> [!NOTE]
> <span data-ttu-id="46f63-115">Windows Forms admite la *contención de controles*.</span><span class="sxs-lookup"><span data-stu-id="46f63-115">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="46f63-116">La contención de controles implica la colocación de varios controles dentro de un control contenedor, como una serie de <xref:System.Windows.Forms.RadioButton> controles de un <xref:System.Windows.Forms.GroupBox> control.</span><span class="sxs-lookup"><span data-stu-id="46f63-116">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="46f63-117">A continuación, puede disponer los controles en el control contenedor.</span><span class="sxs-lookup"><span data-stu-id="46f63-117">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="46f63-118">Al mover el cuadro de grupo también se mueven los controles, ya que están incluidos en él.</span><span class="sxs-lookup"><span data-stu-id="46f63-118">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="46f63-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="46f63-119">See also</span></span>

- [<span data-ttu-id="46f63-120">Windows Forms controles</span><span class="sxs-lookup"><span data-stu-id="46f63-120">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="46f63-121">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="46f63-121">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="46f63-122">Controles que se utilizan en formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="46f63-122">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="46f63-123">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="46f63-123">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
