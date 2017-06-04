---
title: "C&#243;mo: Crear columnas de s&#243;lo lectura en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], solo lectura"
  - "datos [Windows Forms], mostrar"
  - "DataGridView (control) [Windows Forms], columnas de sólo lectura"
  - "Windows Forms, columnas"
ms.assetid: b4ef7a75-ab33-4ee3-b2cf-201530e454e9
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Crear columnas de s&#243;lo lectura en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador
De forma predeterminada, los usuarios pueden modificar el texto y los datos numéricos mostrados en el control <xref:System.Windows.Forms.DataGridView> de los formularios Windows Forms.  Si desea mostrar datos que no estén pensados para su modificación, las columnas que contienen los datos deben ser de sólo lectura.  Para obtener información sobre cómo hacer que el control sea de sólo lectura, vea [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para hacer que una columna sea de sólo lectura mediante el diseñador  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  En la cuadrícula **Propiedades de columna**, establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A> en `true`.  
  
    > [!NOTE]
    >  También puede agregar una columna de sólo lectura activando la casilla **Sólo lectura** en el cuadro de diálogo **Agregar columna**.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=fullName>   
 [Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Impedir la adición y eliminación de filas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)