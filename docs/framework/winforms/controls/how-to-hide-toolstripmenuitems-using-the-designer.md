---
title: Procedimiento para ocultar ToolStripMenuItems mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
ms.openlocfilehash: 0e1cd7d1868adabd4d3eec9510f6ee567ba3867d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966614"
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="42254-102">Procedimiento para ocultar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="42254-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="42254-103">Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario.</span><span class="sxs-lookup"><span data-stu-id="42254-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="42254-104">A menudo, querrá ocultar un menú completo cuando no estén disponibles todos los elementos de menú que hay en él.</span><span class="sxs-lookup"><span data-stu-id="42254-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="42254-105">Esto supone menos distracciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="42254-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="42254-106">Además, es posible que desee ocultar y deshabilitar el menú o el elemento de menú, ya que ocultar solo no impide que el usuario tenga acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="42254-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="42254-107">Para obtener más información acerca de cómo deshabilitar elementos [de menú, consulte Cómo: Deshabilite ToolStripMenuItems mediante el](how-to-disable-toolstripmenuitems-using-the-designer.md)diseñador.</span><span class="sxs-lookup"><span data-stu-id="42254-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>

## <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="42254-108">Para ocultar un menú de nivel superior y sus elementos de submenú</span><span class="sxs-lookup"><span data-stu-id="42254-108">To hide a top-level menu and its submenu items</span></span>

1. <span data-ttu-id="42254-109">Seleccione el elemento de menú de nivel superior y establezca <xref:System.Windows.Forms.ToolStripItem.Visible%2A> su <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad o `false`en.</span><span class="sxs-lookup"><span data-stu-id="42254-109">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>

     <span data-ttu-id="42254-110">Cuando se oculta el elemento de menú de nivel superior, todos los elementos de menú de ese menú también se ocultan.</span><span class="sxs-lookup"><span data-stu-id="42254-110">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="42254-111">Si hace clic en algún lugar distinto de <xref:System.Windows.Forms.MenuStrip> en el <xref:System.Windows.Forms.ToolStripItem.Visible%2A> `false`valor de después de, el elemento de menú de nivel superior completo y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto en tiempo de ejecución de la acción.</span><span class="sxs-lookup"><span data-stu-id="42254-111">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="42254-112">Para mostrar el elemento de menú de nivel superior oculto en tiempo de diseño, haga <xref:System.Windows.Forms.MenuStrip> clic en en la **bandeja de componentes**, en **esquema de documento**o en la parte superior de la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="42254-112">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>

> [!NOTE]
> <span data-ttu-id="42254-113">Rara vez ocultará un menú completo, excepto los menús secundarios de la interfaz de múltiples documentos (MDI) en un escenario de combinación.</span><span class="sxs-lookup"><span data-stu-id="42254-113">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>

## <a name="to-hide-a-submenu-item"></a><span data-ttu-id="42254-114">Para ocultar un elemento de submenú</span><span class="sxs-lookup"><span data-stu-id="42254-114">To hide a submenu item</span></span>

1. <span data-ttu-id="42254-115">Seleccione el elemento de submenú y establezca <xref:System.Windows.Forms.ToolStripItem.Visible%2A> su propiedad `false`en.</span><span class="sxs-lookup"><span data-stu-id="42254-115">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>

     <span data-ttu-id="42254-116">Al ocultar un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que pueda seleccionarlo fácilmente para seguir trabajando.</span><span class="sxs-lookup"><span data-stu-id="42254-116">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="42254-117">Realmente se ocultará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="42254-117">It will actually be hidden at run time.</span></span>

## <a name="see-also"></a><span data-ttu-id="42254-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="42254-118">See also</span></span>

- <xref:System.Windows.Forms.ToolStripItem.Visible%2A>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>
- <xref:System.Windows.Forms.ToolStripItem.Available%2A>
- <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>
- [<span data-ttu-id="42254-119">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="42254-119">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
- [<span data-ttu-id="42254-120">Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador</span><span class="sxs-lookup"><span data-stu-id="42254-120">How to: Disable ToolStripMenuItems Using the Designer</span></span>](how-to-disable-toolstripmenuitems-using-the-designer.md)
