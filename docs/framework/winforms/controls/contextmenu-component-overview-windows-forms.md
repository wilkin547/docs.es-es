---
title: Información general sobre ContextMenu
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
# <a name="contextmenu-component-overview-windows-forms"></a>Información general sobre ContextMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
 Con el componente de <xref:System.Windows.Forms.ContextMenu> de Windows Forms, puede proporcionar a los usuarios un menú contextual fácilmente accesible de los comandos usados con frecuencia que están asociados al objeto seleccionado. Los elementos de un menú contextual suelen ser un subconjunto de los elementos de los menús principales que aparecen en otro lugar de la aplicación. Normalmente, un usuario puede tener acceso a un menú contextual si hace clic con el botón secundario del mouse. En Windows Forms, los menús contextuales se asocian a los controles.  
  
## <a name="key-properties"></a>Propiedades clave  
 Puede asociar un menú contextual a un control estableciendo la propiedad <xref:System.Windows.Forms.Control.ContextMenu%2A> del control en el componente <xref:System.Windows.Forms.ContextMenu>. Un solo menú contextual se puede asociar a varios controles, pero cada control solo puede tener un menú contextual.  
  
 La propiedad clave del componente <xref:System.Windows.Forms.ContextMenu> es la propiedad <xref:System.Windows.Forms.Menu.MenuItems%2A>. Puede agregar elementos de menú mediante programación creando <xref:System.Windows.Forms.MenuItem> objetos y agregándolos al <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual. Dado que los elementos de un menú contextual normalmente se dibujan desde otros menús, los elementos se agregan a menudo a un menú contextual copiándolos.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
