---
title: "C&#243;mo: Ocultar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], ocultar"
  - "datos [Windows Forms], mostrar"
  - "DataGridView (control) [Windows Forms], ocultación de columnas"
  - "Windows Forms, columnas"
ms.assetid: a81c38e6-2527-426a-bcb1-be691403be04
caps.latest.revision: 14
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 14
---
# C&#243;mo: Ocultar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador
A veces se desea mostrar solo algunas de las columnas que están disponibles en el control <xref:System.Windows.Forms.DataGridView> de Windows Forms.  Por ejemplo, se puede mostrar una columna con el sueldo de los empleados a los usuarios con credenciales de administración y ocultarla a los demás usuarios.  Otra opción es enlazar el control a un origen de datos que contiene muchas columnas, algunas de los cuales se desea mostrar.  En este caso, se quitarán las columnas que no interese mostrar en lugar de ocultarlas.  Para obtener más información, vea [Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para ocultar una columna mediante el diseñador  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  En la cuadrícula **Propiedades de columna**, establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A> en `false`.  
  
    > [!NOTE]
    >  También puede ocultar una columna al agregarla si desactiva la casilla **Visible** del cuadro de diálogo **Agregar columna**.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Visible%2A?displayProperty=fullName>   
 [Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)