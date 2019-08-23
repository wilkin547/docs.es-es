---
title: Información general sobre MainMenu (Componente, formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuItem
- MainMenu
helpviewer_keywords:
- MainMenu control [Windows Forms], about MainMenu control
- menus
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
ms.openlocfilehash: fe46683faee13bad951d5a7185aad8a687c290ef
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952134"
---
# <a name="mainmenu-component-overview-windows-forms"></a>Información general sobre MainMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.MainMenu> <xref:System.Windows.Forms.ContextMenu> reemplazan y agregan funcionalidad a los controles y de versiones anteriores, y se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide. <xref:System.Windows.Forms.ContextMenuStrip>  
  
 El componente <xref:System.Windows.Forms.MainMenu> Windows Forms muestra un menú en tiempo de ejecución. Todos los submenús del menú principal y los elementos individuales <xref:System.Windows.Forms.MenuItem> son objetos.  
  
## <a name="key-properties"></a>Propiedades clave  
 Un elemento de menú se puede designar como elemento predeterminado estableciendo la <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> propiedad en `true`. El elemento predeterminado aparece en negrita al hacer clic en el menú. La propiedad del elemento <xref:System.Windows.Forms.MenuItem.Checked%2A> de menú `true` es o `false`y indica si el elemento de menú está seleccionado. La propiedad <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> del elemento de menú personaliza la apariencia del elemento seleccionado: Si `true` <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en, aparece un botón de radio junto al elemento; si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en `false`, aparece una marca de verificación junto al elemento.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
