---
title: Procedimiento para deshabilitar ToolStripMenuItems
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], enabling
- ToolStripMenuItems [Windows Forms], disabling
- menu items [Windows Forms], disabling
- disabling menu items
- menu items [Windows Forms], enabling
- menus [Windows Forms], disabling menu items
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
ms.openlocfilehash: f86a2934e799e4604693491dacbecc517d44d810
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046223"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="6a1a1-102">Procedimiento para deshabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="6a1a1-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="6a1a1-103">Puede limitar o ampliar los comandos que puede realizar un usuario habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="6a1a1-104">Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> ajustar a través de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="6a1a1-105">Puede manipular esta propiedad en tiempo de diseño en la ventana **propiedades** o mediante programación estableciéndolo en código.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="6a1a1-106">Para deshabilitar un elemento de menú mediante programación</span><span class="sxs-lookup"><span data-stu-id="6a1a1-106">To disable a menu item programmatically</span></span>  
  
- <span data-ttu-id="6a1a1-107">Dentro del método donde se establecen las propiedades del elemento de menú, agregue código para establecer la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    > <span data-ttu-id="6a1a1-108">Al deshabilitar el primer elemento de menú de nivel superior de un menú, se ocultan todos los elementos de menú incluidos en el menú, pero no se deshabilitan.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="6a1a1-109">Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú, se ocultan los elementos de submenú, pero no se deshabilitan.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="6a1a1-110">Si todos los comandos de un menú determinado no están disponibles para el usuario, se considera una buena práctica de programación para ocultar y deshabilitar todo el menú, ya que esto presenta una interfaz de usuario limpia.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="6a1a1-111">Debe ocultar y deshabilitar el menú, y deshabilitar todos los elementos y elementos de submenú en el menú, ya que ocultar solo no impide el acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="6a1a1-112">Establezca la <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior `false` en para ocultar todo el menú.</span><span class="sxs-lookup"><span data-stu-id="6a1a1-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a1a1-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a1a1-113">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="6a1a1-114">Procedimientos: Ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="6a1a1-114">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="6a1a1-115">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="6a1a1-115">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
