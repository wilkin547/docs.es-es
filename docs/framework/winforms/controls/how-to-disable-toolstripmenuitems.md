---
title: Procedimiento Deshabilitar ToolStripMenuItems
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
ms.openlocfilehash: 2516080708bba207c3a1d028f2e5a2411974ae5b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705341"
---
# <a name="how-to-disable-toolstripmenuitems"></a><span data-ttu-id="c8f98-102">Procedimiento Deshabilitar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="c8f98-102">How to: Disable ToolStripMenuItems</span></span>
<span data-ttu-id="c8f98-103">Puede limitar o ampliar los comandos que un usuario puede realizar mediante la habilitación y deshabilitación de los elementos de menú en respuesta a las actividades del usuario.</span><span class="sxs-lookup"><span data-stu-id="c8f98-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="c8f98-104">Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="c8f98-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="c8f98-105">Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código.</span><span class="sxs-lookup"><span data-stu-id="c8f98-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span>  
  
### <a name="to-disable-a-menu-item-programmatically"></a><span data-ttu-id="c8f98-106">Para deshabilitar un elemento de menú mediante programación</span><span class="sxs-lookup"><span data-stu-id="c8f98-106">To disable a menu item programmatically</span></span>  
  
-   <span data-ttu-id="c8f98-107">Dentro del método donde estableció las propiedades del elemento de menú, agregue código para establecer el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="c8f98-107">Within the method where you set the properties of the menu item, add code to set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
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
    >  <span data-ttu-id="c8f98-108">Deshabilitar el elemento de menú de primer o de nivel superior en un menú oculta todos los elementos de menú contenidos en el menú, pero no deshabilita.</span><span class="sxs-lookup"><span data-stu-id="c8f98-108">Disabling the first or top-level menu item in a menu hides all the menu items contained within the menu, but does not disable them.</span></span> <span data-ttu-id="c8f98-109">Del mismo modo, la deshabilitación de un elemento de menú que tiene elementos de submenú oculta los elementos de submenú, pero deshabilitarlas.</span><span class="sxs-lookup"><span data-stu-id="c8f98-109">Likewise, disabling a menu item that has submenu items hides the submenu items, but does not disable them.</span></span> <span data-ttu-id="c8f98-110">Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación para ocultar y deshabilitar todo el menú, como esto presenta una interfaz de usuario limpia.</span><span class="sxs-lookup"><span data-stu-id="c8f98-110">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="c8f98-111">Se debe ocultar y deshabilite el menú y cada elemento y el elemento de submenú en el menú, porque oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="c8f98-111">You should hide and disable the menu, and disable every item and submenu item in the menu, because hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="c8f98-112">Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.</span><span class="sxs-lookup"><span data-stu-id="c8f98-112">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f98-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f98-113">See also</span></span>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="c8f98-114">Cómo: Ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="c8f98-114">How to: Hide ToolStripMenuItems</span></span>](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="c8f98-115">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="c8f98-115">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
