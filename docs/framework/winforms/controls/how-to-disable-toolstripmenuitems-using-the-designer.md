---
title: Procedimiento para deshabilitar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 692b6c11f6d58c52a0af29ed04ada45c48cae058
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046238"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="71d57-102">Procedimiento para deshabilitar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="71d57-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="71d57-103">Puede limitar o ampliar los comandos que puede realizar un usuario habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario.</span><span class="sxs-lookup"><span data-stu-id="71d57-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="71d57-104">Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ajustar a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="71d57-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="71d57-105">Puede manipular esta propiedad en tiempo de diseño en la ventana **propiedades** o mediante programación estableciéndolo en código.</span><span class="sxs-lookup"><span data-stu-id="71d57-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="71d57-106">Para obtener más información, consulte [Cómo Deshabilite](how-to-disable-toolstripmenuitems.md)ToolStripMenuItems.</span><span class="sxs-lookup"><span data-stu-id="71d57-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>

## <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="71d57-107">Para deshabilitar un elemento de menú en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="71d57-107">To disable a menu item at design time</span></span>

1. <span data-ttu-id="71d57-108">Con el elemento de menú seleccionado en el formulario, establezca <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> la propiedad `false`en.</span><span class="sxs-lookup"><span data-stu-id="71d57-108">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>

    > [!TIP]
    > <span data-ttu-id="71d57-109">Al deshabilitar el primer elemento de menú de nivel superior de un menú, se deshabilitan todos los elementos de menú incluidos en el menú.</span><span class="sxs-lookup"><span data-stu-id="71d57-109">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="71d57-110">Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú, se deshabilitan los elementos de submenú.</span><span class="sxs-lookup"><span data-stu-id="71d57-110">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="71d57-111">Si todos los comandos de un menú determinado no están disponibles para el usuario, se considera una buena práctica de programación para ocultar y deshabilitar todo el menú, ya que esto presenta una interfaz de usuario limpia.</span><span class="sxs-lookup"><span data-stu-id="71d57-111">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="71d57-112">Debe ocultar y deshabilitar el menú, ya que ocultar solo no impide el acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="71d57-112">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="71d57-113">Establezca la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior `false` en para ocultar todo el menú.</span><span class="sxs-lookup"><span data-stu-id="71d57-113">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>

## <a name="see-also"></a><span data-ttu-id="71d57-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="71d57-114">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="71d57-115">Cómo: Ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="71d57-115">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="71d57-116">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="71d57-116">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
