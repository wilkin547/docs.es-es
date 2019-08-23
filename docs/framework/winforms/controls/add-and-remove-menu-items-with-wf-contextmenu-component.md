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
ms.openlocfilehash: 5d1862b1fc1398f0f8c2217b51c4efb93db639af
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957017"
---
# <a name="how-to-add-and-remove-menu-items-with-the-windows-forms-contextmenu-component"></a>Procedimiento para agregar y quitar elementos de menú con el componente ContextMenu de formularios Windows Forms
Explica cómo agregar y quitar elementos de menú contextual en Windows Forms.  
  
 El componente <xref:System.Windows.Forms.ContextMenu> Windows Forms proporciona un menú de comandos usados con frecuencia que son relevantes para el objeto seleccionado. Puede agregar elementos al menú contextual agregando <xref:System.Windows.Forms.MenuItem> objetos a la <xref:System.Windows.Forms.Menu.MenuItems%2A> colección.  
  
 Puede quitar elementos de un menú contextual de forma permanente; sin embargo, en tiempo de ejecución puede ser más adecuado ocultar o deshabilitar los elementos en su lugar.  
  
> [!IMPORTANT]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> reemplazan y agregan funcionalidad a los controles y de versiones anteriores, y se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. <xref:System.Windows.Forms.ContextMenuStrip>  
  
### <a name="to-remove-items-from-a-shortcut-menu"></a>Para quitar elementos de un menú contextual  
  
1. Use el <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> método <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> <xref:System.Windows.Forms.Menu.MenuItems%2A> o<xref:System.Windows.Forms.ContextMenu> de la colección del componente para quitar un elemento de menú determinado.  
  
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
  
     -o bien-  
  
2. Use el `Clear` método de la `MenuItems` colección del <xref:System.Windows.Forms.ContextMenu> componente para quitar todos los elementos del menú.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ContextMenu>
- [ContextMenu (componente)](contextmenu-component-windows-forms.md)
- [Información general sobre ContextMenu](contextmenu-component-overview-windows-forms.md)
