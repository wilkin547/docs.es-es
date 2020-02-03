---
title: Información general sobre MainMenu
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: 8bc35de239429214d6b493b343d1dd6c898f4d37
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745117"
---
# <a name="mainmenu-component-overview-windows-forms"></a><span data-ttu-id="102ba-102">Información general sobre MainMenu (Componente, formularios Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="102ba-102">MainMenu Component Overview (Windows Forms)</span></span>
> [!IMPORTANT]
> <span data-ttu-id="102ba-103">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="102ba-103">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
 <span data-ttu-id="102ba-104">El componente <xref:System.Windows.Forms.MainMenu> de Windows Forms muestra un menú en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="102ba-104">The Windows Forms <xref:System.Windows.Forms.MainMenu> component displays a menu at run time.</span></span> <span data-ttu-id="102ba-105">Todos los submenús del menú principal y los elementos individuales son objetos <xref:System.Windows.Forms.MenuItem>.</span><span class="sxs-lookup"><span data-stu-id="102ba-105">All submenus of the main menu and individual items are <xref:System.Windows.Forms.MenuItem> objects.</span></span>  
  
## <a name="key-properties"></a><span data-ttu-id="102ba-106">Propiedades clave</span><span class="sxs-lookup"><span data-stu-id="102ba-106">Key Properties</span></span>  
 <span data-ttu-id="102ba-107">Un elemento de menú se puede designar como elemento predeterminado estableciendo la propiedad <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> en `true`.</span><span class="sxs-lookup"><span data-stu-id="102ba-107">A menu item can be designated as the default item by setting the <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> property to `true`.</span></span> <span data-ttu-id="102ba-108">El elemento predeterminado aparece en negrita al hacer clic en el menú.</span><span class="sxs-lookup"><span data-stu-id="102ba-108">The default item appears in bold text when the menu is clicked.</span></span> <span data-ttu-id="102ba-109">La propiedad <xref:System.Windows.Forms.MenuItem.Checked%2A> del elemento de menú es `true` o `false`y indica si el elemento de menú está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="102ba-109">The menu item's <xref:System.Windows.Forms.MenuItem.Checked%2A> property is either `true` or `false`, and indicates whether the menu item is selected.</span></span> <span data-ttu-id="102ba-110">La propiedad <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> del elemento de menú personaliza la apariencia del elemento seleccionado: si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> está establecido en `true`, aparece un botón de radio junto al elemento; Si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en `false`, aparecerá una marca de verificación junto al elemento.</span><span class="sxs-lookup"><span data-stu-id="102ba-110">The menu item's <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> property customizes the appearance of the selected item: if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `true`, a radio button appears next to the item; if <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> is set to `false`, a check mark appears next to the item.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102ba-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="102ba-111">See also</span></span>

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [<span data-ttu-id="102ba-112">Información general sobre el control MenuStrip</span><span class="sxs-lookup"><span data-stu-id="102ba-112">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
