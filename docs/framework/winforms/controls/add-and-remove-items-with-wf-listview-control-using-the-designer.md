---
title: "C&#243;mo: Agregar y quitar elementos de un control ListView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "ListView (control) [Windows Forms], agregar elementos de lista"
  - "ListView (control) [Windows Forms], llenar"
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Agregar y quitar elementos de un control ListView de formularios Windows Forms mediante el Dise&#241;ador
El proceso de agregar un elemento a un control <xref:System.Windows.Forms.ListView> de formularios Windows Forms consiste básicamente en especificar el elemento y asignarle propiedades.  Puede agregar o quitar elementos de la lista en cualquier momento.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ListView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar o quitar elementos con el diseñador  
  
1.  Seleccione el control <xref:System.Windows.Forms.ListView>.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.ListView.Items%2A>.  
  
     Aparecerá el **Editor de la colección de ListViewItem**.  
  
3.  Para agregar un elemento, haga clic en el botón **Agregar**.  A continuación puede establecer las propiedades del nuevo elemento, como las propiedades <xref:System.Windows.Forms.ListView.Text%2A> y <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>.  
  
4.  Para quitar un elemento, selecciónelo y haga clic en el botón **Quitar**.  
  
## Vea también  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Cómo: Agregar columnas al control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar iconos del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)   
 [Cómo: Agrupar elementos en un control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)