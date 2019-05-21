---
title: Procedimiento para dar formato al control DataGrid de formularios Windows Forms mediante el diseñador
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], DataGrid controls
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: 533b9814-6124-49dc-9fda-085f1502609f
ms.openlocfilehash: 1cdafa14d5b25d6cef92a48e4f460975a2076303
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2019
ms.locfileid: "65960197"
---
# <a name="how-to-format-the-windows-forms-datagrid-control-using-the-designer"></a>Procedimiento para dar formato al control DataGrid de formularios Windows Forms mediante el diseñador

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

Aplicar colores diferentes para distintas partes de un <xref:System.Windows.Forms.DataGrid> control puede ayudar a que la información sea más fácil leer e interpretar. Color puede aplicarse a las filas y columnas. Las filas y columnas también se oculta o se muestra a su entera discreción.

Hay tres aspectos básicos del formato el <xref:System.Windows.Forms.DataGrid> control:

- Puede establecer propiedades para establecer un estilo predeterminado en el que se muestran los datos.

- Desde esa base, a continuación, puede personalizar la manera en que se muestren determinadas tablas en tiempo de ejecución.

- Por último, puede modificar las columnas que se muestran en la cuadrícula de datos, así como los colores y otras opciones de formato se muestra.

Como paso inicial para dar formato a una cuadrícula de datos, puede establecer las propiedades de la <xref:System.Windows.Forms.DataGrid> propio. Estas opciones de color y el formato forman una base desde la que puede realizar, a continuación, cambia en función de las tablas de datos y las columnas mostradas.

El procedimiento siguiente requiere una **aplicación Windows** proyecto con un formulario que contenga un <xref:System.Windows.Forms.DataGrid> control. Para obtener información acerca de cómo configurar un proyecto de este tipo, vea [Cómo: Cree un proyecto de aplicación de Windows Forms](/visualstudio/ide/step-1-create-a-windows-forms-application-project) y [Cómo: Agregar controles a Windows Forms](how-to-add-controls-to-windows-forms.md). En Visual Studio 2005, el <xref:System.Windows.Forms.DataGrid> control no está en el **cuadro de herramientas** de forma predeterminada. Para obtener más información, vea [Cómo: Agregar elementos al cuadro de herramientas](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).

> [!NOTE]
> Los cuadros de diálogo y comandos de menú que se ven pueden diferir de los descritos en la Ayuda, en función de los valores de configuración o de edición activos. Para cambiar la configuración, elija la opción **Importar y exportar configuraciones** del menú **Herramientas** . Para más información, vea [Personalizar el IDE de Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).

### <a name="to-establish-a-default-style-for-the-datagrid-control"></a>Para establecer un estilo predeterminado para el control DataGrid

1. Seleccione el control <xref:System.Windows.Forms.DataGrid>.

2. En el **propiedades** ventana, establezca las propiedades siguientes, según corresponda.

    |Propiedad|Descripción|
    |--------------|-----------------|
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|El `BackColor` propiedad define el color de las filas impares de la cuadrícula. Al establecer el <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedad a un color diferente, todas las demás filas se establece en este nuevo color (filas 1, 3, 5 y así sucesivamente).|
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|El color de fondo de las filas impares de la cuadrícula (filas 0, 2, 4, 6 y así sucesivamente).|
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|Mientras que la <xref:System.Windows.Forms.DataGrid.BackColor%2A> y <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> propiedades determinan el color de las filas de la cuadrícula, la <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> propiedad determina el color del área fuera del área de fila, que solo está visible cuando la cuadrícula se desplaza hasta la parte inferior, o si sólo son unas pocas filas contenida en la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|Estilo de borde de la cuadrícula, uno de los <xref:System.Windows.Forms.BorderStyle> valores de enumeración.|
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|El color de fondo del título de ventana de la cuadrícula que aparece justo encima de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|La fuente del título en la parte superior de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|El color de fondo del título de ventana de la cuadrícula.|
    |<xref:System.Windows.Forms.Control.Font%2A>|La fuente utilizada para mostrar el texto en la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|El color de la fuente que aparecen en los datos de las filas de la cuadrícula de datos.|
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|El color de las líneas de cuadrícula de la cuadrícula de datos.|
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|El estilo de las líneas que separan las celdas de la cuadrícula, uno de los <xref:System.Windows.Forms.DataGridLineStyle> valores de enumeración.|
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|El color de fondo de los encabezados de fila y columna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|La fuente utilizada para los encabezados de columna.|
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|El color de primer plano de los encabezados de columna de la cuadrícula, incluido el texto del encabezado de columna y el signo más (+) y signo menos (-) glifos que se expanden y contraen filas cuando varias tablas relacionadas se muestran.|
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|El color del texto de todos los vínculos en la cuadrícula de datos, incluidos los vínculos a las tablas secundarias, el nombre de la relación y así sucesivamente.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|En una tabla secundaria, este es el color de fondo de las filas primarias.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|En una tabla secundaria, este es el color de primer plano de las filas primarias.|
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|Determina si los nombres de tabla y columna se muestran en la fila primaria, por medio de la <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeración.|
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|Ancho predeterminado (en píxeles) de las columnas de la cuadrícula. Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.<br /><br /> No se puede establecer la propiedad en un valor menor que 0.|
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|El alto de fila (en píxeles) de filas en la cuadrícula. Establezca esta propiedad antes de restablecer la <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> propiedades (ya sea por separado, o a través del <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> método), o la propiedad no tiene ningún efecto.<br /><br /> No se puede establecer la propiedad en un valor menor que 0.|
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|El ancho de los encabezados de fila de la cuadrícula.|
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|Cuando se selecciona una celda o fila, este es el color de fondo.|
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|Cuando se selecciona una celda o fila, este es el color de primer plano.|

    > [!NOTE]
    > Si desea personalizar los colores de los controles, es posible que el control sea inaccesible debido a la elección de color deficiente (por ejemplo, rojo y verde). Utilice los colores disponibles en el **colores del sistema** paleta para evitar este problema.

    El procedimiento siguiente requiere una <xref:System.Windows.Forms.DataGrid> control enlazado a una tabla de datos. Para obtener más información, vea [Cómo: Enlazar el Control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

### <a name="to-set-the-table-and-column-style-of-a-data-table-at-design-time"></a>Para establecer el estilo de tabla y columna de una tabla de datos en tiempo de diseño

1. Seleccione el <xref:System.Windows.Forms.DataGrid> control en el formulario.

2. En el **propiedades** ventana, seleccione el <xref:System.Windows.Forms.DataGrid.TableStyles%2A> propiedad y haga clic en el **puntos suspensivos** (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)) botón.

3. En el **Editor de colección DataGridTableStyle** cuadro de diálogo, haga clic en **agregar** para agregar un estilo de tabla a la colección.

     Con el **Editor de colección DataGridTableStyle**, puede agregar y quitar los estilos de tabla, para mostrar del conjunto y las propiedades de diseño y conjunto la asignación de nombre de los estilos de tabla.

4. Establecer el <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> propiedad en el nombre de asignación para cada estilo de tabla.

     El nombre de asignación se utiliza para especificar el estilo de tabla que se debe usar con la tabla.

5. En el **Editor de colección DataGridTableStyle**, seleccione el <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> propiedad y haga clic en el botón de puntos suspensivos (![los puntos suspensivos (...) en la ventana Propiedades de Visual Studio.](./media/visual-studio-ellipsis-button.png)).

6. En el **Editor de colecciones DataGridColumnStyle** diálogo cuadro, agregar estilos de columna para el estilo de tabla que creó.

     Con el **Editor de colecciones DataGridColumnStyle**, puede agregar y quitar estilos de columna, establecer las propiedades de presentación y diseño y establecer el nombre de asignación y las cadenas de formato para los datos de columnas.

    > [!NOTE]
    > Para obtener más información acerca de las cadenas de formato, vea [aplicar formato a tipos](../../../standard/base-types/formatting-types.md).

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [Cómo: Eliminar u ocultar columnas en el Control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [DataGrid (control)](datagrid-control-windows-forms.md)
