---
title: "Informaci&#243;n general sobre ContextMenu (Componente, formularios Windows Forms) | Microsoft Docs"
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
  - "ContextMenu"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "menús contextuales, ContextMenu (componente)"
  - "ContextMenu (componente) [Windows Forms], acerca del componente ContextMenu"
  - "menús contextuales, ContextMenu (componente)"
ms.assetid: 49d6398f-d3c4-4679-84fa-1de07b68b05e
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# Informaci&#243;n general sobre ContextMenu (Componente, formularios Windows Forms)
> [!IMPORTANT]
>  Aunque los controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores y les agregan funcionalidad, los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
 Con el componente <xref:System.Windows.Forms.ContextMenu> de formularios Windows Forms, puede proporcionar a los usuarios un menú contextual que contenga los comandos de uso frecuente asociados al objeto seleccionado.  Los elementos de un menú contextual suelen ser un subconjunto de los elementos de menús principales que aparecen en otros puntos de la aplicación.  Normalmente, el usuario tiene acceso al menú contextual haciendo clic con el botón secundario del mouse.  En formularios Windows Forms, los menús contextuales están asociados a controles.  
  
## Propiedades principales  
 Puede asociar un menú contextual a un control estableciendo la propiedad <xref:System.Windows.Forms.Control.ContextMenu%2A> del control en el componente <xref:System.Windows.Forms.ContextMenu>.  Un mismo menú contextual se puede asociar a varios controles, pero cada control sólo puede tener un menú contextual.  
  
 La propiedad principal del componente <xref:System.Windows.Forms.ContextMenu> es <xref:System.Windows.Forms.Menu.MenuItems%2A>.  Puede agregar elementos de menú creando objetos <xref:System.Windows.Forms.MenuItem> mediante programación y agregándolos al objeto <xref:System.Windows.Forms.Menu.MenuItemCollection> del menú contextual.  Dado que los elementos de un menú contextual se suelen tomar de otros menús, generalmente se copian para agregarlos al menú contextual.  
  
## Vea también  
 <xref:System.Windows.Forms.ContextMenu>   
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ContextMenuStrip>