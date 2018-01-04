---
title: "Cómo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Diseñador"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 48471427baccfa9fb8e7c3aedbb9576ab0d34243
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Cómo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Diseñador
> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Puede mostrar datos en formularios Windows Forms <xref:System.Windows.Forms.DataGrid> control en tablas y columnas mediante la creación de <xref:System.Windows.Forms.DataGridTableStyle> objetos y agregándolos a la <xref:System.Windows.Forms.GridTableStylesCollection> objeto, que se obtiene acceso a través de la <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad. Cada estilo de tabla muestra el contenido de la tabla de datos se haya especificado en el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle>. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas de esa tabla de datos. Puede restringir las columnas de la tabla que aparecen agregando <xref:System.Windows.Forms.DataGridColumnStyle> objetos a la <xref:System.Windows.Forms.GridColumnStylesCollection>, que se tiene acceso a través de la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad de cada <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Los procedimientos siguientes requieren un **aplicación de Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, consulte [Cómo: crear un proyecto de aplicación de Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) y [Cómo: agregar controles a formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md). De forma predeterminada en [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas**. Para obtener información sobre cómo agregarlo, vea [Cómo: agregar elementos al cuadro de herramientas](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para obtener más información, consulte [Personalizar la configuración de desarrollo en Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Para agregar una tabla al control DataGrid en el diseñador  
  
1.  Para mostrar los datos en la tabla, debe enlazar primero el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos. Para obtener más información, consulte [Cómo: enlazar el DataGrid Control de formularios Windows Forms a un origen de datos mediante el diseñador](../../../../docs/framework/winforms/controls/bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2.  Seleccione el <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad en la ventana Propiedades y, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) junto a la propiedad que se va a mostrar el **Editor de colecciones DataGridTableStyles**.  
  
3.  En el editor de colecciones, haga clic en **agregar** para insertar un estilo de tabla.  
  
4.  Haga clic en **Aceptar** para cerrar el editor de colecciones y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad.  
  
     Cuando vuelva a abrir el editor de colecciones, las tablas de datos enlazadas al control aparecerán en la lista desplegable para el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad del estilo de tabla.  
  
5.  En el **miembros** cuadro del editor de colecciones, haga clic en el estilo de tabla.  
  
6.  En el **propiedades** cuadro del editor de la colección, seleccione la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> valor de la tabla que desea mostrar.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Para agregar una columna al control DataGrid en el diseñador  
  
1.  En el **miembros** cuadro de la **Editor de colecciones DataGridTableStyles**, seleccione el estilo de tabla adecuado. En el **propiedades** cuadro del editor de la colección, seleccione la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> colección y, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton] (../../../../docs/framework/winforms/media/vbellipsesbutton.png " vbEllipsesButton")) junto a la propiedad para mostrar el **Editor de colecciones DataGridColumnStyle**.  
  
2.  En el editor de colecciones, haga clic en **agregar** para insertar un estilo de columna o haga clic en la flecha abajo junto a **agregar** para especificar un tipo de columna.  
  
     En el cuadro de lista desplegable, seleccione la <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn> tipo.  
  
3.  Haga clic en Aceptar para cerrar el **Editor de colecciones DataGridColumnStyle**y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad.  
  
     Cuando vuelva a abrir el editor de colecciones, las columnas de datos en la tabla de datos enlazada aparecerán en la lista desplegable para el <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> la propiedad del estilo de columna.  
  
4.  En el **miembros** cuadro del editor de colecciones, haga clic en el estilo de columna.  
  
5.  En el **propiedades** cuadro del editor de la colección, seleccione la <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valor de la columna que desea mostrar.  
  
## <a name="see-also"></a>Vea también  
 [DataGrid (control)](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
