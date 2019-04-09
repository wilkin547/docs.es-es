---
title: Filtrar para deshabilitar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], disabling in designer
- MenuStrip control [Windows Forms], disabling menu items in designer
- menu items [Windows Forms], disabling
- menus [Windows Forms], disabling items
ms.assetid: 985e311e-7d67-4205-b5a3-d045b68a4a03
ms.openlocfilehash: 38a366003a856adaf0840d0d8911263bc40dfe23
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59151416"
---
# <a name="how-to-disable-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="fd7e6-102">Filtrar para deshabilitar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="fd7e6-102">How to: Disable ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="fd7e6-103">Puede limitar o ampliar los comandos que un usuario puede realizar mediante la habilitación y deshabilitación de los elementos de menú en respuesta a las actividades del usuario.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-103">You can limit or broaden the commands a user may make by enabling and disabling menu items in response to user activities.</span></span> <span data-ttu-id="fd7e6-104">Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante el <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-104">Menu items are enabled by default when they are created, but this can be adjusted through the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property.</span></span> <span data-ttu-id="fd7e6-105">Puede manipular esta propiedad en tiempo de diseño en el **propiedades** ventana o mediante programación si se establece en el código.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-105">You can manipulate this property at design time in the **Properties** window or programmatically by setting it in code.</span></span> <span data-ttu-id="fd7e6-106">Para obtener más información, vea [Cómo: Deshabilitar ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span><span class="sxs-lookup"><span data-stu-id="fd7e6-106">For more information, see [How to: Disable ToolStripMenuItems](how-to-disable-toolstripmenuitems.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fd7e6-107">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="fd7e6-108">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="fd7e6-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="fd7e6-109">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="fd7e6-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-disable-a-menu-item-at-design-time"></a><span data-ttu-id="fd7e6-110">Para deshabilitar un elemento de menú en tiempo de diseño</span><span class="sxs-lookup"><span data-stu-id="fd7e6-110">To disable a menu item at design time</span></span>  
  
1.  <span data-ttu-id="fd7e6-111">Con el elemento de menú seleccionado en el formulario, establezca la <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-111">With the menu item selected on the form, set the <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> property to `false`.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="fd7e6-112">Al deshabilitar el elemento de menú de primer o de nivel superior en un menú, deshabilitan todos los elementos de menú contenidos en el menú.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-112">Disabling the first or top-level menu item in a menu disables all the menu items contained within the menu.</span></span> <span data-ttu-id="fd7e6-113">Del mismo modo, la deshabilitación de un elemento de menú que tiene elementos de submenú deshabilita los elementos de submenú.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-113">Likewise, disabling a menu item that has submenu items disables the submenu items.</span></span> <span data-ttu-id="fd7e6-114">Si todos los comandos de un menú no están disponibles para el usuario, se considera buena práctica de programación para ocultar y deshabilitar todo el menú, como esto presenta una interfaz de usuario limpia.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-114">If all the commands on a given menu are unavailable to the user, it is considered good programming practice to both hide and disable the entire menu, as this presents a clean user interface.</span></span> <span data-ttu-id="fd7e6-115">Se debe ocultar y deshabilitar el menú, como oculta por sí solo no impide el acceso a un comando de menú a través de una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-115">You should both hide and disable the menu, as hiding alone does not prevent access to a menu command via a shortcut key.</span></span> <span data-ttu-id="fd7e6-116">Establecer el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad de un elemento de menú de nivel superior para `false` para ocultar todo el menú.</span><span class="sxs-lookup"><span data-stu-id="fd7e6-116">Set the <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property of a top-level menu item to `false` to hide the entire menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd7e6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd7e6-117">See also</span></span>

- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem>
- [<span data-ttu-id="fd7e6-118">Filtrar para ocultar ToolStripMenuItems</span><span class="sxs-lookup"><span data-stu-id="fd7e6-118">How to: Hide ToolStripMenuItems</span></span>](how-to-hide-toolstripmenuitems.md)
- [<span data-ttu-id="fd7e6-119">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="fd7e6-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
