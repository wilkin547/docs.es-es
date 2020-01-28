---
title: Información general sobre el componente MainMenu
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
# <a name="mainmenu-component-overview-windows-forms"></a>Información general sobre MainMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
> Aunque <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan y agregan funcionalidad a los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores, <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
 El componente <xref:System.Windows.Forms.MainMenu> de Windows Forms muestra un menú en tiempo de ejecución. Todos los submenús del menú principal y los elementos individuales son objetos <xref:System.Windows.Forms.MenuItem>.  
  
## <a name="key-properties"></a>Propiedades clave  
 Un elemento de menú se puede designar como elemento predeterminado estableciendo la propiedad <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> en `true`. El elemento predeterminado aparece en negrita al hacer clic en el menú. La propiedad <xref:System.Windows.Forms.MenuItem.Checked%2A> del elemento de menú es `true` o `false`y indica si el elemento de menú está seleccionado. La propiedad <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> del elemento de menú personaliza la apariencia del elemento seleccionado: si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> está establecido en `true`, aparece un botón de radio junto al elemento; Si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en `false`, aparecerá una marca de verificación junto al elemento.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.MainMenu>
- <xref:System.Windows.Forms.Menu>
- <xref:System.Windows.Forms.MenuItem>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- [Información general sobre el control MenuStrip](menustrip-control-overview-windows-forms.md)
