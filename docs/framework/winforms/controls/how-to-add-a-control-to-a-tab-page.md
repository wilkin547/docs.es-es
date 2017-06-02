---
title: "C&#243;mo: Agregar un control a una p&#225;gina de fichas | Microsoft Docs"
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
  - "controles de fichas, orden de tabulación"
  - "páginas de fichas, agregar controles"
  - "TabPage (control)"
ms.assetid: b092532e-7346-469f-b9a1-897f9bea4fb7
caps.latest.revision: 19
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 19
---
# C&#243;mo: Agregar un control a una p&#225;gina de fichas
Puede utilizar <xref:System.Windows.Forms.TabControl> de formularios Windows Forms para mostrar otros controles de un modo organizado.  El procedimiento siguiente muestra cómo agregar un botón a la primera pestaña.  Para obtener información sobre cómo agregar iconos a la parte de la etiqueta de una página de ficha, vea [Cómo: Cambiar la apariencia del control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md).  
  
### Para agregar un control mediante programación  
  
1.  Utilice el método <xref:System.Windows.Forms.Control.ControlCollection.Add%2A> de la colección que devuelve la propiedad <xref:System.Windows.Forms.Control.Controls%2A> de <xref:System.Windows.Forms.TabPage>:  
  
     [!code-cpp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cpp/add.cpp#1)]
     [!code-csharp[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/cs/add.cs#1)]
     [!code-vb[TabPageControlCollectionHowToAdd#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/tabpagecontrolcollectionhowtoadd/vb/add.vb#1)]  
  
## Vea también  
 [TabControl \(Control\)](../../../../docs/framework/winforms/controls/tabcontrol-control-windows-forms.md)   
 [Información general del control TabControl](../../../../docs/framework/winforms/controls/tabcontrol-control-overview-windows-forms.md)   
 [Cómo: Cambiar la apariencia del control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-change-the-appearance-of-the-windows-forms-tabcontrol.md)   
 [Cómo: Deshabilitar páginas de ficha](../../../../docs/framework/winforms/controls/how-to-disable-tab-pages.md)   
 [Cómo: Agregar y quitar fichas con el control TabControl de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)