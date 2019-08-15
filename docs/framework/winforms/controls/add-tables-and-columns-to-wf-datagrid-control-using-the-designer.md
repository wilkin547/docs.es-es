---
title: Procedimiento para agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 4a6d1b34-b696-476b-bf8a-57c6230aa9e1
ms.openlocfilehash: d11c4f7e4cdfb597477bb99f38612ed648849f20
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040053"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control-using-the-designer"></a>Procedimiento para agregar tablas y columnas al control DataGrid de formularios Windows Forms mediante el diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

Puede mostrar los datos en el control <xref:System.Windows.Forms.DataGrid> Windows Forms en las tablas y columnas creando <xref:System.Windows.Forms.DataGridTableStyle> objetos <xref:System.Windows.Forms.GridTableStylesCollection> y agregándolos al objeto, al que se tiene acceso a través de <xref:System.Windows.Forms.DataGrid> la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control. Cada estilo de tabla muestra el contenido de la tabla de datos especificada en <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> la propiedad <xref:System.Windows.Forms.DataGridTableStyle>de. De forma predeterminada, un estilo de tabla sin estilos de columna especificados mostrará todas las columnas de esa tabla de datos. Puede restringir las <xref:System.Windows.Forms.DataGridColumnStyle> columnas de la tabla agregando objetos <xref:System.Windows.Forms.GridColumnStylesCollection>a, al que se tiene acceso a través de <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> la propiedad de <xref:System.Windows.Forms.DataGridTableStyle>cada una de ellas.

Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control. Para obtener información sobre cómo configurar este tipo de proyecto, consulte [cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md). De forma predeterminada, en Visual Studio 2005 <xref:System.Windows.Forms.DataGrid> , el control no está en el **cuadro de herramientas**. Para obtener información acerca de cómo agregarlo, consulte [cómo: Agregar elementos al cuadro de](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))herramientas.

### <a name="to-add-a-table-to-the-datagrid-control-in-the-designer"></a>Para agregar una tabla al control DataGrid en el diseñador

1. Para mostrar los datos en la tabla, primero debe enlazar el <xref:System.Windows.Forms.DataGrid> control a un conjunto de datos. Para obtener más información, vea [Cómo: Enlazar el control DataGrid de Windows Forms a un origen de datos](bind-wf-datagrid-control-to-a-data-source-using-the-designer.md)mediante el diseñador.

2. Seleccione la <xref:System.Windows.Forms.DataGrid> propiedad del <xref:System.Windows.Forms.DataGrid.TableStyles%2A> control en el ventana Propiedades y, a continuación, haga clic en![el botón de puntos suspensivos (el botón de puntos suspensivos (...](./media/visual-studio-ellipsis-button.png)) en el ventana Propiedades de Visual Studio.) junto a la propiedad para mostrar el **Editor de la colección DataGridTableStyle**.

3. En el editor de la colección, haga clic en **Agregar** para insertar un estilo de tabla.

4. Haga clic en **Aceptar** para cerrar el editor de la colección y, a continuación, vuelva a abrirlo haciendo <xref:System.Windows.Forms.DataGrid.TableStyles%2A> clic en el botón de puntos suspensivos junto a la propiedad.

     Al volver a abrir el editor de la colección, todas las tablas de datos enlazadas al control aparecerán en la lista desplegable <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de la propiedad del estilo de tabla.

5. En el cuadro **miembros** del editor de colecciones, haga clic en el estilo de tabla.

6. En el cuadro **propiedades** del editor de la colección, seleccione <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> el valor de la tabla que desea mostrar.

### <a name="to-add-a-column-to-the-datagrid-control-in-the-designer"></a>Para agregar una columna al control DataGrid en el diseñador

1. En el cuadro **miembros** del **Editor de colecciones DataGridTableStyle**, seleccione el estilo de tabla adecuado. En el cuadro **propiedades** del editor de la colección, seleccione <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> la colección y, a continuación, haga clic![en el botón de puntos suspensivos (el botón de puntos suspensivos (..](./media/visual-studio-ellipsis-button.png).) en el ventana Propiedades de Visual Studio.) junto a la propiedad en muestre el **Editor de la colección DataGridColumnStyle**.

2. En el editor de la colección, haga clic en **Agregar** para insertar un estilo de columna o haga clic en la flecha hacia abajo situada junto a **Agregar** para especificar un tipo de columna.

     En el cuadro desplegable, puede seleccionar el <xref:System.Windows.Forms.DataGridTextBoxColumn> tipo o. <xref:System.Windows.Forms.DataGridBoolColumn>

3. Haga clic en Aceptar para cerrar el editor de la **colección DataGridColumnStyle**y, a continuación, vuelva a abrirlo haciendo <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> clic en el botón de puntos suspensivos junto a la propiedad.

     Cuando vuelva a abrir el editor de la colección, todas las columnas de datos de la tabla de datos enlazados aparecerán en la lista <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> desplegable de la propiedad del estilo de columna.

4. En el cuadro **miembros** del editor de colecciones, haga clic en el estilo de columna.

5. En el cuadro **propiedades** del editor de la colección, seleccione <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> el valor de la columna que desea mostrar.

## <a name="see-also"></a>Vea también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Cómo: Eliminar u ocultar columnas en el control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
