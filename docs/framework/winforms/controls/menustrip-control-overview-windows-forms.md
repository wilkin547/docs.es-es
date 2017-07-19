---
title: "Informaci&#243;n general sobre el control MenuStrip (formularios Windows Forms) | Microsoft Docs"
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
  - "MenuStrip"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "menús, crear"
  - "MenuStrip (control) [Windows Forms], acerca del control MenuStrip"
ms.assetid: f45516e5-bf01-4468-b851-d45f4c33c055
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre el control MenuStrip (formularios Windows Forms)
Los menús exponen la funcionalidad a sus usuarios presionando comandos agrupados por un tema común.  
  
 El control <xref:System.Windows.Forms.MenuStrip> es nuevo en esta versión de Visual Studio y .NET Framework.  Con el control puede crear fácilmente menús como los de Microsoft Office.  
  
 El control <xref:System.Windows.Forms.MenuStrip> admite la interfaz de múltiples documentos \(MDI\) y combinación de menús, la información sobre herramientas y el desbordamiento.  Puede mejorar la utilidad y legibilidad de sus menús agregando teclas de acceso, teclas de método abreviado, marcas de verificación, imágenes y barras separadoras.  
  
 Aunque el control <xref:System.Windows.Forms.MenuStrip> reemplaza y agrega la funcionalidad al control <xref:System.Windows.Forms.MainMenu>, éste se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, si se desea.  
  
## Usos del control MenuStrip  
 Utilice el control <xref:System.Windows.Forms.MenuStrip> para:  
  
-   Crear fácilmente menús personalizados y comúnmente empleados compatibles con la interfaz de usuario avanzada y con las características de diseño, como la alineación y orden de texto e imágenes, operaciones de arrastrar y colocar, MDI, desbordamiento y modos alternativos de acceso a comandos de menú.  
  
-   Compatibilidad con el comportamiento y aspecto típico del sistema operativo.  
  
-   Controlar de forma coherente los eventos para todos los contenedores y los elementos contenidos, al igual que controla los eventos para otros controles.  
  
 La tabla siguiente muestra propiedades particularmente importantes de <xref:System.Windows.Forms.MenuStrip> y de las clases asociadas.  
  
|Propiedad.|Descripción|  
|----------------|-----------------|  
|<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>|Obtiene o establece el <xref:System.Windows.Forms.ToolStripMenuItem> utilizado para mostrar una lista de formularios MDI secundarios.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeAction%2A?displayProperty=fullName>|Obtiene o establece cómo se combinan los menús secundarios con menús primarios en aplicaciones MDI.|  
|<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A?displayProperty=fullName>|Obtiene o establece la posición de un elemento combinado dentro de un menú en aplicaciones MDI.|  
|<xref:System.Windows.Forms.Form.IsMdiContainer%2A?displayProperty=fullName>|Obtiene o establece un valor que indica si el formulario es un contenedor para los formularios MDI secundarios.|  
|<xref:System.Windows.Forms.MenuStrip.ShowItemToolTips%2A>|Obtiene o establece un valor que indica si la información sobre herramientas se muestra para <xref:System.Windows.Forms.MenuStrip>.|  
|<xref:System.Windows.Forms.MenuStrip.CanOverflow%2A>|Obtiene o establece un valor que indica si <xref:System.Windows.Forms.MenuStrip> admite la funcionalidad del desbordamiento.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShortcutKeys%2A>|Obtiene o establece las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem>.|  
|<xref:System.Windows.Forms.ToolStripMenuItem.ShowShortcutKeys%2A>|Obtiene o establece un valor que indica si las teclas de método abreviado asociadas a <xref:System.Windows.Forms.ToolStripMenuItem> se muestran al lado de <xref:System.Windows.Forms.ToolStripMenuItem>.|  
  
 La tabla siguiente muestra las clases <xref:System.Windows.Forms.MenuStrip> complementarias importantes.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripMenuItem>|Representa una opción seleccionable mostrada en un <xref:System.Windows.Forms.MenuStrip> o <xref:System.Windows.Forms.ContextMenuStrip>.|  
|<xref:System.Windows.Forms.ContextMenuStrip>|Representa un menú contextual.|  
|<xref:System.Windows.Forms.ToolStripDropDown>|Representa una control que permite al usuario seleccionar un elemento de la lista que se muestra cuando el usuario hace clic en un <xref:System.Windows.Forms.ToolStripDropDownButton> o en un elemento de menú de nivel superior.|  
|<xref:System.Windows.Forms.ToolStripDropDownItem>|Proporciona la funcionalidad básica para controles derivados de <xref:System.Windows.Forms.ToolStripItem> que muestra los elementos desplegables cuando se hace clic en ellos.|  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStrip>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 <xref:System.Windows.Forms.StatusStrip>   
 <xref:System.Windows.Forms.ToolStripItem>   
 <xref:System.Windows.Forms.ToolStripDropDown>