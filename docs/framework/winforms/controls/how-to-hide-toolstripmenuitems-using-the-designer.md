---
title: "Cómo: Ocultar ToolStripMenuItems mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ToolStripMenuItems [Windows Forms], hiding menu items in designer
- MenuStrip control [Windows Forms], hiding menu items in designer
- menu items [Windows Forms], hiding
ms.assetid: 8f1b057e-3d8a-4f11-88df-935f7b29a836
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 5ac840953e34ac6726bb1c240c062d0f17b8cb71
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-hide-toolstripmenuitems-using-the-designer"></a><span data-ttu-id="ac02b-102">Cómo: Ocultar ToolStripMenuItems mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="ac02b-102">How to: Hide ToolStripMenuItems Using the Designer</span></span>
<span data-ttu-id="ac02b-103">Ocultar elementos de menú es una manera de controlar la interfaz de usuario (UI) de la aplicación y restringir los comandos de usuario.</span><span class="sxs-lookup"><span data-stu-id="ac02b-103">Hiding menu items is a way to control the user interface (UI) of your application and restrict user commands.</span></span> <span data-ttu-id="ac02b-104">A menudo, deseará ocultar un menú completo cuando todos los elementos de menú en el no están disponibles.</span><span class="sxs-lookup"><span data-stu-id="ac02b-104">Often, you will want to hide an entire menu when all of the menu items on it are unavailable.</span></span> <span data-ttu-id="ac02b-105">Esto supone menos distracciones para el usuario.</span><span class="sxs-lookup"><span data-stu-id="ac02b-105">This presents fewer distractions for the user.</span></span> <span data-ttu-id="ac02b-106">Además, puede ocultar y deshabilitar el menú o el elemento de menú, como si sólo se oculta no impide que el usuario obtener acceso a un comando de menú mediante una tecla de método abreviado.</span><span class="sxs-lookup"><span data-stu-id="ac02b-106">Furthermore, you might want to both hide and disable the menu or menu item, as hiding alone does not prevent the user from accessing a menu command by using a shortcut key.</span></span> <span data-ttu-id="ac02b-107">Para obtener más información acerca de cómo deshabilitar elementos de menú, vea [Cómo: Deshabilitar ToolStripMenuItems mediante el diseñador](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span><span class="sxs-lookup"><span data-stu-id="ac02b-107">For more information on disabling menu items, see [How to: Disable ToolStripMenuItems Using the Designer](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac02b-108">Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.</span><span class="sxs-lookup"><span data-stu-id="ac02b-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ac02b-109">Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** .</span><span class="sxs-lookup"><span data-stu-id="ac02b-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ac02b-110">Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="ac02b-110">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-hide-a-top-level-menu-and-its-submenu-items"></a><span data-ttu-id="ac02b-111">Para ocultar un menú de nivel superior y sus elementos de submenú</span><span class="sxs-lookup"><span data-stu-id="ac02b-111">To hide a top-level menu and its submenu items</span></span>  
  
1.  <span data-ttu-id="ac02b-112">Seleccione el elemento de menú de nivel superior y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> o <xref:System.Windows.Forms.ToolStripItem.Available%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="ac02b-112">Select the top-level menu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> or <xref:System.Windows.Forms.ToolStripItem.Available%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="ac02b-113">Cuando se oculta el elemento de menú de nivel superior, también se ocultan todos los elementos de menú dentro de ese menú.</span><span class="sxs-lookup"><span data-stu-id="ac02b-113">When you hide the top-level menu item, all menu items within that menu are also hidden.</span></span> <span data-ttu-id="ac02b-114">Si hace clic en otra parte que no sea de en el <xref:System.Windows.Forms.MenuStrip> después de establecer <xref:System.Windows.Forms.ToolStripItem.Visible%2A> a `false`, el elemento de menú de nivel superior completa y sus elementos de submenú desaparecen del formulario, lo que muestra el efecto de tiempo de ejecución de la acción.</span><span class="sxs-lookup"><span data-stu-id="ac02b-114">If you click somewhere other than on the <xref:System.Windows.Forms.MenuStrip> after setting <xref:System.Windows.Forms.ToolStripItem.Visible%2A> to `false`, the entire top-level menu item and its submenu items disappear from your form, thus showing you the run-time effect of your action.</span></span> <span data-ttu-id="ac02b-115">Para mostrar el elemento de menú de nivel superior en tiempo de diseño, haga clic en el <xref:System.Windows.Forms.MenuStrip> en el **Bandeja de componentes**, en **esquema del documento**, o en la parte superior de la cuadrícula de propiedades.</span><span class="sxs-lookup"><span data-stu-id="ac02b-115">To display the hidden top-level menu item at design time, click on the <xref:System.Windows.Forms.MenuStrip> in the **Component Tray**, in **Document Outline**, or at the top of the property grid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ac02b-116">Raramente ocultará un menú completo salvo para los menús secundarios MDI (interfaz) de varios documentos en un escenario de combinación.</span><span class="sxs-lookup"><span data-stu-id="ac02b-116">You will rarely hide an entire menu except for multiple document interface (MDI) child menus in a merging scenario.</span></span>  
  
### <a name="to-hide-a-submenu-item"></a><span data-ttu-id="ac02b-117">Para ocultar un elemento de submenú</span><span class="sxs-lookup"><span data-stu-id="ac02b-117">To hide a submenu item</span></span>  
  
1.  <span data-ttu-id="ac02b-118">Seleccione el elemento de submenú y establezca su <xref:System.Windows.Forms.ToolStripItem.Visible%2A> propiedad `false`.</span><span class="sxs-lookup"><span data-stu-id="ac02b-118">Select the submenu item and set its <xref:System.Windows.Forms.ToolStripItem.Visible%2A> property to `false`.</span></span>  
  
     <span data-ttu-id="ac02b-119">Cuando se oculta un elemento de submenú, permanece visible en el formulario en tiempo de diseño para que se puedan seleccionar fácilmente para seguir trabajando.</span><span class="sxs-lookup"><span data-stu-id="ac02b-119">When you hide a submenu item, it remains visible on your form at design time so that you can easily select it for further work.</span></span> <span data-ttu-id="ac02b-120">En realidad se ocultará en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ac02b-120">It will actually be hidden at run time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac02b-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac02b-121">See Also</span></span>  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>  
 <xref:System.Windows.Forms.ToolStripItem.Available%2A>  
 <xref:System.Windows.Forms.ToolStripMenuItem.Overflow%2A>  
 [<span data-ttu-id="ac02b-122">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="ac02b-122">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)  
 [<span data-ttu-id="ac02b-123">Deshabilitar ToolStripMenuItems mediante el Diseñador</span><span class="sxs-lookup"><span data-stu-id="ac02b-123">How to: Disable ToolStripMenuItems Using the Designer</span></span>](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems-using-the-designer.md)
