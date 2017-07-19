---
title: "C&#243;mo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.DataGridViewAddColumnDialog"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "DataGridView (control) [Windows Forms], agregar columnas"
  - "DataGridView (control) [Windows Forms], quitar columnas"
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# C&#243;mo: Agregar y quitar columnas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador
El control <xref:System.Windows.Forms.DataGridView> de los formularios Windows Forms debe contener las columnas para mostrar los datos.  Si está pensando en rellenar manualmente el control, debe agregar las columnas.  O bien, puede enlazar el control a un origen de datos, que genera y rellena automáticamente las columnas.  Si el origen de datos contiene más columnas de las que desea mostrar, puede quitar las columnas innecesarias.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar una columna mediante el diseñador  
  
1.  Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y seleccione **Agregar columna**.  
  
2.  En el cuadro de diálogo **Agregar columna**, elija la opción **Columna de enlace de datos** y seleccione una columna en el origen de datos, o seleccione la opción **Columna sin enlazar** y defina la columna mediante los campos proporcionados.  
  
3.  Haga clic en el botón **Agregar** para agregar la columna, haciendo que aparezca en el diseñador si las columnas existentes no han rellenado el área de presentación del control.  
  
    > [!NOTE]
    >  Puede modificar las propiedades de columna en el cuadro de diálogo **Editar columnas**, al que puede tener acceso desde la etiqueta inteligente de control.  
  
### Para quitar una columna mediante el diseñador  
  
1.  Elija **Editar columnas** en la etiqueta inteligente del control.  
  
2.  Seleccione una columna en la lista **Columnas seleccionadas**.  
  
3.  Haga clic en el botón **Quitar** para eliminar la columna, con lo que desaparece del diseñador.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)