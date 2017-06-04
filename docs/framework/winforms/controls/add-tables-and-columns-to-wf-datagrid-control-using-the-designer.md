---
title: "C&#243;mo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Dise&#241;ador | Microsoft Docs"
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
  - "columnas [Windows Forms], agregar a un control DataGrid"
  - "DataGrid (control) [Windows Forms], agregar tablas y columnas"
  - "tablas [Windows Forms], agregar a un control DataGrid"
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: 10
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 10
---
# C&#243;mo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Dise&#241;ador
> [!NOTE]
>  Aunque el control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>, este control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y, en su caso, de uso futuro.  Para obtener más información, vea [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).  
  
 Para mostrar datos en el control <xref:System.Windows.Forms.DataGrid> de formularios Windows Forms en formato de tablas y columnas, puede crear objetos <xref:System.Windows.Forms.DataGridTableStyle> y agregarlos al objeto <xref:System.Windows.Forms.GridTableStylesCollection>, al que se obtiene acceso a través de la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control <xref:System.Windows.Forms.DataGrid>.  Cada estilo de tabla muestra el contenido de la tabla de datos que se haya especificado en la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de <xref:System.Windows.Forms.DataGridTableStyle>.  De forma predeterminada, si un estilo de tabla no tiene estilos de columna especificados se mostrarán todas las columnas que contenga la tabla de datos.  Para limitar qué columnas de la tabla aparecerán agregue objetos <xref:System.Windows.Forms.DataGridColumnStyle> a la colección <xref:System.Windows.Forms.GridColumnStylesCollection>, a la que se obtiene acceso mediante la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> de cada objeto <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Los procedimientos siguientes requieren un proyecto de **Aplicación para Windows** con un formulario que contiene un control <xref:System.Windows.Forms.DataGrid>.  Para obtener información sobre cómo configurar tal proyecto, vea [How to: Create a Windows Application Project](http://msdn.microsoft.com/es-es/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: Agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).  En [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], el control <xref:System.Windows.Forms.DataGrid> no está en el **Cuadro de herramientas** de manera predeterminada.  Para obtener información sobre cómo agregarlo, vea [How to: Add Items to the Toolbox](http://msdn.microsoft.com/es-es/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos.  Para cambiar la configuración, elija **Importar y exportar configuraciones** en el menú **Herramientas**.  Para obtener más información, vea [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/es-es/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### Para agregar una tabla al control DataGrid en el diseñador  
  
1.  Para mostrar los datos de la tabla, deberá enlazar en primer lugar el control <xref:System.Windows.Forms.DataGrid> a un conjunto de datos.  Para obtener más información, vea [Cómo: Enlazar el control DataGrid de formularios Windows Forms a un origen de datos mediante el Diseñador](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Seleccione la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control <xref:System.Windows.Forms.DataGrid> en la ventana Propiedades y, a continuación, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) situado junto a la propiedad para mostrar el **Editor de la colección DataGridTableStyle**.  
  
3.  En el editor de colecciones, haga clic en **Agregar** para insertar un estilo de tabla.  
  
4.  Haga clic en **Aceptar** para cerrar el editor de colecciones; a continuación, ábralo de nuevo haciendo clic en el botón de puntos suspensivos que se encuentra junto a la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A>.  
  
     Cuando abra de nuevo el editor de colecciones, las tablas de datos enlazadas al control aparecerán en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> del estilo de tabla.  
  
5.  En el cuadro **Miembros** del editor de colecciones, haga clic en el estilo de tabla.  
  
6.  En el cuadro **Propiedades** del editor de colecciones, seleccione el valor <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de la tabla que desea mostrar.  
  
### Para agregar una columna al control DataGrid en el diseñador  
  
1.  En el cuadro **Miembros** del **Editor de la colección DataGridTableStyle**, seleccione el estilo de tabla adecuado.  En el cuadro **Propiedades** del editor de colecciones, seleccione la colección <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> y, a continuación, haga clic en el botón de puntos suspensivos \(![Captura de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")\) que se encuentra junto a la propiedad para mostrar el **Editor de la colección DataGridColumnStyle**.  
  
2.  En el editor de colecciones, haga clic en **Agregar** para insertar un estilo de columna o haga clic en la flecha hacia abajo que se encuentra junto a **Agregar** para especificar un tipo de columna.  
  
     En la lista desplegable, puede seleccionar el tipo <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn>.  
  
3.  Haga clic en OK para cerrar el **Editor de la colección DataGridColumnStyle**; a continuación, ábralo de nuevo haciendo clic en el botón de puntos suspensivos que se encuentra junto a la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.  
  
     Cuando abra de nuevo el editor de colecciones, las columnas de datos de la tabla de datos enlazada aparecerán en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> del estilo de columna.  
  
4.  En el cuadro **Miembros** del editor de colecciones, haga clic en el estilo de columna.  
  
5.  En el cuadro **Propiedades** del editor de colecciones, seleccione el valor <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> de la columna que desea mostrar.  
  
## Vea también  
 [Control DataGrid](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)   
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)