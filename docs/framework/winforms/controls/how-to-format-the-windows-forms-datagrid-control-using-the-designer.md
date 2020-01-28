---
title: Dar formato al control DataGrid mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: 548acac0fc7724490bfe89927ec0662b3488c230
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736795"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Cómo: Dar formato al control DataGrid de formularios Windows Forms mediante el Diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).

Aplicar distintos colores a varias partes de un control de <xref:System.Windows.Forms.DataGrid> puede ayudar a facilitar la lectura y la interpretación de la información. El color se puede aplicar a filas y columnas. Las filas y columnas también se pueden ocultar o mostrar a su discreción.

Hay tres aspectos básicos del formato del control <xref:System.Windows.Forms.DataGrid>:

- Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos.

- A partir de esa base, puede personalizar la forma en que se muestran ciertas tablas en tiempo de ejecución.

- Por último, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otros formatos que se muestran.

Como paso inicial para dar formato a una cuadrícula de datos, puede establecer las propiedades del propio <xref:System.Windows.Forms.DataGrid>. Estas opciones de color y formato forman una base de la que puede realizar cambios en función de las tablas de datos y las columnas que se muestran.

El procedimiento siguiente requiere un proyecto de **aplicación Windows** con un formulario que contenga un control <xref:System.Windows.Forms.DataGrid>. Para obtener información sobre cómo configurar este tipo de proyecto, vea [Cómo: crear un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el control <xref:System.Windows.Forms.DataGrid> no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, vea [Cómo: agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Para establecer un estilo predeterminado para el control DataGrid

1. Seleccione el control <xref:System.Windows.Forms.DataGrid>.

2. En la ventana **propiedades** , establezca las siguientes propiedades, según corresponda.

    |La propiedad|Descripción|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|La propiedad `BackColor` define el color de las filas pares de la cuadrícula. Al establecer la propiedad <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> en un color diferente, todas las demás filas se establecen en este nuevo color (filas 1, 3, 5, etc.).|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|Color de fondo de las filas pares de la cuadrícula (filas 0, 2, 4, 6, etc.).|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que las propiedades <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> determinan el color de las filas de la cuadrícula, la propiedad <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> determina el color del área fuera del área de fila, que solo está visible cuando la cuadrícula se desplaza hasta la parte inferior o si solo unas pocas filas están contenidas en la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Estilo de borde de la cuadrícula, uno de los valores de enumeración de <xref:System.Windows.Forms.BorderStyle>.|
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|Color de fondo del título de la ventana de la cuadrícula que aparece justo encima de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|Fuente del título en la parte superior de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|Color de fondo del título de la ventana de la cuadrícula.|
    |<xref:System.Windows.Forms.Control.Font%2A>|Fuente utilizada para mostrar el texto en la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|Color de la fuente que muestran los datos de las filas de la cuadrícula de datos.|
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|Color de las líneas de cuadrícula de la cuadrícula de datos.|
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|Estilo de las líneas que separan las celdas de la cuadrícula, uno de los valores de enumeración de <xref:System.Windows.Forms.DataGridLineStyle>.|
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|Color de fondo de los encabezados de fila y de columna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|Fuente utilizada para los encabezados de columna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|Color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y los glifos del signo más (+) y del signo menos (-) que expanden y contraen las filas cuando se muestran varias tablas relacionadas.|
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|Color del texto de todos los vínculos de la cuadrícula de datos, incluidos los vínculos a las tablas secundarias, el nombre de la relación, etc.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, es el color de fondo de las filas primarias.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, es el color de primer plano de las filas primarias.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y de columna se muestran en la fila primaria, por medio de la enumeración <xref:System.Windows.Forms.DataGridParentRowsLabelStyle>.|
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado (en píxeles) de las columnas de la cuadrícula. Establezca esta propiedad antes de restablecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> (por separado, o a través del método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>) o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|Alto de fila (en píxeles) de las filas de la cuadrícula. Establezca esta propiedad antes de restablecer las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> (por separado, o a través del método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>) o la propiedad no tendrá ningún efecto.<br /><br /> La propiedad no se puede establecer en un valor menor que 0.|
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|Ancho de los encabezados de fila de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una fila o celda, este es el color de fondo.|
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una fila o celda, este es el color de primer plano.|

    > [!NOTE]
    > Cuando se personalizan los colores de los controles, es posible hacer que el control sea inaccesible debido a una mala elección de color (por ejemplo, rojo y verde). Use los colores disponibles en la paleta de **colores del sistema** para evitar este problema.

    El procedimiento siguiente requiere un control de <xref:System.Windows.Forms.DataGrid> enlazado a una tabla de datos. Para obtener más información, vea [Cómo: enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Para establecer el estilo de tabla y columna de una tabla de datos en tiempo de diseño

1. Seleccione el control de <xref:System.Windows.Forms.DataGrid> en el formulario.

2. En la ventana **propiedades** , seleccione la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> y haga clic en los **puntos suspensivos** (![el botón de puntos suspensivos (...) en el botón ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)).

3. En el cuadro de diálogo Editor de la **colección DataGridTableStyle** , haga clic en **Agregar** para agregar un estilo de tabla a la colección.

     Con el **Editor de la colección DataGridTableStyle**, puede Agregar y quitar estilos de tabla, establecer las propiedades de presentación y diseño, y establecer el nombre de asignación para los estilos de tabla.

4. Establezca la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> en el nombre de asignación para cada estilo de tabla.

     El nombre de la asignación se utiliza para especificar qué estilo de tabla se debe utilizar con cada tabla.

5. En el **Editor de la colección DataGridTableStyle**, seleccione la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> y haga clic en el botón de puntos suspensivos (![el botón de puntos suspensivos (...) en el ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)).

6. En el cuadro de diálogo Editor de la **colección DataGridColumnStyle** , agregue estilos de columna al estilo de tabla que ha creado.

     Con el **Editor de la colección DataGridColumnStyle**, puede Agregar y quitar estilos de columna, establecer las propiedades de presentación y diseño, y establecer el nombre de asignación y las cadenas de formato para las columnas de datos.

    > [!NOTE]
    > Para obtener más información sobre las cadenas de formato, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Cómo: Eliminar u ocultar columnas del control DataGrid de formularios Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
