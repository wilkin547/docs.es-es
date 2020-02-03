---
title: Agregar y quitar elementos de menú con el componente ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- context menus [Windows Forms], removing items
- ContextMenu component [Windows Forms], adding items
- shortcut menus [Windows Forms], removing items
- shortcut menus [Windows Forms], examples
- context menus [Windows Forms], adding items
- shortcut menus [Windows Forms], adding items
- ContextMenu component [Windows Forms], removing items
- context menus [Windows Forms], examples
- examples [Windows Forms], context menus
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
ms.openlocfilehash: 989ab6d47ec761930a32f542b5fa1136e831f73d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746272"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="d8740-102">Cómo: Agregar y quitar elementos de menú con el componente ContextMenu de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d8740-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="d8740-103">Explica cómo agregar y quitar elementos de menú contextual en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d8740-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="d8740-104">El componente <xref:System.Windows.Forms.ContextMenu> de Windows Forms proporciona un menú de comandos usados con frecuencia que son relevantes para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="d8740-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="d8740-105">Puede agregar elementos al menú contextual agregando <xref:System.Windows.Forms.MenuItem> objetos a la colección <xref:System.Windows.Forms.Menu.MenuItems%2A>.</span><span class="sxs-lookup"><span data-stu-id="d8740-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="d8740-106">Puede quitar elementos de un menú contextual de forma permanente; sin embargo, en tiempo de ejecución puede ser más adecuado ocultar o deshabilitar los elementos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d8740-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d8740-107">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.</span><span class="sxs-lookup"><span data-stu-id="d8740-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="d8740-108">Para quitar elementos de un menú contextual</span><span class="sxs-lookup"><span data-stu-id="d8740-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="d8740-109">Use el método <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> de la colección <xref:System.Windows.Forms.Menu.MenuItems%2A> del componente <xref:System.Windows.Forms.ContextMenu> para quitar un elemento de menú determinado.</span><span class="sxs-lookup"><span data-stu-id="d8740-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     <span data-ttu-id="d8740-110">O bien</span><span class="sxs-lookup"><span data-stu-id="d8740-110">-or-</span></span>  
  
2. <span data-ttu-id="d8740-111">Utilice el método `Clear` de la colección `MenuItems` del componente <xref:System.Windows.Forms.ContextMenu> para quitar todos los elementos del menú.</span><span class="sxs-lookup"><span data-stu-id="d8740-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="d8740-112">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d8740-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="d8740-113">ContextMenu (componente)</span><span class="sxs-lookup"><span data-stu-id="d8740-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="d8740-114">Información general sobre ContextMenu</span><span class="sxs-lookup"><span data-stu-id="d8740-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
