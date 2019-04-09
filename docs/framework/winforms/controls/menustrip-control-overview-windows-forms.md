---
title: Información general sobre el control MenuStrip (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- MenuStrip
helpviewer_keywords:
- MenuStrip control [Windows Forms], about MenuStrip control
- menus [Windows Forms], creating
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
ms.openlocfilehash: 7cd761697a09205294727043efc6cf73816803ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59144357"
---
# <a name="menustrip-control-overview-windows-forms"></a>Información general sobre el control MenuStrip (formularios Windows Forms)
Los menús exponen la funcionalidad a los usuarios manteniendo los comandos que se agrupan por un tema común.  
  
 El <xref:System.Windows.Forms.MenuStrip> control es una novedad de esta versión de Visual Studio y .NET Framework. Con el control, puede crear fácilmente menús como los que se encuentran en Microsoft Office.  
  
 El <xref:System.Windows.Forms.MenuStrip> control es compatible con la interfaz de múltiples documentos (MDI) y combinación de menús, información sobre herramientas y desbordamiento. Puede mejorar la facilidad de uso y la legibilidad de los menús mediante la adición de barras separadoras, teclas de método abreviado, marcas de verificación, imágenes y las claves de acceso.  
  
 El <xref:System.Windows.Forms.MenuStrip> control reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.MainMenu> controlar; sin embargo, el <xref:System.Windows.Forms.MainMenu> control se conserva para compatibilidad con versiones anteriores y uso futuro, si elige.  
  
## <a name="ways-to-use-the-menustrip-control"></a>Formas de usar el Control MenuStrip  
 Use el <xref:System.Windows.Forms.MenuStrip> controlar para:  
  
-   Cree fácilmente personalizada, comúnmente empleados menús que admiten usuario interfaz y diseño de características avanzadas, como texto y ordenación de la imagen y alineación, operaciones de arrastrar y colocar, MDI, desbordamiento y modos alternativos de obtener acceso a los comandos de menú.  
  
-   Admite el comportamiento del sistema operativo y el aspecto típico.  
  
-   Controlar los eventos de forma coherente para todos los contenedores y los elementos contenidos, de la misma manera controlan los eventos de otros controles.  
  
 La siguiente tabla muestra algunas propiedades especialmente importantes de <xref:System.Windows.Forms.MenuStrip> y sus clases asociadas.  
  
|Propiedad|Descripción|  
|--------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Obtiene o establece el <xref:System.Windows.Forms.ToolStripMenuItem> que se usa para mostrar una lista de formularios MDI secundarios.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=nameWithType>|Obtiene o establece cómo se combinan los menús secundarios con los menús primarios en las aplicaciones MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=nameWithType>|Obtiene o establece la posición de un elemento combinado dentro de un menú en las aplicaciones MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=nameWithType>|Obtiene o establece un valor que indica si el formulario es un contenedor para formularios MDI secundarios.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Obtiene o establece un valor que indica si se muestra información sobre herramientas para el <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Obtiene o establece un valor que indica si <xref:System.Windows.Forms.MenuStrip> admite la funcionalidad del desbordamiento.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Obtiene o establece las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Obtiene o establece un valor que indica si las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem> se muestran al lado de <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 La siguiente tabla muestra las importantes <xref:System.Windows.Forms.MenuStrip> clases complementarias.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Representa una opción seleccionable mostrada en un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Representa un menú contextual.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Representa un control que permite al usuario seleccionar un único elemento de una lista que se muestra cuando el usuario hace clic en un <xref:System.Windows.Forms.ToolStripDropDownButton> o un elemento de menú de nivel superior.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Proporciona funcionalidad básica para los controles derivan de <xref:System.Windows.Forms.ToolStripItem> que mostrar los elementos de lista desplegable al hacer clic en.|  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
