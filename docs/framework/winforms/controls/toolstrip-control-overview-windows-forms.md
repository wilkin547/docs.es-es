---
title: Información sobre el control ToolStrip
ms.date: 03/30/2017
f1_keywords:
- Toolstrip
helpviewer_keywords:
- ToolStrip control [Windows Forms], about ToolStrip control
- toolbars [Windows Forms], what's new in Windows Forms
- toolbars [Windows Forms]
- what's new [Windows Forms], toolbars
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
ms.openlocfilehash: 931a6a0ea09f9b684b793c05cb1c3db8ee8fb7c7
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741076"
---
# <a name="toolstrip-control-overview-windows-forms"></a>Información general sobre el control ToolStrip (Windows Forms)
El control <xref:System.Windows.Forms.ToolStrip> de Windows Forms y sus clases asociadas proporcionan un marco común para combinar los elementos de la interfaz de usuario en barras de herramientas, barras de estado y menús. <xref:System.Windows.Forms.ToolStrip> controles ofrecen una experiencia enriquecida en tiempo de diseño que incluye la activación y edición en contexto, el diseño personalizado y el uso compartido, que es la capacidad de las barras de herramientas de compartir el espacio horizontal o vertical.  
  
 Aunque <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control en versiones anteriores, <xref:System.Windows.Forms.ToolBar> se conserva por compatibilidad con versiones anteriores y uso futuro, si se desea.  
  
## <a name="features-of-the-toolstrip-controls"></a>Características de los controles ToolStrip  
 Utilice el control <xref:System.Windows.Forms.ToolStrip> para:  
  
- Presente una interfaz de usuario común en todos los contenedores.  
  
- Cree barras de herramientas de uso frecuente y personalizadas que admitan características avanzadas de la interfaz de usuario y el diseño, como acoplamiento, espacio compartido, botones con texto e imágenes, botones y controles desplegables, botones de desbordamiento y reordenación en tiempo de ejecución de los elementos de <xref:System.Windows.Forms.ToolStrip>.  
  
- Admite el desbordamiento y la reordenación de elementos en tiempo de ejecución. La característica de desbordamiento mueve los elementos a un menú desplegable cuando no hay espacio suficiente para mostrarlos en un <xref:System.Windows.Forms.ToolStrip>.  
  
- Admitir la apariencia y el comportamiento típicos del sistema operativo a través de un modelo de representación común.  
  
- Controle los eventos de forma coherente para todos los contenedores y elementos contenidos, de la misma manera que controla los eventos de otros controles.  
  
- Arrastre los elementos de una <xref:System.Windows.Forms.ToolStrip> a otra o dentro de un <xref:System.Windows.Forms.ToolStrip>.  
  
- Cree controles desplegables y editores de tipos de interfaz de usuario con diseños avanzados en una <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Utilice la clase <xref:System.Windows.Forms.ToolStripControlHost> para usar otros controles en una <xref:System.Windows.Forms.ToolStrip> y obtener <xref:System.Windows.Forms.ToolStrip> funcionalidad para ellos.  
  
 Puede ampliar la funcionalidad y modificar la apariencia y el comportamiento mediante el <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer>y <xref:System.Windows.Forms.ToolStripManager> junto con las enumeraciones <xref:System.Windows.Forms.ToolStripRenderMode> y <xref:System.Windows.Forms.ToolStripManagerRenderMode>.  
  
 El control <xref:System.Windows.Forms.ToolStrip> es muy configurable y extensible, y proporciona muchas propiedades, métodos y eventos para personalizar la apariencia y el comportamiento. A continuación se muestran algunos miembros destacados:  
  
### <a name="important-toolstrip-members"></a>Miembros importantes de ToolStrip  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Obtiene o establece a qué borde del contenedor primario se acopla un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Obtiene o establece un valor que indica si la clase <xref:System.Windows.Forms.ToolStrip> controla la organización de elementos y las operaciones de arrastrar y colocar de forma privada|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Obtiene o establece un valor que indica cómo el <xref:System.Windows.Forms.ToolStrip> coloca sus elementos.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Obtiene o establece un valor que indica si un <xref:System.Windows.Forms.ToolStripItem> está asociado al <xref:System.Windows.Forms.ToolStrip> o <xref:System.Windows.Forms.ToolStripOverflowButton> o puede flotar entre los dos.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Obtiene un valor que indica si un <xref:System.Windows.Forms.ToolStripItem> muestra otros elementos en una lista desplegable cuando se hace clic en el <xref:System.Windows.Forms.ToolStripItem>.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Obtiene el <xref:System.Windows.Forms.ToolStripItem> que es el botón de desbordamiento para un <xref:System.Windows.Forms.ToolStrip> con desbordamiento habilitado.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Obtiene o establece un <xref:System.Windows.Forms.ToolStripRenderer> utilizado para personalizar la apariencia y el comportamiento (apariencia y funcionamiento) de un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Obtiene o establece los estilos de dibujo que van a aplicarse al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Se produce cuando cambia la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.|  
  
 La flexibilidad del control <xref:System.Windows.Forms.ToolStrip> se logra mediante el uso de varias clases complementarias. A continuación se muestran algunas de las más destacadas:  
  
### <a name="important-toolstrip-companion-classes"></a>Clases auxiliares de ToolStrip importantes  
  
|Nombre|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Reemplaza y agrega funcionalidad a la clase <xref:System.Windows.Forms.MainMenu>.|  
|<xref:System.Windows.Forms.StatusStrip>|Reemplaza y agrega funcionalidad a la clase <xref:System.Windows.Forms.StatusBar>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Reemplaza y agrega funcionalidad a la clase <xref:System.Windows.Forms.ContextMenu>.|  
|<xref:System.Windows.Forms.ToolStripItem>|Clase base abstracta que administra los eventos y el diseño de todos los elementos que puede contener un <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost>o <xref:System.Windows.Forms.ToolStripDropDown>.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proporciona un contenedor con un panel en cada lado del formulario en el que los controles se pueden organizar de varias maneras.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Controla la funcionalidad de dibujo de los objetos <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Proporciona una apariencia de estilo Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controla la representación y el espacio compartido de <xref:System.Windows.Forms.ToolStrip>, y la combinación de objetos <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a varios objetos <xref:System.Windows.Forms.ToolStrip> contenidos en un formulario.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Especifica el estilo de dibujo (personalizado, Windows XP o Microsoft Office Professional) aplicado a un <xref:System.Windows.Forms.ToolStrip> objeto contenido en un formulario.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hospeda otros controles que no son específicamente <xref:System.Windows.Forms.ToolStrip> controles pero para los que desea <xref:System.Windows.Forms.ToolStrip> funcionalidad.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Especifica si una <xref:System.Windows.Forms.ToolStripItem> se va a disponer en el <xref:System.Windows.Forms.ToolStrip>principal, en el <xref:System.Windows.Forms.ToolStrip>de desbordamiento o en ninguna de ellas.|  
  
 Para obtener más información, vea Resumen de la [tecnología ToolStrip](toolstrip-technology-summary.md) y [arquitectura del control ToolStrip](toolstrip-control-architecture.md).  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.ToolStrip>
- <xref:System.Windows.Forms.MenuStrip>
- <xref:System.Windows.Forms.ContextMenuStrip>
- <xref:System.Windows.Forms.StatusStrip>
- <xref:System.Windows.Forms.ToolStripItem>
- <xref:System.Windows.Forms.ToolStripDropDown>
