---
title: Procedimiento para agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: 5e530b475745a3df7482b9ea4276f004d13ec055
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61642456"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedimiento para agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el diseñador

> [!NOTE]
>  El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).  
  
 Puede mostrar datos en los formularios de Windows <xref:System.Windows.Forms.DataGrid> control en las tablas y columnas mediante la creación de <xref:System.Windows.Forms.DataGridTableStyle> objetos y agregarlos a la <xref:System.Windows.Forms.GridTableStylesCollection> objeto, que se accede mediante el <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad. Cada tabla muestra el contenido de la tabla de datos se haya especificado en el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad de la <xref:System.Windows.Forms.DataGridTableStyle>. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas dentro de esa tabla de datos. Puede restringir qué columnas de la tabla aparecen agregando <xref:System.Windows.Forms.DataGridColumnStyle> objetos a la <xref:System.Windows.Forms.GridColumnStylesCollection>, que se accede a través de la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad de cada uno <xref:System.Windows.Forms.DataGridTableStyle>.  
  
 Los procedimientos siguientes requieren un **aplicación Windows** proyecto con un formulario que contiene un <xref:System.Windows.Forms.DataGrid> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). De forma predeterminada en Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas**. Para obtener información sobre cómo agregarlo, vea [Cómo: Agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).  
  
> [!NOTE]
>  Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).  
  
### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Para agregar una tabla al control DataGrid en el diseñador  
  
1. Para mostrar los datos en la tabla, se debe enlazar el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos. Para obtener más información, vea [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos mediante el diseñador](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).  
  
2. Seleccione el <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad en la ventana Propiedades y, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) junto a la propiedad para mostrar el **Editor de colección DataGridTableStyle**.  
  
3. En el editor de colecciones, haga clic en **agregar** para insertar un estilo de tabla.  
  
4. Haga clic en **Aceptar** para cerrar el editor de colecciones y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad.  
  
     Cuando vuelva a abrir el editor de colecciones, las tablas de datos enlazadas al control aparecerá en la lista desplegable para el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad del estilo de tabla.  
  
5. En el **miembros** cuadro del editor de la colección, haga clic en el estilo de tabla.  
  
6. En el **propiedades** cuadro del editor de colección, seleccione la <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> valor de la tabla que desea mostrar.  
  
### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Para agregar una columna al control DataGrid en el diseñador  
  
1. En el **miembros** cuadro de la **Editor de colección DataGridTableStyle**, seleccione el estilo de tabla correspondiente. En el **propiedades** cuadro del editor de colección, seleccione la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> colección y, a continuación, haga clic en el botón de puntos suspensivos (![de pantalla de VisualStudioEllipsesButton](../media/vbellipsesbutton.png " vbEllipsesButton")) junto a la propiedad para mostrar el **Editor de colecciones DataGridColumnStyle**.  
  
2. En el editor de colecciones, haga clic en **agregar** para insertar un estilo de columna o haga clic en la flecha abajo junto a **agregar** para especificar un tipo de columna.  
  
     En el cuadro de lista desplegable, seleccione el <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn> tipo.  
  
3. Haga clic en Aceptar para cerrar el **Editor de colecciones DataGridColumnStyle**y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad.  
  
     Cuando vuelva a abrir el editor de colecciones, las columnas de datos en la tabla de datos enlazados aparecerá en la lista desplegable para el <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> la propiedad del estilo de columna.  
  
4. En el **miembros** cuadro del editor de la colección, haga clic en el estilo de columna.  
  
5. En el **propiedades** cuadro del editor de colección, seleccione la <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> valor para la columna que desea mostrar.  
  
## <a name="see-also"></a>Vea también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
