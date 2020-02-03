---
title: Información general sobre el control MenuStrip
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: a536d13cb7be3f4e4e4a085e1a4da1b0899b3a0c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734466"
---
# <a name="menustrip-control-overview-windows-forms"></a>Información general sobre el control MenuStrip (Windows Forms)
Los menús exponen la funcionalidad a los usuarios manteniendo los comandos agrupados por un tema común.  
  
 El control <xref:System.Windows.Forms.MenuStrip> se presentó en la versión 2,0 del .NET Framework. Con el control de <xref:System.Windows.Forms.MenuStrip>, puede crear fácilmente menús como los que se encuentran en Microsoft Office.  
  
 El control <xref:System.Windows.Forms.MenuStrip> es compatible con la interfaz de múltiples documentos (MDI) y la combinación de menús, la información sobre herramientas y el desbordamiento. Puede mejorar la facilidad de uso y la legibilidad de los menús agregando teclas de acceso, teclas de método abreviado, marcas de verificación, imágenes y barras separadoras.  
  
 El control <xref:System.Windows.Forms.MenuStrip> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.MainMenu>. sin embargo, el control de <xref:System.Windows.Forms.MainMenu> se conserva por compatibilidad con versiones anteriores y uso futuro, si así lo decide.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Formas de usar el control MenuStrip  
 Utilice el control <xref:System.Windows.Forms.MenuStrip> para:  
  
- Cree menús fáciles de personalizar y de uso frecuente que admitan características avanzadas de la interfaz de usuario y el diseño, como el orden y la alineación de texto e imagen, operaciones de arrastrar y colocar, MDI, desbordamiento y modos alternativos de acceso a comandos de menú.  
  
- Admitir la apariencia y el comportamiento típicos del sistema operativo.  
  
- Controle los eventos de forma coherente para todos los contenedores y elementos contenidos, de la misma manera que controla los eventos de otros controles.  
  
 En la tabla siguiente se muestran algunas propiedades especialmente importantes de <xref:System.Windows.Forms.MenuStrip> y las clases asociadas.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Obtiene o establece el <xref:System.Windows.Forms.ToolStripMenuItem> que se usa para mostrar una lista de formularios MDI secundarios.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Obtiene o establece cómo se combinan los menús secundarios con los menús primarios en las aplicaciones MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Obtiene o establece la posición de un elemento combinado en un menú de aplicaciones MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Obtiene o establece un valor que indica si el formulario es un contenedor de formularios MDI secundarios.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Obtiene o establece un valor que indica si se muestra información sobre herramientas para el <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Obtiene o establece un valor que indica si <xref:System.Windows.Forms.MenuStrip> admite la funcionalidad del desbordamiento.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Obtiene o establece las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Obtiene o establece un valor que indica si las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem> se muestran al lado de <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 En la tabla siguiente se muestran las clases de complementos de <xref:System.Windows.Forms.MenuStrip> importantes.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Representa una opción seleccionable mostrada en un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Representa un menú contextual.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Representa un control que permite al usuario seleccionar un solo elemento de una lista que se muestra cuando el usuario hace clic en un <xref:System.Windows.Forms.ToolStripDropDownButton> o en un elemento de menú de nivel superior.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Proporciona la funcionalidad básica para los controles derivados de <xref:System.Windows.Forms.ToolStripItem> que muestran los elementos desplegables cuando se hace clic en ellos.|  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
