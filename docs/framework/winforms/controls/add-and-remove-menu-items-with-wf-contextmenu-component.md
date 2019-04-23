---
title: Procedimiento para agregar y quitar elementos de menú con el componente ContextMenu de formularios Windows Forms
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
ms.openlocfilehash: cf70a5cc426b6c6075d1deb11aa2685c39a065c0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332188"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a><span data-ttu-id="1a0a2-102">Procedimiento para agregar y quitar elementos de menú con el componente ContextMenu de formularios Windows Forms</span><span class="sxs-lookup"><span data-stu-id="1a0a2-102">How to: Add and Remove Menu Items with the Windows Forms ContextMenu Component</span></span>
<span data-ttu-id="1a0a2-103">Explica cómo agregar y quitar elementos del menú contextual en Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-103">Explains how to add and remove shortcut menu items in Windows Forms.</span></span>  
  
 <span data-ttu-id="1a0a2-104">Los formularios de Windows <xref:System.Windows.Forms.ContextMenu> componente proporciona un menú de comandos usados frecuentemente que son relevantes para el objeto seleccionado.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-104">The Windows Forms <xref:System.Windows.Forms.ContextMenu> component provides a menu of frequently used commands that are relevant to the selected object.</span></span> <span data-ttu-id="1a0a2-105">Puede agregar elementos al menú contextual mediante la adición de <xref:System.Windows.Forms.MenuItem> objetos a la <xref:System.Windows.Forms.Menu.MenuItems%2A> colección.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-105">You can add items to the shortcut menu by adding <xref:System.Windows.Forms.MenuItem> objects to the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection.</span></span>  
  
 <span data-ttu-id="1a0a2-106">Se pueden quitar elementos de un menú contextual de forma permanente; Sin embargo, en tiempo de ejecución puede ser más adecuado ocultar o deshabilitar los elementos en su lugar.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-106">You can remove items from a shortcut menu permanently; however, at run time it may be more appropriate to hide or disable the items instead.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="1a0a2-107">Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-107">Although <xref:System.Windows.Forms.MenuStrip> and <xref:System.Windows.Forms.ContextMenuStrip> replace and add functionality to the <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> controls of previous versions, <xref:System.Windows.Forms.MainMenu> and <xref:System.Windows.Forms.ContextMenu> are retained for both backward compatibility and future use if you choose.</span></span>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a><span data-ttu-id="1a0a2-108">Para quitar elementos de un menú contextual</span><span class="sxs-lookup"><span data-stu-id="1a0a2-108">To remove items from a shortcut menu</span></span>  
  
1. <span data-ttu-id="1a0a2-109">Use la <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> método de la <xref:System.Windows.Forms.Menu.MenuItems%2A> colección de los <xref:System.Windows.Forms.ContextMenu> componente para quitar un elemento de menú concreto.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-109">Use the <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> or <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> method of the <xref:System.Windows.Forms.Menu.MenuItems%2A> collection of the <xref:System.Windows.Forms.ContextMenu> component to remove a particular menu item.</span></span>  
  
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
  
     <span data-ttu-id="1a0a2-110">-o bien-</span><span class="sxs-lookup"><span data-stu-id="1a0a2-110">-or-</span></span>  
  
2. <span data-ttu-id="1a0a2-111">Use la `Clear` método de la `MenuItems` colección de los <xref:System.Windows.Forms.ContextMenu> componente para quitar todos los elementos del menú.</span><span class="sxs-lookup"><span data-stu-id="1a0a2-111">Use the `Clear` method of the `MenuItems` collection of the <xref:System.Windows.Forms.ContextMenu> component to remove all items from the menu.</span></span>  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1a0a2-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="1a0a2-112">See also</span></span>

- <xref:System.Windows.Forms.ContextMenu>
- [<span data-ttu-id="1a0a2-113">ContextMenu (componente)</span><span class="sxs-lookup"><span data-stu-id="1a0a2-113">ContextMenu Component</span></span>](contextmenu-component-windows-forms.md)
- [<span data-ttu-id="1a0a2-114">Información general sobre ContextMenu</span><span class="sxs-lookup"><span data-stu-id="1a0a2-114">ContextMenu Component Overview</span></span>](contextmenu-component-overview-windows-forms.md)
