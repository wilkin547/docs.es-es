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
ms.openlocfilehash: 7da0522dae00608ead356484a31d219a67ec4ba9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54545678"
---
# <a name="contextmenu-component-overview-windows-forms"></a>Información general sobre ContextMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a la <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> controles de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan para compatibilidad con versiones anteriores y uso futuro, si elige.  
  
 Con los formularios de Windows <xref:System.Windows.Forms.ContextMenu> componente, puede proporcionar a los usuarios con un menú contextual de comandos usados con frecuencia que están asociados con el objeto seleccionado. Con frecuencia, los elementos de un menú contextual son un subconjunto de los elementos de menús principales que aparecen en otra parte de la aplicación. Normalmente, un usuario puede acceder a un menú contextual haciendo clic con el mouse. En Windows Forms, los menús contextuales se asocian con controles.  
  
## <a name="key-properties"></a>Propiedades clave  
 Puede asociar un menú contextual a un control mediante el establecimiento del control <xref:System.Windows.Forms.Control.ContextMenu%2A> propiedad a la <xref:System.Windows.Forms.ContextMenu> componente. Un menú contextual solo se puede asociar con varios controles, pero cada control puede tener solo un menú contextual.  
  
 La propiedad de clave de la <xref:System.Windows.Forms.ContextMenu> componente es el <xref:System.Windows.Forms.Menu.MenuItems%2A> propiedad. Puede agregar elementos de menú mediante la creación mediante programación <xref:System.Windows.Forms.MenuItem> objetos y agregarlos a la <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual. Dado que normalmente se dibujan los elementos de un menú contextual de otros menús, con más frecuencia agregará elementos a un menú contextual mediante su copia.  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ContextMenu>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
