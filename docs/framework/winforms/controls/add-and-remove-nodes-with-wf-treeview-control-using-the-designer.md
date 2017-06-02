---
title: "C&#243;mo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "ejemplos [Windows Forms], TreeView (control)"
  - "nodos de árbol en el control TreeView"
  - "TreeView (control) [Windows Forms], agregar nodos"
  - "TreeView (control) [Windows Forms], quitar nodos"
ms.assetid: 35bf1750-045e-4ec5-97cb-b47b0dbdaa2c
caps.latest.revision: 7
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 7
---
# C&#243;mo: Agregar y quitar nodos de un control TreeView de formularios Windows Forms mediante el Dise&#241;ador
Dado que el control <xref:System.Windows.Forms.TreeView> de formularios Windows Forms muestra nodos de forma jerárquica, al agregar un nodo es necesario prestar atención a cuál es su nodo primario.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.TreeView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar o quitar nodos en el diseñador  
  
1.  Seleccione el control <xref:System.Windows.Forms.TreeView>.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.TreeView.Nodes%2A>.  
  
     Aparecerá el **Editor TreeNode**.  
  
3.  Para agregar nodos debe existir un nodo raíz; si no existe ninguno, primero deberá hacer clic en el botón **Agregar raíz** para agregar uno.  A continuación, podrá agregar nodos secundarios seleccionando el nodo raíz o cualquier otro nodo y haciendo clic en el botón **Agregar secundario**.  
  
4.  Para eliminar nodos, seleccione el nodo que desea eliminar y haga clic en el botón **Eliminar**.  
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [Cómo: Establecer iconos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-icons-for-the-windows-forms-treeview-control.md)   
 [Cómo: Recorrer en iteración todos los nodos del control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control.md)   
 [Cómo: Determinar en qué nodo de TreeView se hizo clic](../../../../docs/framework/winforms/controls/how-to-determine-which-treeview-node-was-clicked-windows-forms.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)