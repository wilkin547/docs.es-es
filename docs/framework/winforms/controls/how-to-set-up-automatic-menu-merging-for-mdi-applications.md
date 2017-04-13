---
title: "C&#243;mo: Configurar la combinaci&#243;n autom&#225;tica de men&#250;s para aplicaciones MDI | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MenuStrip, combinar"
  - "Combinación, automática de menús"
ms.assetid: 55e32cad-1141-4a56-aa33-d9543ca3d393
caps.latest.revision: 5
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 5
---
# C&#243;mo: Configurar la combinaci&#243;n autom&#225;tica de men&#250;s para aplicaciones MDI
En el procedimiento siguiente se describen los pasos básicos para configurar la combinación automática en una aplicación de interfaz de múltiples documentos \(MDI\) con <xref:System.Windows.Forms.MenuStrip>.  
  
### Para configurar la combinación automática de menús  
  
1.  Cree el formulario primario de MDI estableciendo la propiedad <xref:System.Windows.Forms.Form.IsMdiContainer%2A> en `true`.  
  
2.  Agregue un objeto <xref:System.Windows.Forms.MenuStrip> al elemento primario de MDI, estableciendo la propiedad <xref:System.Windows.Forms.Form.MainMenuStrip%2A> en <xref:System.Windows.Forms.MenuStrip>.  
  
3.  Cree un formulario secundario de MDI y establezca su propiedad <xref:System.Windows.Forms.Form.MdiParent%2A> en el nombre del formulario principal.  
  
4.  Agregue un objeto <xref:System.Windows.Forms.MenuStrip> al formulario secundario de MDI.  
  
5.  En el formulario secundario, establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> de <xref:System.Windows.Forms.MenuStrip> en `false`.  
  
6.  Agregue elementos de menú a <xref:System.Windows.Forms.MenuStrip> del formulario secundario que desee combinar en <xref:System.Windows.Forms.MenuStrip> del formulario principal cuando se active el formulario secundario.  
  
7.  Use la propiedad <xref:System.Windows.Forms.ToolStripItem.MergeAction%2A> en los elementos de menú del objeto <xref:System.Windows.Forms.MenuStrip> del formulario secundario para controlar cómo se combinan en el formulario principal.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)