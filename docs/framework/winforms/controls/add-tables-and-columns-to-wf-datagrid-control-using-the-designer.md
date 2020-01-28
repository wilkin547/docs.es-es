---
title: Agregar tablas y columnas al control DataGrid mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: fed7465fbe665b1945161653616e3a21640e0b2a
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746266"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Cómo: Agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el Diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Puede mostrar los datos en el control Windows Forms <xref:System.Windows.Forms.DataGrid> en tablas y columnas creando objetos <xref:System.Windows.Forms.DataGridTableStyle> y agregándolos al objeto <xref:System.Windows.Forms.GridTableStylesCollection>, al que se tiene acceso a través de la propiedad <xref:System.Windows.Forms.DataGrid> del control <xref:System.Windows.Forms.DataGrid.TableStyles%2A>. Cada estilo de tabla muestra el contenido de la tabla de datos especificada en la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de la <xref:System.Windows.Forms.DataGridTableStyle>. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas de esa tabla de datos. Puede restringir Qué columnas de la tabla aparecen agregando <xref:System.Windows.Forms.DataGridColumnStyle> objetos a la <xref:System.Windows.Forms.GridColumnStylesCollection>, a la que se tiene acceso a través de la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> de cada <xref:System.Windows.Forms.DataGridTableStyle>.

Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGrid>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). De forma predeterminada en Visual Studio 2005, el control <xref:System.Windows.Forms.DataGrid> no está en el **cuadro de herramientas**. Para obtener información sobre cómo agregarlo, vea [Cómo: agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Para agregar una tabla al control DataGrid en el diseñador

1. Para mostrar los datos en la tabla, primero debe enlazar el control <xref:System.Windows.Forms.DataGrid> a un conjunto de datos. Para obtener más información, vea [Cómo: enlazar el control DataGrid de Windows Forms a un origen de datos mediante el diseñador](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md).

2. Seleccione la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control <xref:System.Windows.Forms.DataGrid> en el ventana Propiedades y, a continuación, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) del ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad para mostrar el editor de la **colección DataGridTableStyle**.

3. En el editor de la colección, haga clic en **Agregar** para insertar un estilo de tabla.

4. Haga clic en **Aceptar** para cerrar el editor de la colección y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A>.

     Al volver a abrir el editor de la colección, todas las tablas de datos enlazadas al control aparecerán en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> del estilo de tabla.

5. En el cuadro **miembros** del editor de colecciones, haga clic en el estilo de tabla.

6. En el cuadro **propiedades** del editor de la colección, seleccione el valor de <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de la tabla que desea mostrar.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Para agregar una columna al control DataGrid en el diseñador

1. En el cuadro **miembros** del **Editor de colecciones DataGridTableStyle**, seleccione el estilo de tabla adecuado. En el cuadro **propiedades** del editor de la colección, seleccione la colección de <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> y, a continuación, haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) del ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) junto a la propiedad para mostrar el editor de la **colección DataGridColumnStyle**.

2. En el editor de la colección, haga clic en **Agregar** para insertar un estilo de columna o haga clic en la flecha hacia abajo situada junto a **Agregar** para especificar un tipo de columna.

     En el cuadro desplegable, puede seleccionar el tipo <xref:System.Windows.Forms.DataGridTextBoxColumn> o <xref:System.Windows.Forms.DataGridBoolColumn>.

3. Haga clic en Aceptar para cerrar el editor de la **colección DataGridColumnStyle**y, a continuación, vuelva a abrirlo haciendo clic en el botón de puntos suspensivos junto a la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.

     Cuando vuelva a abrir el editor de la colección, todas las columnas de datos de la tabla de datos enlazados aparecerán en la lista desplegable de la propiedad <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> del estilo de columna.

4. En el cuadro **miembros** del editor de colecciones, haga clic en el estilo de columna.

5. En el cuadro **propiedades** del editor de la colección, seleccione el valor <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> de la columna que desea mostrar.

## <a name="see-also"></a>Vea también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
