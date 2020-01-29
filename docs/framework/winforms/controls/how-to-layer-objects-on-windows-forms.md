---
title: para objetos de capa
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
ms.openlocfilehash: 1615b9c4df222edd95cda9bceae622ba6f1d8d78
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736345"
---
# <a name="how-to-layer-objects-on-windows-forms"></a><span data-ttu-id="2a245-102">Cómo: disponer objetos en capas en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a245-102">How to: Layer objects on Windows Forms</span></span>

<span data-ttu-id="2a245-103">Cuando se crea una interfaz de usuario compleja, o cuando se trabaja con un formulario de interfaz de múltiples documentos (MDI), a menudo se desea disponer en capas los controles y los formularios secundarios para crear interfaces de usuario (UI) más complejas.</span><span class="sxs-lookup"><span data-stu-id="2a245-103">When you create a complex user interface, or work with a multiple document interface (MDI) form, you will often want to layer both controls and child forms to create more complex user interfaces (UI).</span></span> <span data-ttu-id="2a245-104">Para trasladar y realizar un seguimiento de los controles y ventanas dentro del contexto de un grupo, puede manipular su *orden z*.</span><span class="sxs-lookup"><span data-stu-id="2a245-104">To move and keep track of controls and windows within the context of a group, you manipulate their *z-order*.</span></span> <span data-ttu-id="2a245-105">El orden z es el nivel visual de los controles en un formulario a lo largo del eje z (profundidad) del formulario.</span><span class="sxs-lookup"><span data-stu-id="2a245-105">Z-order is the visual layering of controls on a form along the form's z-axis (depth).</span></span> <span data-ttu-id="2a245-106">La ventana situada en la parte superior del orden z se superpone a todas las demás ventanas.</span><span class="sxs-lookup"><span data-stu-id="2a245-106">The window at the top of the z-order overlaps all other windows.</span></span> <span data-ttu-id="2a245-107">Todas las demás ventanas se superponen a la ventana en la parte inferior del orden z.</span><span class="sxs-lookup"><span data-stu-id="2a245-107">All other windows overlap the window at the bottom of the z-order.</span></span>

## <a name="to-layer-controls-at-design-time"></a><span data-ttu-id="2a245-108">Para capas de controles en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="2a245-108">To layer controls at design time</span></span>

1. <span data-ttu-id="2a245-109">En Visual Studio, seleccione un control que desee capas.</span><span class="sxs-lookup"><span data-stu-id="2a245-109">In Visual Studio, select a control that you want to layer.</span></span>

2. <span data-ttu-id="2a245-110">En el menú **formato** , seleccione **pedido**y, a continuación, seleccione **traer al frente** o **enviar al fondo**.</span><span class="sxs-lookup"><span data-stu-id="2a245-110">On the **Format** menu, select **Order**, and then select **Bring To Front** or **Send To Back**.</span></span>

## <a name="to-layer-controls-programmatically"></a><span data-ttu-id="2a245-111">Para capas de controles mediante programación</span><span class="sxs-lookup"><span data-stu-id="2a245-111">To layer controls programmatically</span></span>

<span data-ttu-id="2a245-112">Utilice los métodos <xref:System.Windows.Forms.Control.BringToFront%2A> y <xref:System.Windows.Forms.Control.SendToBack%2A> para manipular el orden z de los controles.</span><span class="sxs-lookup"><span data-stu-id="2a245-112">Use the <xref:System.Windows.Forms.Control.BringToFront%2A> and <xref:System.Windows.Forms.Control.SendToBack%2A> methods to manipulate the z-order of the controls.</span></span>

<span data-ttu-id="2a245-113">Por ejemplo, si un control de <xref:System.Windows.Forms.TextBox>, `txtFirstName`, está debajo de otro control y desea que esté en primer lugar, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="2a245-113">For example, if a <xref:System.Windows.Forms.TextBox> control, `txtFirstName`, is underneath another control and you want to have it on top, use the following code:</span></span>

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
> <span data-ttu-id="2a245-114">Windows Forms admite la *contención de controles*.</span><span class="sxs-lookup"><span data-stu-id="2a245-114">Windows Forms supports *control containment*.</span></span> <span data-ttu-id="2a245-115">La contención de controles implica la colocación de varios controles dentro de un control contenedor, como varios controles <xref:System.Windows.Forms.RadioButton> dentro de un control <xref:System.Windows.Forms.GroupBox>.</span><span class="sxs-lookup"><span data-stu-id="2a245-115">Control containment involves placing a number of controls within a containing control, such as a number of <xref:System.Windows.Forms.RadioButton> controls within a <xref:System.Windows.Forms.GroupBox> control.</span></span> <span data-ttu-id="2a245-116">A continuación, puede disponer los controles en el control contenedor.</span><span class="sxs-lookup"><span data-stu-id="2a245-116">You can then layer the controls within the containing control.</span></span> <span data-ttu-id="2a245-117">Al mover el cuadro de grupo también se mueven los controles, ya que están incluidos en él.</span><span class="sxs-lookup"><span data-stu-id="2a245-117">Moving the group box moves the controls as well, because they are contained inside it.</span></span>

## <a name="see-also"></a><span data-ttu-id="2a245-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a245-118">See also</span></span>

- [<span data-ttu-id="2a245-119">Controles de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a245-119">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="2a245-120">Asignar etiquetas a controles individuales de formularios Windows Forms y proporcionar accesos directos a los mismos</span><span class="sxs-lookup"><span data-stu-id="2a245-120">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="2a245-121">Controles que se utilizan en Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2a245-121">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="2a245-122">Controles de formularios Windows Forms por función</span><span class="sxs-lookup"><span data-stu-id="2a245-122">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
