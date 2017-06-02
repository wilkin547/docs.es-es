---
title: "C&#243;mo: Agregar columnas al control ListView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], agregar a controles ListView"
  - "ListView (control) [Windows Forms], agregar encabezados de columna"
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
caps.latest.revision: 6
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 6
---
# C&#243;mo: Agregar columnas al control ListView de formularios Windows Forms mediante el Dise&#241;ador
El control <xref:System.Windows.Forms.ListView> de formularios Windows Forms puede mostrar varias columnas para cada elemento de la lista cuando se utiliza la vista **Detalles**.  Puede utilizar las columnas para mostrar información de diversos tipos acerca de cada elemento de la lista.  Por ejemplo, una lista de archivos puede mostrar el nombre de archivo, el tipo de archivo, el tamaño y la fecha de la última modificación.  Para obtener información sobre cómo rellenar las columnas una vez creadas, vea [Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.ListView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar columnas en el diseñador  
  
1.  En la ventana **Propiedades**, establezca la propiedad <xref:System.Windows.Forms.ListView.View%2A> del control en <xref:System.Windows.Forms.View>.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de **puntos suspensivos** \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad <xref:System.Windows.Forms.ListView.Columns%2A>.  
  
     Aparecerá el **Editor de la colección ColumnHeader**.  
  
3.  Utilice el botón **Agregar** para agregar nuevas columnas.  A continuación, puede seleccionar el encabezado de la columna y definir el texto \(la leyenda de la columna\), la alineación del texto y el ancho de la columna.  
  
## Vea también  
 [Información general del control ListView](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)   
 [Cómo: Agregar y quitar elementos con el control ListView de Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar subelementos en columnas con el control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)   
 [Cómo: Mostrar iconos del control ListView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)   
 [Cómo: Agregar información personalizada a los controles TreeView o ListView \(formularios Windows Forms\)](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)