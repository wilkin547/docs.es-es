---
title: "C&#243;mo: Deshabilitar ToolStripMenuItems | Microsoft Docs"
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
  - "deshabilitar elementos de menú"
  - "elementos de menú, deshabilitar"
  - "elementos de menú, habilitar"
  - "menús, deshabilitar elementos de menú"
  - "ToolStripMenuItems, deshabilitar"
  - "ToolStripMenuItems, habilitar"
ms.assetid: bcc1da84-50fd-41d2-8475-103b581d5654
caps.latest.revision: 15
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 15
---
# C&#243;mo: Deshabilitar ToolStripMenuItems
Puede limitar o ampliar los comandos que introducen los usuarios habilitando y deshabilitando los elementos de menú en respuesta a las actividades del usuario.  Los elementos de menú están habilitados de forma predeterminada cuando se crean, pero esto se puede ajustar mediante la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A>.  Puede manipular en tiempo de diseño esta propiedad en la ventana **Propiedades** o mediante programación estableciéndola en código.  
  
### Para deshabilitar un elemento de menú mediante programación  
  
-   Dentro del método donde se establecen las propiedades del elemento de menú, agregue código para establecer la propiedad <xref:System.Windows.Forms.ToolStripMenuItem.Enabled%2A> en `false`.  
  
    ```vb  
    MenuItem1.Enabled = False  
    ```  
  
    ```csharp  
    menuItem1.Enabled = false;  
    ```  
  
    ```cpp  
    menuItem1->Enabled = false;  
    ```  
  
    > [!TIP]
    >  Al deshabilitar el primer elemento de menú o de nivel superior de un menú se ocultan todos los elementos de menú contenidos dentro del menú, pero no se deshabilitan.  Del mismo modo, al deshabilitar un elemento de menú que tenga elementos de submenú se ocultan los elementos de submenú, pero no se deshabilitan.  Si ninguno de los comandos de un menú dado está disponible para el usuario, se considera una buena práctica de programación ocultar y deshabilitar todo el menú, para presentar una interfaz de usuario limpia.  Debe ocultar y deshabilitar el menú, y deshabilitar todos los elementos y elementos de submenú del menú, ya que el hecho de ocultarlo no impide el acceso a un comando de menú mediante una tecla de método abreviado.  Establezca la propiedad <xref:System.Windows.Forms.ToolStripItem.Visible%2A> de un elemento de menú de nivel superior en `false` para ocultar todo el menú.  
  
## Vea también  
 <xref:System.Windows.Forms.MenuStrip>   
 <xref:System.Windows.Forms.ToolStripMenuItem>   
 [Cómo: Ocultar ToolStripMenuItems](../../../../docs/framework/winforms/controls/how-to-hide-toolstripmenuitems.md)   
 [Información general sobre el control MenuStrip](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)