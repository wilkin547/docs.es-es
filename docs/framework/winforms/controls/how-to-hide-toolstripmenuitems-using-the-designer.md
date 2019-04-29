---
title: Procedimiento para ocultar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 31c597a0e2cbf41484f19c8d4179823e9fb929ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941211"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="f4a58-102">Procedimiento para ocultar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f4a58-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="f4a58-103">Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario.</span><span class="sxs-lookup"><span data-stu-id="f4a58-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="f4a58-104">A menudo, deseará ocultar un menú completo cuando no están disponibles todos los elementos de menú en él.</span><span class="sxs-lookup"><span data-stu-id="f4a58-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="f4a58-105">Esto supone menos distracciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="f4a58-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="f4a58-106">Además, es posible que desea ocultar y deshabilitar el menú o elemento de menú, como ocultar por sí solo no impide que el usuario acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="f4a58-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="f4a58-107">Para obtener más información acerca de cómo deshabilitar los elementos de menú, vea [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="f4a58-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4a58-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="f4a58-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f4a58-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="f4a58-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f4a58-110">Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="f4a58-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="f4a58-111">Para ocultar un menú de nivel superior y sus elementos de submenú</span><span class="sxs-lookup"><span data-stu-id="f4a58-111">To hide a top-level menu and its submenu items</span></span>  
  
1. <span data-ttu-id="f4a58-112">Seleccione el elemento de menú de nivel superior y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="f4a58-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="f4a58-113">Cuando se oculta el elemento de menú de nivel superior, también se ocultan todos los elementos de menú dentro de ese menú.</span><span class="sxs-lookup"><span data-stu-id="f4a58-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="f4a58-114">Si hace clic en algún lugar que no sea en el <xref:System.Windows.Forms.MenuStrip> después de establecer <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, el elemento de menú de nivel superior completa y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto del tiempo de ejecución de la acción.</span><span class="sxs-lookup"><span data-stu-id="f4a58-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="f4a58-115">Para mostrar el elemento de menú de nivel superior en tiempo de diseño, haga clic en el <xref:System.Windows.Forms.MenuStrip> en el **Bandeja de componentes**, en **esquema del documento**, o en la parte superior de la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="f4a58-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f4a58-116">Rara vez se oculte un menú todo excepto los menús secundarios MDI (interfaz) de varios documentos en un escenario de combinación.</span><span class="sxs-lookup"><span data-stu-id="f4a58-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="f4a58-117">Para ocultar un elemento de submenú</span><span class="sxs-lookup"><span data-stu-id="f4a58-117">To hide a submenu item</span></span>  
  
1. <span data-ttu-id="f4a58-118">Seleccione el elemento de submenú y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="f4a58-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="f4a58-119">Cuando se oculta un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que se puede seleccionar fácilmente para seguir trabajando.</span><span class="sxs-lookup"><span data-stu-id="f4a58-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="f4a58-120">En realidad se ocultará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f4a58-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4a58-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="f4a58-121">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="f4a58-122">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="f4a58-122">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="f4a58-123">Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="f4a58-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
