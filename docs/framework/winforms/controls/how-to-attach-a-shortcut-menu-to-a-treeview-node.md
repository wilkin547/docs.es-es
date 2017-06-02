---
title: "C&#243;mo: Asociar un men&#250; contextual a un nodo TreeView | Microsoft Docs"
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
  - "menús contextuales, agregar a controles TreeView"
  - "nodos de árbol en el control TreeView, menús contextuales"
  - "TreeView (control) [Windows Forms], agregar menús contextuales"
ms.assetid: a23c6752-fd8f-44ad-b781-bab37962fc7c
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Asociar un men&#250; contextual a un nodo TreeView
El control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms muestra una jerarquía de nodos similar a la que se muestran los archivos y las carpetas en el panel izquierdo del Explorador de Windows.  Estableciendo la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>, puede proporcionar operaciones contextuales al usuario cuando hacen clic con el botón secundario en el control <xref:System.Windows.Forms.TreeView>.  Asociando un componente <xref:System.Windows.Forms.ContextMenuStrip> a elementos <xref:System.Windows.Forms.TreeNode> individuales, puede agregar un nivel personalizado de funcionalidad del menú contextual a sus controles <xref:System.Windows.Forms.TreeView>.  
  
### Para asociar un menú contextual a un TreeNode mediante programación  
  
1.  Cree instancias de un control <xref:System.Windows.Forms.TreeView> con los valores de propiedades adecuados, cree una raíz <xref:System.Windows.Forms.TreeNode> y, a continuación, agregue los subnodos.  
  
2.  Cree instancias de un componente <xref:System.Windows.Forms.ContextMenuStrip> y, a continuación, agregue un <xref:System.Windows.Forms.ToolStripMenuItem> para cada operación que desee establecer como disponible en tiempo de ejecución.  
  
3.  Establezca la propiedad <xref:System.Windows.Forms.TreeNode.ContextMenuStrip%2A> del <xref:System.Windows.Forms.TreeNode> adecuado al menú contextual que cree.  
  
4.  Cuando se establece esta propiedad, se muestra el menú contextual cuando se hace clic con el botón secundario en el nodo.  
  
 El ejemplo de código siguiente crea un <xref:System.Windows.Forms.TreeView> básico y un <xref:System.Windows.Forms.ContextMenuStrip> asociado a la raíz <xref:System.Windows.Forms.TreeNode> de <xref:System.Windows.Forms.TreeView>.  Deberá personalizar las opciones de menú para ajustarlas al <xref:System.Windows.Forms.TreeView> que está desarrollando.  De manera adicional, podría escribir código para controlar los eventos <xref:System.Windows.Forms.ToolStripItem.Click> de estos elementos de menú.  
  
 [!code-cpp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/cpp/Form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.TreeNodeContextMenuStrip#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/system.windows.forms.TreeNodeContextMenuStrip/VB/Form1.vb#1)]  
  
## Vea también  
 <xref:System.Windows.Forms.ContextMenuStrip>   
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)