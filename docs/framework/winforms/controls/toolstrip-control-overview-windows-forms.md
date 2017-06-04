---
title: "Informaci&#243;n sobre el control ToolStrip (formularios Windows Forms) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Toolstrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "barras de herramientas [Windows Forms]"
  - "barras de herramientas [Windows Forms], lo nuevo [Windows Forms]"
  - "ToolStrip (control) [Windows Forms], acerca del control ToolStrip"
  - "lo nuevo [Windows Forms], barras de herramientas"
ms.assetid: 81d067ed-297c-4dad-90de-1bcac15336ec
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# Informaci&#243;n sobre el control ToolStrip (formularios Windows Forms)
El control <xref:System.Windows.Forms.ToolStrip> de Windows Forms y sus clases asociadas proporcionan un marco de trabajo común para combinar elementos de interfaz de usuario en barras de herramientas, barras de estado y menús.  Los controles <xref:System.Windows.Forms.ToolStrip> ofrecen una completa experiencia en tiempo de diseño que incluye la edición y activación in situ, el diseño personalizado y de espacio compartido, que es la posibilidad que ofrecen las barras de herramientas de compartir el espacio vertical y horizontal.  
  
 Aunque <xref:System.Windows.Forms.ToolStrip> reemplaza y agrega funcionalidad al control en versiones anteriores, <xref:System.Windows.Forms.ToolBar> se conserva a efectos de compatibilidad con versiones anteriores y de uso futuro, según sea el caso.  
  
## Características de los controles ToolStrip  
 Utilice el control <xref:System.Windows.Forms.ToolStrip> para:  
  
-   Presentar una interfaz de usuario común entre todos los contenedores.  
  
-   Crear fácilmente barras de herramientas comúnmente empleadas y personalizadas compatibles con la interfaz de usuario avanzada y las características de diseño, como el acoplamiento, el espacio compartido, los botones con texto e imágenes, botones y controles desplegables, botones de desbordamiento y reorganización en tiempo de ejecución de elementos <xref:System.Windows.Forms.ToolStrip>.  
  
-   Admitir el desbordamiento y la reordenación de los elementos en tiempo de ejecución.  La característica de desbordamiento mueve los elementos a un menú desplegable cuando no hay espacio suficiente para mostrarlos en <xref:System.Windows.Forms.ToolStrip>.  
  
-   Admitir la apariencia y el comportamiento típicos del sistema operativo a través de un modelo del representación común.  
  
-   Controlar de forma coherente los eventos para todos los contenedores y los elementos contenidos, al igual que controla los eventos para otros controles.  
  
-   Arrastre los elementos de un <xref:System.Windows.Forms.ToolStrip> a otro o dentro de un <xref:System.Windows.Forms.ToolStrip>.  
  
-   Cree controles desplegables y editores de tipos de la interfaz de usuario con diseños avanzados en un <xref:System.Windows.Forms.ToolStripDropDown>.  
  
 Utilice la clase <xref:System.Windows.Forms.ToolStripControlHost> para utilizar otros controles de un <xref:System.Windows.Forms.ToolStrip> y obtener la funcionalidad <xref:System.Windows.Forms.ToolStrip> para ellos.  
  
 Puede extender la funcionalidad y modificar el aspecto y el comportamiento utilizando <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripProfessionalRenderer> y <xref:System.Windows.Forms.ToolStripManager> junto con las enumeraciones <xref:System.Windows.Forms.ToolStripRenderMode> y <xref:System.Windows.Forms.ToolStripManagerRenderMode>.  
  
 El control <xref:System.Windows.Forms.ToolStrip> es muy configurable y extensible y proporciona muchas propiedades, métodos y eventos para personalizar el aspecto y el comportamiento.  A continuación se enumeran algunos miembros que merece la pena comentar:  
  
### Miembros importantes de ToolStrip  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStrip.Dock%2A>|Obtiene o establece a qué borde del contenedor primario se acopla <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.AllowItemReorder%2A>|Obtiene o establece un valor que indica si la clase <xref:System.Windows.Forms.ToolStrip> controla la organización de elementos y la operación de arrastrar y colocar de forma privada.|  
|<xref:System.Windows.Forms.ToolStrip.LayoutStyle%2A>|Obtiene o establece un valor que indica cómo dispone <xref:System.Windows.Forms.ToolStrip> sus elementos.|  
|<xref:System.Windows.Forms.ToolStripItem.Overflow%2A>|Obtiene o establece si <xref:System.Windows.Forms.ToolStripItem> se asocia a al <xref:System.Windows.Forms.ToolStrip>, a <xref:System.Windows.Forms.ToolStripOverflowButton> o puede oscilar entre los dos.|  
|<xref:System.Windows.Forms.ToolStrip.IsDropDown%2A>|Obtiene un valor que indica si <xref:System.Windows.Forms.ToolStripItem> muestra otros elementos en una lista desplegable cuando se hace clic con <xref:System.Windows.Forms.ToolStripItem>.|  
|<xref:System.Windows.Forms.ToolStrip.OverflowButton%2A>|Obtiene el <xref:System.Windows.Forms.ToolStripItem> que es el botón de desbordamiento para un <xref:System.Windows.Forms.ToolStrip> con desbordamiento habilitado.|  
|<xref:System.Windows.Forms.ToolStrip.Renderer%2A>|Obtiene o establece un <xref:System.Windows.Forms.ToolStripRenderer> utilizado para personalizar el aspecto y el comportamiento \(apariencia y percepción\) de un <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RenderMode%2A>|Obtiene o establece los estilos de dibujo que van a aplicarse al <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStrip.RendererChanged>|Se produce cuando cambia la propiedad <xref:System.Windows.Forms.ToolStrip.Renderer%2A>.|  
  
 La flexibilidad del control <xref:System.Windows.Forms.ToolStrip> se logra a través del uso de varias clases complementarias.  A continuación se enumeran algunas de las más notables:  
  
### Clases complementarias importantes de ToolStrip  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip>|Reemplaza y agrega funcionalidad a la clase <xref:System.Windows.Forms.MainMenu>.|  
|<xref:System.Windows.Forms.StatusStrip>|Reemplaza y agrega la funcionalidad al control <xref:System.Windows.Forms.StatusBar>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Reemplaza y agrega la funcionalidad al control <xref:System.Windows.Forms.ContextMenu>.|  
|<xref:System.Windows.Forms.ToolStripItem>|Clase base abstracta que administra eventos y el diseño para todos los elementos que <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.ToolStripControlHost> o <xref:System.Windows.Forms.ToolStripDropDown> pueden contener.|  
|<xref:System.Windows.Forms.ToolStripContainer>|Proporciona un contenedor con un panel en cada lado del formulario en el que los controles se pueden organizar de distintas maneras.|  
|<xref:System.Windows.Forms.ToolStripRenderer>|Controla la funcionalidad de dibujo de los objetos <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripProfessionalRenderer>|Proporciona el aspecto del estilo de Microsoft Office.|  
|<xref:System.Windows.Forms.ToolStripManager>|Controla la representación y el espacio compartido de <xref:System.Windows.Forms.ToolStrip>, y la combinación de objetos <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ToolStripDropDownMenu> y <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripManagerRenderMode>|Especifica el estilo de dibujo \(personalizado, de Windows XP o Microsoft Office Professional\) aplicado a varios objetos <xref:System.Windows.Forms.ToolStrip> contenidos en un formulario.|  
|<xref:System.Windows.Forms.ToolStripRenderMode>|Especifica el estilo de dibujo \(personalizado, de Windows XP o Microsoft Office Professional\) aplicado a varios objetos <xref:System.Windows.Forms.ToolStrip> contenidos en un formulario.|  
|<xref:System.Windows.Forms.ToolStripControlHost>|Hospeda otros controles que no son específicamente los controles <xref:System.Windows.Forms.ToolStrip> pero para los que desea la funcionalidad <xref:System.Windows.Forms.ToolStrip>.|  
|<xref:System.Windows.Forms.ToolStripItemPlacement>|Especifica si un <xref:System.Windows.Forms.ToolStripItem> se coloca en el <xref:System.Windows.Forms.ToolStrip> principal, en el desbordamiento <xref:System.Windows.Forms.ToolStrip> o en ninguno.|  
  
 Para obtener más información, vea [Resumen de la tecnología ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-technology-summary.md) y [Arquitectura del control ToolStrip](../../../../docs/framework/winforms/controls/toolstrip-control-architecture.md).  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>