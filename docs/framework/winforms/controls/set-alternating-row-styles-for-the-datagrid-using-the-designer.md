---
title: "C&#243;mo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el dise&#241;ador | Microsoft Docs"
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
  - "datos [Windows Forms], mostrar"
  - "DataGridView (control) [Windows Forms], alternancia de estilos de fila"
  - "formatos de doble carta"
  - "filas, alternas"
  - "Windows Forms, filas"
ms.assetid: 02373442-bf94-4470-9f8a-e44c4a9d5b88
caps.latest.revision: 12
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 12
---
# C&#243;mo: Establecer estilos de fila alternos en el control DataGridView de formularios Windows Forms mediante el dise&#241;ador
Con frecuencia los datos tabulares se presentan en un formato de doble carta donde las filas alternas presentan distintos colores de fondo.  Este formato permite a los usuarios saber con facilidad las celdas que están en cada fila, sobre todo en el caso de tablas anchas que tienen muchas columnas.  
  
 Con el control <xref:System.Windows.Forms.DataGridView>, puede especificar toda la información de estilo a las filas alternas.  Puede utilizar características de estilo como el color de primer plano y la fuente, además del color de fondo, para diferenciar las filas alternas.  Para obtener más información, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
 El procedimiento siguiente requiere un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGridView>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Defina los estilos para filas alternas  
  
1.  Seleccione el control <xref:System.Windows.Forms.DataGridView> en el diseñador.  
  
2.  En la ventana **Propiedades**, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad <xref:System.Windows.Forms.DataGridView.AlternatingRowsDefaultCellStyle%2A>.  
  
3.  En el cuadro de diálogo **Generador de CellStyle**, defina el estilo estableciendo las propiedades y utilice el panel **Vista previa** para confirmar sus opciones.  Los estilos que especifique se utilizan cada dos filas mostradas en el control, iniciándose con la segunda.  
  
4.  Para definir los estilos para las filas restantes, repita los pasos 2 y 3 utilizando la propiedad <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A>.  
  
    > [!NOTE]
    >  Las celdas se muestran mediante estilos heredados de distintas propiedades.  Para obtener más información sobre herencia de estilos, vea [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## Vea también  
 <xref:System.Windows.Forms.DataGridView>   
 [Estilos de celda en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)   
 [Estilo y formato básicos del control DataGridView en formularios Windows Forms](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)   
 [Utilizar el Diseñador con el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/using-the-designer-with-the-windows-forms-datagridview-control.md)   
 [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa)   
 [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)