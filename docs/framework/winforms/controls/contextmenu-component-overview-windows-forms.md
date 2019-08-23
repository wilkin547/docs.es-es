---
title: Información general sobre ContextMenu (Componente, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ContextMenu
helpviewer_keywords:
- ContextMenu component [Windows Forms], about ContextMenu component
- context menus [Windows Forms], ContextMenu component
- shortcut menus [Windows Forms], ContextMenu component
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
ms.openlocfilehash: 6ae7817bc158f30fbf55b5f6228ecdf134d6657d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962180"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="e2911-102">Información general sobre ContextMenu (Componente, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="e2911-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="e2911-103">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> reemplazan y agregan funcionalidad a los controles y de versiones anteriores, y se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. <xref:System.Windows.Forms.ContextMenuStrip></span><span class="sxs-lookup"><span data-stu-id="e2911-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="e2911-104">Con el componente <xref:System.Windows.Forms.ContextMenu> de Windows Forms, puede proporcionar a los usuarios un menú contextual fácilmente accesible de los comandos usados con frecuencia que están asociados al objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="e2911-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="e2911-105">Los elementos de un menú contextual suelen ser un subconjunto de los elementos de los menús principales que aparecen en otro lugar de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="e2911-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="e2911-106">Normalmente, un usuario puede tener acceso a un menú contextual si hace clic con el botón secundario del mouse.</span><span class="sxs-lookup"><span data-stu-id="e2911-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="e2911-107">En Windows Forms, los menús contextuales se asocian a los controles.</span><span class="sxs-lookup"><span data-stu-id="e2911-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="e2911-108">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="e2911-108">Key Properties</span></span>  
 <span data-ttu-id="e2911-109">Puede asociar un menú contextual a un control estableciendo la propiedad del <xref:System.Windows.Forms.Control.ContextMenu%2A> control en el <xref:System.Windows.Forms.ContextMenu> componente.</span><span class="sxs-lookup"><span data-stu-id="e2911-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="e2911-110">Un solo menú contextual se puede asociar a varios controles, pero cada control solo puede tener un menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e2911-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="e2911-111">La propiedad clave del <xref:System.Windows.Forms.ContextMenu> componente es la <xref:System.Windows.Forms.Menu.MenuItems%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="e2911-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="e2911-112">Puede agregar elementos <xref:System.Windows.Forms.Menu.MenuItemCollection> de menú mediante programación para crear <xref:System.Windows.Forms.MenuItem> objetos y agregarlos al del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="e2911-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="e2911-113">Dado que los elementos de un menú contextual normalmente se dibujan desde otros menús, los elementos se agregan a menudo a un menú contextual copiándolos.</span><span class="sxs-lookup"><span data-stu-id="e2911-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2911-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2911-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
