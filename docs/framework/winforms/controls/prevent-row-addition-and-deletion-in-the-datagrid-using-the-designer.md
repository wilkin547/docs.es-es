---
title: "C&#243;mo: Impedir la adici&#243;n y eliminaci&#243;n de filas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "DataGridView (control) [Windows Forms], impedir la inclusión o eliminación de filas"
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
caps.latest.revision: 11
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 11
---
# C&#243;mo: Impedir la adici&#243;n y eliminaci&#243;n de filas en el control DataGridView de formularios Windows Forms mediante el Dise&#241;ador
A veces deseará impedir que los usuarios escriban nuevas filas de datos o eliminen las filas existentes en el control <xref:System.Windows.Forms.DataGridView>.  Las nuevas filas se escriben en la fila especial para los nuevos registros en la parte inferior del control.  Cuando deshabilita la adición de filas, no se muestra la fila para los nuevos registros.  A continuación, puede hacer que el control sea de sólo lectura deshabilitando la eliminación de filas y la edición de celdas.  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para impedir la adición y eliminación de filas  
  
-   Haga clic en el glifo de la etiqueta inteligente \(![Glifo de etiqueta inteligente](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.png "VS\_WinFormSmtTagGlyph")\) situado en la esquina superior derecha del control <xref:System.Windows.Forms.DataGridView> y, a continuación, desactive las casillas **Habilitar acción de agregar** y **Habilitar eliminación**.  
  
    > [!NOTE]
    >  Para que el control sea de sólo lectura, borre también la casilla **Habilitar edición**.  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=fullName>   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)