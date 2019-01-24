---
title: Información sobre el control ToolStrip (formularios Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 49f544727ee82b1e36357fc4312bcd449ffc3c0c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54558753"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Información sobre el control ToolStrip (formularios Windows Forms)
Los formularios de Windows <xref:System.Windows.Forms.ToolStrip> control y sus clases asociadas proporcionan un marco común para combinar elementos de la interfaz de usuario en los menús, barras de estado y las barras de herramientas. <xref:System.Windows.Forms.ToolStrip> los controles ofrecen una experiencia de tiempo de diseño que incluye la edición y activación en contexto, el diseño personalizado y espacio compartido, que es la capacidad de las barras de herramientas para compartir el espacio horizontal o vertical.  
  
 Aunque <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control de versiones anteriores, <xref:System.Windows.Forms.ToolBar> se conserva por compatibilidad con versiones anteriores y uso futuro, si lo desea.  
  
## <a name="features-of-the-toolstrip-controls"></a>Características de los controles ToolStrip  
 Use el <xref:System.Windows.Forms.ToolStrip> controlar para:  
  
-   Presentar una interfaz de usuario común entre los contenedores.  
  
-   Cree fácilmente personalizado, normalmente por cuenta propia las barras de herramientas que admiten avanzadas características de diseño y la interfaz de usuario, como los botones de acoplamiento, espacio compartidos, con texto y las imágenes, botones desplegables y controles, botones y la reordenación de tiempo de ejecución de desbordamiento <xref:System.Windows.Forms.ToolStrip> elementos.  
  
-   Admiten el desbordamiento y reordenación de elementos en tiempo de ejecución. La característica de desbordamiento mueve los elementos a un menú desplegable cuando no hay espacio suficiente para mostrarlas en un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Compatibilidad con el aspecto típico y comportamiento del sistema operativo a través de un modelo común de representación.  
  
-   Controlar los eventos de forma coherente para todos los contenedores y los elementos contenidos, de la misma manera controlan los eventos de otros controles.  
  
-   Arrastre elementos desde una <xref:System.Windows.Forms.ToolStrip> a otra o dentro un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Crear controles de lista desplegable y un usuario de editores de tipos de interfaz con las disposiciones avanzadas en un <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Utilice la <xref:System.Windows.Forms.ToolStripControlHost> clase usar otros controles en un <xref:System.Windows.Forms.ToolStrip> y obtenga <xref:System.Windows.Forms.ToolStrip> funcionalidad para ellos.  
  
 Puede ampliar la funcionalidad y modificar la apariencia y comportamiento mediante la <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, y <xref:System.Windows.Forms.ToolStripManager> junto con el <xref:System.Windows.Forms.ToolStripRenderMode> y <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumeraciones.  
  
 El <xref:System.Windows.Forms.ToolStrip> control es altamente configurable y extensible, y proporciona muchas propiedades, métodos y eventos para personalizar la apariencia y comportamiento. A continuación se muestran algunos miembros interesantes:  
  
### <a name="important-toolstrip-members"></a>Miembros importantes de ToolStrip  
  
|nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Obtiene o establece el borde del contenedor primario un <xref:System.Windows.Forms.ToolStrip> está acoplado.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Obtiene o establece un valor que indica si la clase <xref:System.Windows.Forms.ToolStrip> controla la organización de elementos y las operaciones de arrastrar y colocar de forma privada|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Obtiene o establece un valor que indica cómo el <xref:System.Windows.Forms.ToolStrip> presenta sus elementos.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Obtiene o establece si un <xref:System.Windows.Forms.ToolStripItem> está asociado a la <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> o si puede flotar entre los dos.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Obtiene un valor que indica si un <xref:System.Windows.Forms.ToolStripItem> muestra otros elementos en una lista desplegable lista cuando la <xref:System.Windows.Forms.ToolStripItem> se hace clic en.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Obtiene el <xref:System.Windows.Forms.ToolStripItem> que es el botón de desbordamiento para un <xref:System.Windows.Forms.ToolStrip> con desbordamiento habilitado.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Obtiene o establece un <xref:System.Windows.Forms.ToolStripRenderer> utilizado para personalizar la apariencia y comportamiento (apariencia) de un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Obtiene o establece los estilos de dibujo que van a aplicarse al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Se produce cuando el <xref:System.Windows.Forms.ToolStrip.Renderer%2A> los cambios de propiedad.|  
  
 El <xref:System.Windows.Forms.ToolStrip> flexibilidad del control se logra mediante el uso de un número de clases complementarias. A continuación se muestran algunas de las más notables:  
  
### <a name="important-toolstrip-companion-classes"></a>Clases complementarias importantes de ToolStrip  
  
|nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.MainMenu> clase.|  
|<xref:System.Windows.Forms.StatusStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.StatusBar> clase.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.ContextMenu> clase.|  
|<xref:System.Windows.Forms.ToolStripItem>|Base clase abstracta que administra eventos y el diseño para todos los elementos que un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, o <xref:System.Windows.Forms.ToolStripDropDown> puede contener.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proporciona un contenedor con un panel en cada lado del formulario en el que se pueden organizar los controles de varias maneras.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Controla la funcionalidad de dibujo <xref:System.Windows.Forms.ToolStrip> objetos.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Proporciona la apariencia de estilo de Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controles <xref:System.Windows.Forms.ToolStrip> representación y compartir espacio y la combinación de <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, y <xref:System.Windows.Forms.ToolStripMenuItem> objetos.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a varios <xref:System.Windows.Forms.ToolStrip> objetos incluidos en un formulario.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a una <xref:System.Windows.Forms.ToolStrip> objeto contenido en un formulario.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hospeda otros controles que no son específicamente <xref:System.Windows.Forms.ToolStrip> controles, pero desea <xref:System.Windows.Forms.ToolStrip> funcionalidad.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Especifica si un <xref:System.Windows.Forms.ToolStripItem> es que se coloquen en el método main <xref:System.Windows.Forms.ToolStrip>, en el caso de desbordamiento <xref:System.Windows.Forms.ToolStrip>, o ninguno.|  
  
 Para obtener más información, consulte [resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) y [arquitectura del Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
