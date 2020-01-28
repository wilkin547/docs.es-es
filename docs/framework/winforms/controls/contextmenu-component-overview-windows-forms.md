---
title: Información general sobre el componente ContextMenu
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 83740221894941d09d1014585513043851a518e5
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746201"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="3fd64-102">Información general sobre ContextMenu (Componente, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="3fd64-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="3fd64-103">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="3fd64-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="3fd64-104">Con el componente de <xref:System.Windows.Forms.ContextMenu> de Windows Forms, puede proporcionar a los usuarios un menú contextual fácilmente accesible de los comandos usados con frecuencia que están asociados al objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="3fd64-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="3fd64-105">Los elementos de un menú contextual suelen ser un subconjunto de los elementos de los menús principales que aparecen en otro lugar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3fd64-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="3fd64-106">Normalmente, un usuario puede tener acceso a un menú contextual si hace clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="3fd64-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="3fd64-107">En Windows Forms, los menús contextuales se asocian a los controles.</span><span class="sxs-lookup"><span data-stu-id="3fd64-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="3fd64-108">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="3fd64-108">Key Properties</span></span>  
 <span data-ttu-id="3fd64-109">Puede asociar un menú contextual a un control estableciendo la propiedad <xref:System.Windows.Forms.Control.ContextMenu%2A> del control en el componente <xref:System.Windows.Forms.ContextMenu>.</span><span class="sxs-lookup"><span data-stu-id="3fd64-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="3fd64-110">Un solo menú contextual se puede asociar a varios controles, pero cada control solo puede tener un menú contextual.</span><span class="sxs-lookup"><span data-stu-id="3fd64-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="3fd64-111">La propiedad clave del componente <xref:System.Windows.Forms.ContextMenu> es la propiedad <xref:System.Windows.Forms.Menu.MenuItems%2A>.</span><span class="sxs-lookup"><span data-stu-id="3fd64-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="3fd64-112">Puede agregar elementos de menú mediante programación creando <xref:System.Windows.Forms.MenuItem> objetos y agregándolos al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="3fd64-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="3fd64-113">Dado que los elementos de un menú contextual normalmente se dibujan desde otros menús, los elementos se agregan a menudo a un menú contextual copiándolos.</span><span class="sxs-lookup"><span data-stu-id="3fd64-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fd64-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3fd64-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
