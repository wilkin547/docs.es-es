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
ms.openlocfilehash: 3927f180e738541f2f2f8af6d03d281f6a601167
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33542056"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Información sobre el control ToolStrip (formularios Windows Forms)
Los formularios Windows Forms <xref:System.Windows.Forms.ToolStrip> control y sus clases asociadas proporcionan un marco común para combinar elementos de la interfaz de usuario en las barras de herramientas, barras de estado y menús. <xref:System.Windows.Forms.ToolStrip> controles de ofrecen una experiencia en tiempo de diseño enriquecida que incluye la edición y activación en contexto, el diseño personalizado y espacio compartido, que es la capacidad de las barras de herramientas para compartir el espacio horizontal o vertical.  
  
 Aunque <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control en versiones anteriores, <xref:System.Windows.Forms.ToolBar> se conserva para compatibilidad con versiones anteriores y uso futuro, si lo desea.  
  
## <a name="features-of-the-toolstrip-controls"></a>Características de los controles ToolStrip  
 Use el <xref:System.Windows.Forms.ToolStrip> el control al:  
  
-   Presentar una interfaz de usuario común entre los contenedores.  
  
-   Crear fácilmente personalizados, se utilizan las barras de herramientas que admiten avanzadas características de diseño y la interfaz de usuario, como botones de acoplamiento, espacio compartido, con el texto y las imágenes, botones desplegables y controles, botones y la reordenación de tiempo de ejecución de desbordamiento <xref:System.Windows.Forms.ToolStrip> elementos.  
  
-   Admiten el desbordamiento y la reordenación de elementos en tiempo de ejecución. La característica de desbordamiento mueve los elementos a un menú desplegable cuando no hay espacio suficiente para que se muestren en un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Admite la apariencia habitual y el comportamiento del sistema operativo a través de un modelo común de representación.  
  
-   Controlar los eventos de forma coherente para todos los contenedores y los elementos contenidos, de la misma manera controlar los eventos de otros controles.  
  
-   Arrastre elementos desde una <xref:System.Windows.Forms.ToolStrip> a otro o en un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Crear editores de tipos de interfaz de controles de lista desplegable y un usuario con diseños avanzados en un <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Utilice la <xref:System.Windows.Forms.ToolStripControlHost> clase se debe utilizar otros controles en un <xref:System.Windows.Forms.ToolStrip> y obtener <xref:System.Windows.Forms.ToolStrip> funcionalidad para ellos.  
  
 Puede ampliar la funcionalidad y modificar la apariencia y comportamiento mediante la <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>, y <xref:System.Windows.Forms.ToolStripManager> junto con el <xref:System.Windows.Forms.ToolStripRenderMode> y <xref:System.Windows.Forms.ToolStripManagerRenderMode> enumeraciones.  
  
 El <xref:System.Windows.Forms.ToolStrip> control es altamente configurable y extensible y proporciona muchas propiedades, métodos y eventos para personalizar la apariencia y el comportamiento. A continuación se muestran algunos de los miembros importantes:  
  
### <a name="important-toolstrip-members"></a>Miembros importantes de ToolStrip  
  
|nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Obtiene o establece el borde del contenedor primario un <xref:System.Windows.Forms.ToolStrip> está acoplado.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Obtiene o establece un valor que indica si la clase <xref:System.Windows.Forms.ToolStrip> controla la organización de elementos y las operaciones de arrastrar y colocar de forma privada|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Obtiene o establece un valor que indica cómo el <xref:System.Windows.Forms.ToolStrip> distribuye sus elementos.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Obtiene o establece si un <xref:System.Windows.Forms.ToolStripItem> está conectado a la <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> , o puede flotar entre los dos.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Obtiene un valor que indica si un <xref:System.Windows.Forms.ToolStripItem> muestra otros elementos en una lista desplegable lista cuando la <xref:System.Windows.Forms.ToolStripItem> se hace clic en.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Obtiene el <xref:System.Windows.Forms.ToolStripItem> que es el botón de desbordamiento para un <xref:System.Windows.Forms.ToolStrip> con desbordamiento habilitado.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Obtiene o establece un <xref:System.Windows.Forms.ToolStripRenderer> utiliza para personalizar la apariencia y el comportamiento (apariencia y funcionamiento) de un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Obtiene o establece los estilos de dibujo que se aplicará a la <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Se genera cuando el <xref:System.Windows.Forms.ToolStrip.Renderer%2A> cambios de propiedad.|  
  
 El <xref:System.Windows.Forms.ToolStrip> flexibilidad del control se logra mediante el uso de un número de clases complementarias. A continuación se muestran algunas de las más notables:  
  
### <a name="important-toolstrip-companion-classes"></a>Clases complementarias importantes de ToolStrip  
  
|nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.MainMenu> clase.|  
|<xref:System.Windows.Forms.StatusStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.StatusBar> clase.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Reemplaza y agrega funcionalidad a la <xref:System.Windows.Forms.ContextMenu> clase.|  
|<xref:System.Windows.Forms.ToolStripItem>|Clase base que administra eventos y el diseño para todos los elementos abstracta que un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>, o <xref:System.Windows.Forms.ToolStripDropDown> puede contener.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proporciona un contenedor con un panel en cada lado de la forma en que los controles se pueden organizar de varias maneras.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Controla la funcionalidad de dibujo <xref:System.Windows.Forms.ToolStrip> objetos.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Proporciona la apariencia de estilo de Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controles <xref:System.Windows.Forms.ToolStrip> representación y espacio compartido y la combinación de <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu>, y <xref:System.Windows.Forms.ToolStripMenuItem> objetos.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a varios <xref:System.Windows.Forms.ToolStrip> objetos incluidos en un formulario.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a uno <xref:System.Windows.Forms.ToolStrip> objeto contenido en un formulario.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hospeda otros controles que no son específicamente <xref:System.Windows.Forms.ToolStrip> controles pero desea <xref:System.Windows.Forms.ToolStrip> funcionalidad.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Especifica si un <xref:System.Windows.Forms.ToolStripItem> es que se coloquen en el método main <xref:System.Windows.Forms.ToolStrip>, en el caso de desbordamiento <xref:System.Windows.Forms.ToolStrip>, o ninguno.|  
  
 Para obtener más información, consulte [resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) y [arquitectura del Control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.ToolStrip>  
 <xref:System.Windows.Forms.MenuStrip>  
 <xref:System.Windows.Forms.ContextMenuStrip>  
 <xref:System.Windows.Forms.StatusStrip>  
 <xref:System.Windows.Forms.ToolStripItem>  
 <xref:System.Windows.Forms.ToolStripDropDown>
