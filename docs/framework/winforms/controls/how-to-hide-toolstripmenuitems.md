---
title: "C&#243;mo: Ocultar ToolStripMenuItems | Microsoft Docs"
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
  - "ocultar elementos de menú"
  - "elementos de menú, ocultar"
  - "menús, ocultar elementos de menú"
  - "MenuStrip (control) [Windows Forms], ocultar elementos de menú"
  - "ToolStripMenuItems, ocultar"
ms.assetid: 418a768f-808a-44cd-8cef-f4e161883621
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Ocultar ToolStripMenuItems
Ocultar elementos de menú es un modo de controlar la interfaz de usuario de la aplicación y restringir los comandos de usuario.  Con frecuencia, se quiere ocultar un menú completo cuando todos sus elementos no están disponibles.  Esto supone menos distracciones para el usuario.  Es más, a veces es necesario ocultar y deshabilitar el menú o elemento de menú, ya que si sólo se oculta, no impide al usuario el acceso a los comandos de menú por medio de teclas de método abreviado.  
  
### Para ocultar un elemento de menú mediante programación  
  
-   Dentro del método donde se establecen las propiedades del elemento de menú, agregue el código para establecer la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> en `false`.  
  
    ```vb  
    MenuItem3.Visible = False  
  
    ```  
  
    ```csharp  
    menuItem3.Visible = false;  
  
    ```  
  
    ```cpp  
    menuItem3->Visible = false;  
  
    ```  
  
## Vea también  
 <xref:System.Windows.Forms.ToolStripItem.Visible%2A>   
 <xref:System.Windows.Forms.MenuStrip>   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)   
 [Cómo: Deshabilitar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-disable-toolstripmenuitems.md)