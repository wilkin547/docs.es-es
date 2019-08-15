---
title: Procedimiento para establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], cell styles
- cells [Windows Forms], setting styles
- data formats
- data [Windows Forms], setting formats
ms.assetid: fc6da49f-8942-41da-b49f-b2afc38cc656
ms.openlocfilehash: 53faf31c8dd3be1606c491e95594c4aae5aedf98
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039670"
---
# <a name="how-to-set-default-cell-styles-and-data-formats-for-the-windows-forms-datagridview-control-using-the-designer"></a>Procedimiento para establecer estilos de celdas y formatos de datos predeterminados en el control DataGridView de formularios Windows Forms mediante el diseñador

El <xref:System.Windows.Forms.DataGridView> control permite especificar los estilos de celda y los formatos de datos de celda predeterminados para todo el control, para las columnas específicas, para los encabezados de fila y de columna, y para las filas alternas para crear un efecto de libro. Los estilos predeterminados establecidos para todo el control se reemplazan por los estilos predeterminados establecidos para las columnas y las filas alternas. Además, los estilos que se establecen en el código para filas y celdas individuales reemplazan los estilos predeterminados.

Para obtener más información sobre los estilos de celda, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md). Para establecer estilos para filas alternas, vea [cómo: Establezca estilos de fila alternos para el control DataGridView Windows Forms mediante el](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)diseñador.

También puede establecer estilos mediante la <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad para que afecten a todas las filas que se van a agregar al control. Para obtener más información acerca de la plantilla de [fila, consulte How to: Use la plantilla de filas para personalizar las filas en el control](use-the-row-template-to-customize-rows-in-the-datagrid.md)DataGridView Windows Forms.

Los procedimientos siguientes requieren un proyecto de **aplicación Windows** con un formulario que <xref:System.Windows.Forms.DataGridView> contenga un control. Para obtener información acerca de cómo configurar este tipo de [proyecto, consulte Cómo: Cree un proyecto](/visualstudio/ide/step-1-create-a-windows-forms-application-project) de aplicación de [Windows Forms y cómo: Agregue controles a Windows Forms](how-to-add-controls-to-windows-forms.md).


### <a name="to-set-default-styles-for-all-cells-in-the-control"></a>Para establecer estilos predeterminados para todas las celdas del control

1. Seleccione el <xref:System.Windows.Forms.DataGridView> control en el diseñador.

2. En la **ventana Propiedades** , haga clic en el botón![de puntos suspensivos (el botón de puntos suspensivos (...) del ventana Propiedades de Visual Studio <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A>. <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A>](./media/visual-studio-ellipsis-button.png)) situado <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> junto a la propiedad, o. Aparecerá el cuadro de diálogo **generador de CellStyle** .

3. Defina el estilo estableciendo las propiedades mediante el panel de **vista previa** para confirmar las opciones.

> [!NOTE]
> Si los estilos visuales están habilitados, los encabezados de fila y de columna ( <xref:System.Windows.Forms.DataGridView.TopLeftHeaderCell%2A>excepto para) se aplican automáticamente de estilo al tema actual, <xref:System.Windows.Forms.DataGridView.ColumnHeadersDefaultCellStyle%2A> invalidando los valores de las propiedades y <xref:System.Windows.Forms.DataGridView.RowHeadersDefaultCellStyle%2A> .
>
> Puede establecer estilos de celda para varios controles <xref:System.Windows.Forms.DataGridView> seleccionados mediante el diseñador, pero solo si tienen valores idénticos para la propiedad de estilo de celda que desea modificar. Si hay algún estilo de celda distinto para esa propiedad, las ventanas **propiedades** del cuadro de diálogo **generador de CellStyle** estarán en blanco.

### <a name="to-set-default-styles-for-cells-in-individual-columns"></a>Para establecer estilos predeterminados para las celdas de columnas individuales

1. Haga clic con el <xref:System.Windows.Forms.DataGridView> botón secundario en el control en el diseñador y elija **Editar columnas**.

2. Seleccione una columna de la lista **columnas seleccionadas** .

3. En la **cuadrícula propiedades de columna** , haga clic en el![botón de puntos suspensivos (el botón de puntos suspensivos (...) en el ventana Propiedades de <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A> Visual Studio.](./media/visual-studio-ellipsis-button.png)) situado junto a la propiedad. Aparecerá el cuadro de diálogo **generador de CellStyle** .

4. Defina el estilo estableciendo las propiedades mediante el panel de **vista previa** para confirmar las opciones.

### <a name="to-format-data-in-cells"></a>Para dar formato a los datos de las celdas

1. Use uno de los procedimientos anteriores para mostrar un cuadro de diálogo **generador de CellStyle** relacionado con una propiedad de estilo de celda predeterminada.

2. En el cuadro de diálogo **generador de CellStyle** , haga clic en![el botón de puntos suspensivos (el botón de puntos suspensivos (...](./media/visual-studio-ellipsis-button.png)) en el ventana propiedades <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A> de Visual Studio.) situado junto a la propiedad. Aparecerá el cuadro de diálogo **cadena de formato** .

3. Seleccione un tipo de formato y, a continuación, modifique los detalles del tipo (por ejemplo, el número de posiciones decimales que se van a mostrar), mediante el cuadro **ejemplo** para confirmar las opciones.

4. Si va a enlazar <xref:System.Windows.Forms.DataGridView> el control a un origen de datos que probablemente contenga valores NULL, rellene el cuadro de texto **valor nulo** . Este valor se muestra cuando el valor de la celda es igual a una referencia`Nothing` nula (en Visual Basic <xref:System.DBNull.Value?displayProperty=nameWithType>) o.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewCellStyle>
- <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.RowsDefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.DefaultCellStyle%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCellStyle.Format%2A?displayProperty=nameWithType>
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer estilos de fila alternos para el control DataGridView Windows Forms mediante el diseñador](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)
- [Procedimientos: Crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md)
