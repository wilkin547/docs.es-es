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
# <a name="contextmenu-component-overview-windows-forms"></a>Información general sobre ContextMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> reemplazan y agregan funcionalidad a los controles y de versiones anteriores, y se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. <xref:System.Windows.Forms.ContextMenuStrip>  
  
 Con el componente <xref:System.Windows.Forms.ContextMenu> de Windows Forms, puede proporcionar a los usuarios un menú contextual fácilmente accesible de los comandos usados con frecuencia que están asociados al objeto seleccionado. Los elementos de un menú contextual suelen ser un subconjunto de los elementos de los menús principales que aparecen en otro lugar de la aplicación. Normalmente, un usuario puede tener acceso a un menú contextual si hace clic con el botón secundario del mouse. En Windows Forms, los menús contextuales se asocian a los controles.  
  
## <a name="key-properties"></a>Propiedades clave  
 Puede asociar un menú contextual a un control estableciendo la propiedad del <xref:System.Windows.Forms.Control.ContextMenu%2A> control en el <xref:System.Windows.Forms.ContextMenu> componente. Un solo menú contextual se puede asociar a varios controles, pero cada control solo puede tener un menú contextual.  
  
 La propiedad clave del <xref:System.Windows.Forms.ContextMenu> componente es la <xref:System.Windows.Forms.Menu.MenuItems%2A> propiedad. Puede agregar elementos <xref:System.Windows.Forms.Menu.MenuItemCollection> de menú mediante programación para crear <xref:System.Windows.Forms.MenuItem> objetos y agregarlos al del menú contextual. Dado que los elementos de un menú contextual normalmente se dibujan desde otros menús, los elementos se agregan a menudo a un menú contextual copiándolos.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
