---
title: "Informaci&#243;n general sobre MainMenu (Componente, formularios Windows Forms) | Microsoft Docs"
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
  - "MenuItem"
  - "MainMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "MainMenu (control) [Windows Forms], acerca del control MainMenu"
  - "menús"
ms.assetid: b41cc5a3-cc59-4996-aa3c-8dd9c17d3c90
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# Informaci&#243;n general sobre MainMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque los controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores y les agregan funcionalidad, los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 El componente <xref:System.Windows.Forms.MainMenu> de formularios Windows Forms muestra un menú en tiempo de ejecución.  Todos los submenús del menú principal y los elementos individuales son objetos <xref:System.Windows.Forms.MenuItem>.  
  
## Propiedades principales  
 Para designar un elemento de menú como elemento predeterminado, establezca la propiedad <xref:System.Windows.Forms.MenuItem.DefaultItem%2A> en `true`.  El elemento predeterminado aparece en negrita cuando se hace clic en el menú.  El valor de la propiedad <xref:System.Windows.Forms.MenuItem.Checked%2A> del elemento de menú puede ser `true` o `false`, e indica si éste está seleccionado.  La propiedad <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> del elemento de menú personaliza el aspecto del elemento seleccionado: si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en `true`, aparece un botón de radio al lado del elemento; si <xref:System.Windows.Forms.MenuItem.RadioCheck%2A> se establece en `false`, aparece una marca de verificación al lado del elemento.  
  
## Vea también  
 <xref:System.Windows.Forms.MainMenu>   
 <xref:System.Windows.Forms.Menu>   
 <xref:System.Windows.Forms.MenuItem>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)