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
ms.openlocfilehash: 2acbcc9197a630a993471c22e572a4f3ed682c64
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956057"
---
# <a name="contextmenu-component-overview-windows-forms"></a><span data-ttu-id="09c48-102">Información general sobre ContextMenu (Componente, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="09c48-102">ContextMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
>  <span data-ttu-id="09c48-103">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="09c48-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="09c48-104">Con los formularios de Windows <xref:System.Windows.Forms.ContextMenu> componente, puede proporcionar a los usuarios con un menú contextual de comandos usados con frecuencia que están asociados con el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="09c48-104">With the Windows Forms <xref:System.Windows.Forms.ContextMenu> component, you can provide users with an easily accessible shortcut menu of frequently used commands that are associated with the selected object.</span></span> <span data-ttu-id="09c48-105">Con frecuencia, los elementos de un menú contextual son un subconjunto de los elementos de menús principales que aparecen en otra parte de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09c48-105">The items in a shortcut menu are frequently a subset of the items from main menus that appear elsewhere in the application.</span></span> <span data-ttu-id="09c48-106">Normalmente, un usuario puede acceder a un menú contextual haciendo clic con el mouse.</span><span class="sxs-lookup"><span data-stu-id="09c48-106">A user can typically access a shortcut menu by right-clicking the mouse.</span></span> <span data-ttu-id="09c48-107">En Windows Forms, los menús contextuales se asocian con controles.</span><span class="sxs-lookup"><span data-stu-id="09c48-107">On Windows Forms, shortcut menus are associated with controls.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="09c48-108">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="09c48-108">Key Properties</span></span>  
 <span data-ttu-id="09c48-109">Puede asociar un menú contextual a un control mediante el establecimiento del control <xref:System.Windows.Forms.Control.ContextMenu%2A> propiedad a la <xref:System.Windows.Forms.ContextMenu> componente.</span><span class="sxs-lookup"><span data-stu-id="09c48-109">You can associate a shortcut menu with a control by setting the control's <xref:System.Windows.Forms.Control.ContextMenu%2A> property to the <xref:System.Windows.Forms.ContextMenu> component.</span></span> <span data-ttu-id="09c48-110">Un menú contextual solo se puede asociar con varios controles, pero cada control puede tener solo un menú contextual.</span><span class="sxs-lookup"><span data-stu-id="09c48-110">A single shortcut menu can be associated with multiple controls, but each control can have only one shortcut menu.</span></span>  
  
 <span data-ttu-id="09c48-111">La propiedad de clave de la <xref:System.Windows.Forms.ContextMenu> componente es el <xref:System.Windows.Forms.Menu.MenuItems%2A> propiedad.</span><span class="sxs-lookup"><span data-stu-id="09c48-111">The key property of the <xref:System.Windows.Forms.ContextMenu> component is the <xref:System.Windows.Forms.Menu.MenuItems%2A> property.</span></span> <span data-ttu-id="09c48-112">Puede agregar elementos de menú mediante la creación mediante programación <xref:System.Windows.Forms.MenuItem> objetos y agregarlos a la <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual.</span><span class="sxs-lookup"><span data-stu-id="09c48-112">You can add menu items by programmatically creating <xref:System.Windows.Forms.MenuItem> objects and adding them to the <xref:System.Windows.Forms.Menu.MenuItemCollection> of the shortcut menu.</span></span> <span data-ttu-id="09c48-113">Dado que normalmente se dibujan los elementos de un menú contextual de otros menús, con más frecuencia agregará elementos a un menú contextual mediante su copia.</span><span class="sxs-lookup"><span data-stu-id="09c48-113">Because the items in a shortcut menu are usually drawn from other menus, you will most frequently add items to a shortcut menu by copying them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09c48-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c48-114">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
