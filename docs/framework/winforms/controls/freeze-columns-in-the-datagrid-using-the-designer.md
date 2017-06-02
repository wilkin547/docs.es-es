---
title: "C&#243;mo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], congelar"
  - "datos [Windows Forms], mostrar"
  - "DataGridView (control) [Windows Forms], inmovilización de columnas"
  - "Windows Forms, columnas"
ms.assetid: 87412dd2-478f-4751-af87-dafc591fc215
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Inmovilizar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador
Cuando los usuarios ven los datos mostrados en un control <xref:System.Windows.Forms.DataGridView> de formularios Windows Forms, a veces tienen que referirse con frecuencia a una columna o a un conjunto de columnas.  Por ejemplo, cuando se muestra una tabla de información de clientes que contiene muchas columnas, es práctico mostrar siempre el nombre del cliente, mientras se habilitan otras columnas para que se puedan desplazar fuera de la región visible.  
  
 Para conseguir este comportamiento, puede inmovilizar las columnas en el control.  Cuando inmoviliza una columna, también se inmovilizan todas las columnas situadas a su izquierda \(o a su derecha en los scripts de idioma de derecha a izquierda\).  Las columnas inmovilizadas permanecen en su sitio mientras se pueden desplazar todas las demás columnas.  Si se habilita la reordenación de las columnas, las columnas inmovilizadas se tratan como un grupo distinto de las columnas no inmovilizadas.  Los usuarios pueden cambiar la posición de las columnas en los grupos, pero no pueden mover una columna de un grupo a otro.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para inmovilizar una columna mediante el diseñador  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  En la cuadrícula **Propiedades de columna**, establezca la propiedad <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A> en `true`.  
  
    > [!NOTE]
    >  También puede inmovilizar una columna al agregarla seleccionando el cuadro **Inmovilizar** en el cuadro de diálogo **Agregar columna**.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn.Frozen%2A?displayProperty=fullName>   
 [Cómo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)   
 [Cómo: Habilitar la reordenación de columnas en el control DataGridView de formularios Windows Forms mediante el Diseñador](../../../../docs/framework/winforms/controls/enable-column-reordering-in-the-datagrid-using-the-designer.md)   
 [How to: Display Right\-to\-Left Text in Windows Forms for Globalization](http://msdn.microsoft.com/es-es/f0663385-2354-4c65-8676-706422283b14)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)