---
title: "C&#243;mo: Agregar y quitar elementos de men&#250; con el componente ContextMenu de formularios Windows Forms | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "menús contextuales, agregar elementos"
  - "menús contextuales, ejemplos"
  - "menús contextuales, quitar elementos"
  - "ContextMenu (componente) [Windows Forms], agregar elementos"
  - "ContextMenu (componente) [Windows Forms], quitar elementos"
  - "ejemplos [Windows Forms], menús contextuales"
  - "menús contextuales, agregar elementos"
  - "menús contextuales, ejemplos"
  - "menús contextuales, quitar elementos"
ms.assetid: 426d1eaf-7fb8-4b0b-8a33-5e8721786ea4
caps.latest.revision: 16
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 16
---
# C&#243;mo: Agregar y quitar elementos de men&#250; con el componente ContextMenu de formularios Windows Forms
Explica cómo agregar y quitar elementos de un menú contextual en formularios Windows Forms.  
  
 El componente <xref:System.Windows.Forms.ContextMenu> de formularios Windows Forms proporciona un menú de comandos de uso frecuente que son relevantes para el objeto seleccionado.  Puede agregar elementos al menú contextual agregando objetos <xref:System.Windows.Forms.MenuItem> a la colección <xref:System.Windows.Forms.Menu.MenuItems%2A>.  
  
 Se pueden quitar elementos de un menú contextual de forma permanente; sin embargo, en tiempo de ejecución puede ser más conveniente ocultarlos o deshabilitarlos.  
  
> [!IMPORTANT]
>  Aunque los controles <xref:System.Windows.Forms.MenuStrip> y <xref:System.Windows.Forms.ContextMenuStrip> reemplazan los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> de versiones anteriores y les agregan funcionalidad, los controles <xref:System.Windows.Forms.MainMenu> y <xref:System.Windows.Forms.ContextMenu> se conservan a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  
  
### Para quitar elementos de un menú contextual  
  
1.  Utilice el método <xref:System.Windows.Forms.Menu.MenuItemCollection.Remove%2A> o <xref:System.Windows.Forms.Menu.MenuItemCollection.RemoveAt%2A> de la colección <xref:System.Windows.Forms.Menu.MenuItems%2A> del componente <xref:System.Windows.Forms.ContextMenu> para quitar un elemento de menú determinado.  
  
    ```vb  
    ' Removes the first item in the shortcut menu.  
    ContextMenu1.MenuItems.RemoveAt(0)  
    ' Removes a particular object from the shortcut menu.  
    ContextMenu1.MenuItems.Remove(mnuItemNew)  
  
    ```  
  
    ```csharp  
    // Removes the first item in the shortcut menu.  
    contextMenu1.MenuItems.RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1.MenuItems.Remove(mnuItemNew);  
  
    ```  
  
    ```cpp  
    // Removes the first item in the shortcut menu.  
    contextMenu1->MenuItems->RemoveAt(0);  
    // Removes a particular object from the shortcut menu.  
    contextMenu1->MenuItems->Remove(mnuItemNew);  
    ```  
  
     O bien  
  
2.  Utilice el método `Clear` de la colección `MenuItems` del componente <xref:System.Windows.Forms.ContextMenu> para quitar todos los elementos del menú.  
  
    ```vb  
    ContextMenu1.MenuItems.Clear()  
  
    ```  
  
    ```csharp  
    contextMenu1.MenuItems.Clear();  
  
    ```  
  
    ```cpp  
    contextMenu1->MenuItems->Clear();  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ContextMenu>   
 [ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-windows-forms.md)   
 [Información general sobre ContextMenu](../../../../docs/framework/winforms/controls/contextmenu-component-overview-windows-forms.md)