---
title: "C&#243;mo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], tipos"
  - "datos [Windows Forms], mostrar"
  - "DataGridView (control) [Windows Forms], cambiar el tipo de columnas"
  - "Windows Forms, columnas"
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: 13
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 13
---
# C&#243;mo: Cambiar el tipo de una columna DataGridView de formularios Windows Forms mediante el Dise&#241;ador
Algunas veces se desea cambiar el tipo de una columna que ya se ha agregado a un control <xref:System.Windows.Forms.DataGridView> de formularios Windows Forms.  Por ejemplo, es posible que desee modificar los tipos de algunas de las columnas que se generan automáticamente cuando enlaza el control a un origen de datos.  Esto resulta útil cuando la tabla que se muestra tiene columnas que contienen claves externas a las filas en una tabla relacionada.  En este caso, es posible que quiera reemplazar las columnas del cuadro de texto que muestran estas claves externas con columnas de cuadro combinado que muestran valores más significativos desde la tabla relacionada.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para cambiar el tipo de una columna mediante el diseñador  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y seleccione **Editar columnas**.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  En la cuadrícula **Propiedades de columna**, establezca la propiedad `ColumnType` en el nuevo tipo de columna.  
  
    > [!NOTE]
    >  La propiedad `ColumnType` es una propiedad en tiempo de diseño únicamente que indica la clase que representa el tipo de columna.  No es una propiedad real definida en una clase de columna.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridViewColumn>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)