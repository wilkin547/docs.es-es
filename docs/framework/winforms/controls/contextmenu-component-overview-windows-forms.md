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
ms.openlocfilehash: 5d548815533e8f9bb37ad00129a5ae526612ea08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="contextmenu-component-overview-windows-forms"></a>Información general sobre ContextMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazar y agregar funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si elige.  
  
 Con los formularios de Windows <xref:System.Windows.Forms.ContextMenu> componente, puede proporcionar a los usuarios con un menú contextual fácilmente accesible de comandos de uso frecuente que están asociados con el objeto seleccionado. Los elementos de un menú contextual con frecuencia son un subconjunto de los elementos de los menús principales que aparecen en otros lugares en la aplicación. Un usuario normalmente puede tener acceso a un menú contextual con el botón secundario del mouse. En Windows Forms, los menús contextuales están asociados a controles.  
  
## <a name="key-properties"></a>Propiedades clave  
 Puede asociar un menú contextual a un control mediante el establecimiento del control <xref:System.Windows.Forms.Control.ContextMenu%2A> propiedad a la <xref:System.Windows.Forms.ContextMenu> componente. Un menú contextual solo puede asociarse a varios controles, pero cada control puede tener solo un menú contextual.  
  
 La propiedad clave de la <xref:System.Windows.Forms.ContextMenu> componente es el <xref:System.Windows.Forms.Menu.MenuItems%2A> propiedad. Puede agregar elementos de menú creando mediante programación <xref:System.Windows.Forms.MenuItem> objetos y agregándolos a la <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual. Dado que los elementos de un menú contextual se suelen tomar de otros menús, con más frecuencia agregará elementos a un menú contextual, cópielas.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ContextMenu>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>
