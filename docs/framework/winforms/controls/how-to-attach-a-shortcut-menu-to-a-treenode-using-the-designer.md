---
title: "C&#243;mo: Adjuntar un men&#250; contextual a un objeto TreeNode mediante el Dise&#241;ador | Microsoft Docs"
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
  - "menús contextuales, adjuntar a TreeNodes"
  - "TreeNode, adjuntar un menú contextual mediante el diseñador"
ms.assetid: 8e45e184-1313-4f8f-90ff-2cd5789b2268
caps.latest.revision: 9
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 9
---
# C&#243;mo: Adjuntar un men&#250; contextual a un objeto TreeNode mediante el Dise&#241;ador
El control <xref:System.Windows.Forms.TreeView> de los formularios Windows Forms muestra una jerarquía de nodos similar a la que se muestran los archivos y las carpetas en el panel izquierdo de la característica Explorador de Windows en los sistemas operativos Windows.  Estableciendo la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A>, puede proporcionar operaciones contextuales al usuario cuando hacen clic con el botón secundario en el control <xref:System.Windows.Forms.TreeView>.  Asociando un componente <xref:System.Windows.Forms.ContextMenuStrip> a elementos <xref:System.Windows.Forms.TreeNode> individuales, puede agregar un nivel personalizado de funcionalidad del menú contextual a sus controles <xref:System.Windows.Forms.TreeView>.  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para asociar en tiempo de diseño un menú contextual a un TreeNode  
  
1.  Agregue un control <xref:System.Windows.Forms.TreeView> al formulario y, a continuación, agregue según sea necesario los nodos a <xref:System.Windows.Forms.TreeView>.  Para obtener más información, vea [Cómo: Agregar y quitar nodos con el control TreeView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md).  
  
2.  Agregue un componente <xref:System.Windows.Forms.ContextMenuStrip> al formulario y, a continuación, agregue elementos de menú al menú contextual que representa las operaciones en el nivel de nodo que desea estén disponibles en tiempo de ejecución.  Para obtener más información, vea [Cómo: Agregar elementos de menú a ContextMenuStrip](../../../../docs/framework/winforms/controls/how-to-add-menu-items-to-a-contextmenustrip.md).  
  
3.  Vuelva a abrir el cuadro de diálogo **TreeNodeEditor** para el control <xref:System.Windows.Forms.TreeView>, seleccione el nodo que va a editar y establezca su propiedad <xref:System.Windows.Forms.ContextMenuStrip> en el menú contextual que ha agregado.  
  
4.  Cuando se establece esta propiedad, se muestra el menú contextual cuando se hace clic con el botón secundario en el nodo.  
  
     De manera adicional, podría escribir código para controlar los eventos <xref:System.Windows.Forms.ToolStripItem.Click> de estos elementos de menú.  
  
## Vea también  
 [TreeView \(Control\)](../../../../docs/framework/winforms/controls/treeview-control-windows-forms.md)   
 [Información general del control TreeView](../../../../docs/framework/winforms/controls/treeview-control-overview-windows-forms.md)   
 [ContextMenuStrip \(Control\)](../../../../docs/framework/winforms/controls/contextmenustrip-control.md)