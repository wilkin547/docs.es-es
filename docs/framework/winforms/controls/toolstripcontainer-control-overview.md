---
title: "Informaci&#243;n general del control ToolStripContainer | Microsoft Docs"
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
  - "ToolStripContainer"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "barras de herramientas [Windows Forms], espacio compartido integrado"
  - "ToolStripContainer (control) [Windows Forms], acerca del control ToolStripContainer"
ms.assetid: c7d63bff-64e2-4a63-bd89-d31bc96dacb8
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# Informaci&#243;n general del control ToolStripContainer
<xref:System.Windows.Forms.ToolStripContainer> tiene paneles en sus laterales izquierdo, derecho, superior e inferior para colocar y compartir el espacio de los controles <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.StatusStrip>.  Varios controles <xref:System.Windows.Forms.ToolStrip> se apilan verticalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> izquierdo o derecho.  Se apilan horizontalmente si los coloca en el <xref:System.Windows.Forms.ToolStripContainer> superior o inferior.  Puede utilizar el panel <xref:System.Windows.Forms.ToolStripContentPanel> central del control <xref:System.Windows.Forms.ToolStripContainer> para colocar controles tradicionales en el formulario.  
  
 Cualquiera o todos los controles <xref:System.Windows.Forms.ToolStripContainer> son directamente seleccionables en tiempo de diseño y se pueden eliminar.  Cada panel de <xref:System.Windows.Forms.ToolStripContainer> se puede expandir y contraer y cambia el tamaño con los controles que contiene.  
  
### Miembros importantes de ToolStripContainer  
  
|Name|Descripción|  
|----------|-----------------|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanel%2A>|Obtiene el panel inferior del objeto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.BottomToolStripPanelVisible%2A>|Obtiene o establece un valor que indica si está visible el panel inferior del control <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanel%2A>|Obtiene el panel izquierdo del objeto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.LeftToolStripPanelVisible%2A>|Obtiene o establece un valor que indica si está visible el panel izquierdo del control <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanel%2A>|Obtiene el panel derecho del objeto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.RightToolStripPanelVisible%2A>|Obtiene o establece un valor que indica si está visible el panel derecho del control <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanel%2A>|Obtiene el panel superior del objeto <xref:System.Windows.Forms.ToolStripContainer>.|  
|<xref:System.Windows.Forms.ToolStripContainer.TopToolStripPanelVisible%2A>|Obtiene o establece un valor que indica si está visible el panel superior del control <xref:System.Windows.Forms.ToolStripContainer>.|  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripContainer>   
 <xref:System.Windows.Forms.ToolStripContentPanel>