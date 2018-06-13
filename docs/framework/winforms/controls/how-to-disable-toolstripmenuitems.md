---
title: 'Cómo: Deshabilitar ToolStripMenuItems'
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
ms.openlocfilehash: 20d0e13642aac3004a31ff416318cf6723207379
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33532033"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="afdde-102">Cómo: Deshabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="afdde-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="afdde-103">Puede limitar o ampliar los comandos que un usuario puede realizar para habilitar y deshabilitar elementos de menú en respuesta a las actividades del usuario.</span><span class="sxs-lookup"><span data-stu-id="afdde-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="afdde-104">Elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="afdde-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="afdde-105">Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código.</span><span class="sxs-lookup"><span data-stu-id="afdde-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="afdde-106">Para deshabilitar un elemento de menú mediante programación</span><span class="sxs-lookup"><span data-stu-id="afdde-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="afdde-107">Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="afdde-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="afdde-108">Deshabilitar el elemento de menú de primer o de nivel superior en un menú oculta todos los elementos de menú contenidos en el menú, pero no deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="afdde-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="afdde-109">Del mismo modo, al deshabilitar un elemento de menú que tiene elementos de submenú oculta los elementos de submenú, pero no deshabilitará.</span><span class="sxs-lookup"><span data-stu-id="afdde-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="afdde-110">Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación ocultar y deshabilitar todo el menú, tal y como se presenta una interfaz de usuario limpia.</span><span class="sxs-lookup"><span data-stu-id="afdde-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="afdde-111">Debe ocultar y deshabilitar el menú y deshabilitar cada elemento y el elemento de submenú en el menú, ya que oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="afdde-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="afdde-112">Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.</span><span class="sxs-lookup"><span data-stu-id="afdde-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="afdde-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="afdde-113">See Also</span></span>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem>  
 [<span data-ttu-id="afdde-114">Ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="afdde-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)  
 [<span data-ttu-id="afdde-115">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="afdde-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
