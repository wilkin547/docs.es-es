---
title: Información general del control DataGrid
ms.date: 03/30/2017
f1_keywords:
- DataGrid
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- columns [Windows Forms], DataGrid control
- data sources [Windows Forms], binding to DataGrid control
- tables [Windows Forms], binding to DataGrid control
- DataGrid control [Windows Forms], data binding
- DataGrid control [Windows Forms], about DataGrid control
- parent tables in DataGrid control
- tables [Windows Forms], displaying in DataGrid control
- data grids [Windows Forms], about data grids
- multiple tables in DataGrid control
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- parent table navigation in DataGrid
- child tables [Windows Forms], dataGrid control
ms.assetid: 85604bce-bc03-49d9-9030-dda8896c44b1
ms.openlocfilehash: df559926dbc9141276f0a03deb99e340fd7212da
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742568"
---
# <a name="datagrid-control-overview-windows-forms"></a>Información general del control DataGrid (Formularios Windows Forms)

> [!NOTE]
> El control <xref:System.Windows.Forms.DataGridView> reemplaza y agrega funcionalidad al control <xref:System.Windows.Forms.DataGrid>; sin embargo, el control <xref:System.Windows.Forms.DataGrid> se conserva a efectos de compatibilidad con versiones anteriores y uso futuro, en su caso. Para obtener más información, consulte [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md) (Diferencias entre los controles DataGridView y DataGrid de formularios Windows Forms).

El control <xref:System.Windows.Forms.DataGrid> de Windows Forms muestra los datos en una serie de filas y columnas. El caso más simple es cuando la cuadrícula está enlazada a un origen de datos con una sola tabla que no contiene relaciones. En ese caso, los datos aparecen en simples filas y columnas, como en una hoja de cálculo. Para obtener más información sobre cómo enlazar datos a otros controles, vea el artículo sobre [enlace de datos y formularios Windows Forms](../data-binding-and-windows-forms.md).

Si <xref:System.Windows.Forms.DataGrid> está enlazado a datos con varias tablas relacionadas, y si la navegación está habilitada en la cuadrícula, la cuadrícula mostrará expansores en cada fila. Con un expansor, el usuario puede pasar de una tabla primaria a una tabla secundaria. Al hacer clic en un nodo se muestra la tabla secundaria y al hacer clic en un botón de retroceso se muestra la tabla primaria original. De esta manera, la cuadrícula muestra las relaciones jerárquicas entre tablas.

En la captura de pantalla siguiente se muestra un control DataGrid enlazado a datos con varias tablas:

![Aplicación de WinForms que muestra un control DataGrid enlazado a datos con varias tablas.](./media/datagrid-control-overview-windows-forms/datagrid-bound-multiple-tables.gif)

<xref:System.Windows.Forms.DataGrid> puede proporcionar una interfaz de usuario para un conjunto de datos, navegación entre tablas relacionadas, formato enriquecido y capacidades de edición.

La presentación y manipulación de datos son funciones independientes: El control administra la interfaz de usuario, mientras que las actualizaciones de datos se controlan mediante el Windows Forms la arquitectura de enlace de datos y los proveedores de datos de .NET Framework. Por lo tanto, si hay varios controles enlazados al mismo origen de datos, estarán sincronizados.

> [!NOTE]
> Si está familiarizado con el control DataGrid en Visual Basic 6.0, encontrará algunas diferencias significativas en el control <xref:System.Windows.Forms.DataGrid> de Windows Forms.

Cuando la cuadrícula está enlazada a un <xref:System.Data.DataSet>, las columnas y filas se crean, se les aplica formato y se rellenan automáticamente. Para obtener más información, consulta [Data Binding and Windows Forms](../data-binding-and-windows-forms.md). Después generar el control <xref:System.Windows.Forms.DataGrid>, puede agregar, eliminar, reorganizar y dar formato a las columnas y filas según sus necesidades.

## <a name="binding-data-to-the-control"></a>Enlazar datos al control

Para que el control <xref:System.Windows.Forms.DataGrid> funcione, debe enlazarse a un origen de datos mediante las propiedades <xref:System.Windows.Forms.DataGrid.DataSource%2A> y <xref:System.Windows.Forms.DataGrid.DataMember%2A> en tiempo de diseño o el método <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> en tiempo de ejecución. Este enlace apunta el control <xref:System.Windows.Forms.DataGrid> a un objeto de origen de datos con instancias, como un <xref:System.Data.DataSet> o <xref:System.Data.DataTable>). El control <xref:System.Windows.Forms.DataGrid> muestra los resultados de las acciones que se realizan en los datos. Las acciones más específicas de los datos no se realizan a través de <xref:System.Windows.Forms.DataGrid>, sino a través del origen de datos.

Si los datos del conjunto de datos enlazado se actualizan mediante cualquier mecanismo, el control <xref:System.Windows.Forms.DataGrid> refleja los cambios. Si la cuadrícula de datos y sus estilos de tabla y estilos de columna tienen la propiedad `ReadOnly` establecida en `false`, los datos del conjunto de datos se pueden actualizar a través del control <xref:System.Windows.Forms.DataGrid>.

Tan solo se puede mostrar una tabla en <xref:System.Windows.Forms.DataGrid> a la vez. Si se define una relación primaria-secundaria entre las tablas, el usuario puede desplazarse entre las tablas relacionadas para seleccionar la tabla que se mostrará en el control <xref:System.Windows.Forms.DataGrid>. Para obtener información sobre cómo enlazar un control de <xref:System.Windows.Forms.DataGrid> a un origen de datos de ADO.NET en tiempo de diseño o en tiempo de ejecución, vea [How to: Enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).

Los orígenes de datos válidos para <xref:System.Windows.Forms.DataGrid> son:

- Clase <xref:System.Data.DataTable>

- Clase <xref:System.Data.DataView>

- Clase <xref:System.Data.DataSet>

- Clase <xref:System.Data.DataViewManager>

Si su origen es un conjunto de datos, el conjunto de datos podría ser un objeto en el formulario o un objeto pasado al formulario por un servicio web XML. Puede enlazar a conjuntos de datos con tipo o sin tipo.

También puede enlazar un control <xref:System.Windows.Forms.DataGrid> a estructuras adicionales si los objetos de la estructura, como los elementos de una matriz, exponen propiedades públicas. La cuadrícula mostrará todas las propiedades públicas de los elementos de la estructura. Por ejemplo, si enlaza el control <xref:System.Windows.Forms.DataGrid> a una matriz de objetos customer, la cuadrícula mostrará todas las propiedades públicas de esos objetos customer. En algunas instancias esto significa que, aunque se puede enlazar con la estructura, la estructura enlazada resultante podría no tener aplicación práctica. Por ejemplo, se puede enlazar a una matriz de enteros, pero dado que el tipo de datos `Integer` no admite una propiedad pública, la cuadrícula no puede mostrar los datos.

Las siguientes estructuras se pueden enlazar si sus elementos exponen propiedades públicas:

- Cualquier componente que implemente la interfaz <xref:System.Collections.IList>. Esto incluye las matrices unidimensionales.

- Cualquier componente que implemente la interfaz <xref:System.ComponentModel.IListSource>.

- Cualquier componente que implemente la interfaz <xref:System.ComponentModel.IBindingList>.

 Para obtener más información sobre posibles orígenes de datos, vea el artículo sobre los [orígenes de datos compatibles con formularios Windows Forms](../data-sources-supported-by-windows-forms.md).

## <a name="grid-display"></a>Visualización de la cuadrícula

Un uso común del control <xref:System.Windows.Forms.DataGrid> es mostrar una única tabla de datos de un conjunto de datos. Sin embargo, el control también puede usarse para mostrar varias tablas, incluidas tablas relacionadas. La presentación de la cuadrícula se ajusta automáticamente conforme al origen de datos. En la tabla siguiente se indica lo que se muestra según las diferentes configuraciones.

|Contenido del conjunto de datos|Qué se muestra|
|--------------------------|-----------------------|
|Tabla única.|La tabla se muestra en una cuadrícula.|
|Varias tablas.|La cuadrícula puede mostrar una vista de árbol por la que los usuarios pueden desplazarse para localizar la tabla que desean mostrar.|
|Varias tablas relacionadas.|La cuadrícula puede mostrar una vista de árbol para seleccionar las tablas, o usted puede especificar que la cuadrícula muestre la tabla primaria. Los registros de la tabla primaria permiten a los usuarios desplazarse a las filas secundarias relacionadas.|

> [!NOTE]
> Las tablas de un conjunto de datos se relacionan mediante <xref:System.Data.DataRelation>. Vea también [crear relaciones entre conjuntos de valores](/visualstudio/data-tools/relationships-in-datasets).

Cuando el control <xref:System.Windows.Forms.DataGrid> muestra una tabla y la propiedad <xref:System.Windows.Forms.DataGrid.AllowSorting%2A> se establece en `true`, los datos se pueden volver a ordenar haciendo clic en los encabezados de columna. El usuario también puede agregar filas y modificar celdas.

Las relaciones entre un conjunto de tablas se muestran a los usuarios con una estructura de elementos primarios y secundarios de navegación. Las tablas primarias son el nivel más alto de los datos y las tablas secundarias son las tablas de datos que se derivan de los listados individuales de las tablas primarias. Los expansores se muestran en cada fila primaria que contiene una tabla secundaria. Al hacer clic en un expansor, se genera una lista de vínculos de tipo web a las tablas secundarias. Cuando el usuario selecciona un vínculo, se muestra la tabla secundaria. Haga clic en el icono Mostrar u ocultar filas principales (![Icono Mostrar u ocultar filas principales](./media/datagrid-control-overview-windows-forms/show-hide-parent-rows.gif)) ocultará la información sobre la tabla primaria o hará que vuelva a aparecer si el usuario la ocultó anteriormente. El usuario puede hacer clic en un botón Atrás para volver a la tabla mostrada previamente.

## <a name="columns-and-rows"></a>Columnas y filas

<xref:System.Windows.Forms.DataGrid> consta de una colección de objetos <xref:System.Windows.Forms.DataGridTableStyle> que se encuentran en la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control <xref:System.Windows.Forms.DataGrid>. Un estilo de tabla puede contener una colección de objetos <xref:System.Windows.Forms.DataGridColumnStyle> que se encuentran en la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> de <xref:System.Windows.Forms.DataGridTableStyle>. Puede editar las propiedades <xref:System.Windows.Forms.DataGrid.TableStyles%2A> y <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> mediante los editores de colección a los que se tiene acceso a través de la ventana **propiedades** .

Cualquier <xref:System.Windows.Forms.DataGridTableStyle> asociado con el control <xref:System.Windows.Forms.DataGrid> puede tener acceso mediante <xref:System.Windows.Forms.GridTableStylesCollection>. <xref:System.Windows.Forms.GridTableStylesCollection> se puede editar en el diseñador con el editor de colección <xref:System.Windows.Forms.DataGridTableStyle>, o mediante programación a través de la propiedad <xref:System.Windows.Forms.DataGrid.TableStyles%2A> del control <xref:System.Windows.Forms.DataGrid>.

En la ilustración siguiente se muestran los objetos incluidos en el control DataGrid:

![Diagrama que muestra los objetos incluidos en el control DataGrid.](./media/datagrid-control-overview-windows-forms/visual-basic-columns.gif)

Los estilos de tabla y columna se sincronizan con objetos <xref:System.Data.DataTable> y objetos <xref:System.Data.DataColumn> al establecer sus propiedades `MappingName` en las propiedades <xref:System.Data.DataTable.TableName%2A> y <xref:System.Data.DataColumn.ColumnName%2A> correspondientes. Cuando un <xref:System.Windows.Forms.DataGridTableStyle> que no tiene estilos de columna se agrega a un control <xref:System.Windows.Forms.DataGrid> enlazado a un origen de datos válido y la propiedad <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> de ese estilo de tabla se establece en una propiedad <xref:System.Data.DataTable.TableName%2A> válida, se crea una colección de objetos <xref:System.Windows.Forms.DataGridColumnStyle> para ese estilo de tabla. Por cada <xref:System.Data.DataColumn> encontrado en la colección <xref:System.Data.DataTable.Columns%2A> de <xref:System.Data.DataTable>, se agrega un <xref:System.Windows.Forms.DataGridColumnStyle> correspondiente al <xref:System.Windows.Forms.GridColumnStylesCollection>. El acceso a <xref:System.Windows.Forms.GridColumnStylesCollection> se realiza mediante la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A> de <xref:System.Windows.Forms.DataGridTableStyle>. Las columnas se pueden agregar o eliminar desde la cuadrícula mediante el método <xref:System.Windows.Forms.GridColumnStylesCollection.Add%2A> o <xref:System.Windows.Forms.GridColumnStylesCollection.Remove%2A> en <xref:System.Windows.Forms.GridColumnStylesCollection>. Para obtener más información, vea [Cómo: Agregue tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md) y [cómo: Eliminar u ocultar columnas en el control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md).

Una colección de tipos de columna extiende la clase <xref:System.Windows.Forms.DataGridColumnStyle> con formato enriquecido y capacidades de edición. Todos los tipos de columna se heredan de la clase base <xref:System.Windows.Forms.DataGridColumnStyle>. La clase que se crea depende de la propiedad <xref:System.Data.DataColumn.DataType%2A> del objeto <xref:System.Data.DataColumn> en el que se basa <xref:System.Web.UI.WebControls.DataGridColumn>. Por ejemplo, un <xref:System.Data.DataColumn> que tiene su propiedad <xref:System.Data.DataColumn.DataType%2A> establecida en <xref:System.Boolean> se asociará con <xref:System.Windows.Forms.DataGridBoolColumn>. En la siguiente tabla se describe cada uno de estos tipos de columna.

|Tipo de columna|Descripción|
|-----------------|-----------------|
|<xref:System.Windows.Forms.DataGridTextBoxColumn>|Acepta y muestra los datos como cadenas con o sin formato. Las capacidades de edición son las mismas que se usan para modificar los datos de un <xref:System.Windows.Forms.TextBox> simple. Se hereda de <xref:System.Windows.Forms.DataGridColumnStyle>.|
|<xref:System.Windows.Forms.DataGridBoolColumn>|Acepta y muestra `true`, `false` y valores null. Se hereda de <xref:System.Windows.Forms.DataGridColumnStyle>.|

Al hacer doble clic en el borde derecho de una columna se cambia el tamaño de la columna para mostrar su leyenda completa y su entrada más ancha.

## <a name="table-styles-and-column-styles"></a>Estilos de tabla y estilos de columna

Tan pronto como haya establecido el formato predeterminado del control <xref:System.Windows.Forms.DataGrid>, puede personalizar los colores que se usarán cuando se muestren determinadas tablas en la cuadrícula de datos.

Esto se logra mediante la creación de instancias de la clase <xref:System.Windows.Forms.DataGridTableStyle>. Los estilos de tabla especifican el formato de tablas específicas, distinto del formato predeterminado del propio control <xref:System.Windows.Forms.DataGrid>. Una tabla no puede tener más de un estilo definido.

Es posible que en ocasiones desee que una columna concreta tenga una apariencia diferente a la del resto de columnas de una tabla de datos. En ese caso, puede crear un conjunto personalizado de estilos de columna mediante la propiedad <xref:System.Windows.Forms.DataGridTableStyle.GridColumnStyles%2A>.

Los estilos de columna están relacionados con las columnas de un conjunto de datos del mismo modo que los estilos de tabla están relacionados con las tablas de datos. Al igual que sucede con las tablas, que no pueden tener más de un estilo de tabla definido, una columna no puede tener definido más de un estilo de columna en un estilo de tabla concreto. Esta relación se define en la propiedad <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> de la columna.

Si ha creado un estilo de tabla sin agregarle estilos de columna, Visual Studio agregará estilos de columna predeterminados cuando se creen el formulario y la cuadrícula en tiempo de ejecución. Sin embargo, si ha creado un estilo de tabla y le ha agregado estilos de columna, Visual Studio no creará ningún estilo de columna. Además, necesitará definir estilos de columna y asignarlos con el nombre de la asignación para que las columnas que desee aparezcan en la cuadrícula.

Dado que usted especifica las columnas que se incluyen en la cuadrícula de datos al asignarles un estilo de columna y no se les ha asignado ningún estilo de columna, puede incluir columnas de datos en el conjunto de datos que no se muestran en la cuadrícula. Sin embargo, dado que la columna de datos se incluye en el conjunto de datos, puede editar mediante programación los datos que no se muestran.

> [!NOTE]
> En general, es mejor que cree los estilos de columna y los agregue a la colección de estilos de columna antes de agregar estilos de tabla a la colección de estilos de tabla. Si agrega un estilo de tabla vacío a la colección, se generan automáticamente los estilos de columna. Por lo tanto, se producirá una excepción si intenta agregar estilos de columna nuevos con valores <xref:System.Windows.Forms.DataGridColumnStyle.MappingName%2A> duplicados a la colección de estilos de columna.
>
> Es posible que en ocasiones desee quitar una sola columna de muchas; por ejemplo, si el conjunto de datos contiene 50 columnas y solo desea 49. En este caso, es más fácil importar las 50 columnas y quitar una mediante programación, en lugar de agregar mediante programación cada una de las 49 columnas que desee.

## <a name="formatting"></a>Formato

El formato que se pueden aplicar al control <xref:System.Windows.Forms.DataGrid> incluye estilos de borde, estilos de línea de cuadrícula, fuentes, propiedades de título, alineación de datos y colores alternativos para el fondo de las filas. Para obtener más información, vea [Cómo: Dé formato al Windows Forms control DataGrid](how-to-format-the-windows-forms-datagrid-control.md).

## <a name="events"></a>Eventos

Además de los eventos de control comunes como <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.Enter> y <xref:System.Windows.Forms.DataGrid.Scroll>, el control <xref:System.Windows.Forms.DataGrid> admite eventos asociados con la edición y navegación dentro de la cuadrícula. La propiedad <xref:System.Windows.Forms.DataGrid.CurrentCell%2A> determina la celda seleccionada. El evento <xref:System.Windows.Forms.DataGrid.CurrentCellChanged> se genera cuando el usuario navega a una nueva celda. Cuando el usuario navega a una nueva tabla a través de relaciones de elementos primarios y secundarios, se genera el evento <xref:System.Windows.Forms.DataGrid.Navigate>. El evento <xref:System.Windows.Forms.DataGrid.BackButtonClick> se genera cuando el usuario hace clic en el botón Atrás mientras mira una tabla secundaria y el evento <xref:System.Windows.Forms.DataGrid.ShowParentDetailsButtonClick> se genera cuando se hace clic en el icono de mostrar u ocultar las filas primarias.

## <a name="see-also"></a>Vea también

- [DataGrid (control)](datagrid-control-windows-forms.md)
- [Cómo: Enlazar el control DataGrid de Windows Forms a un origen de datos](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [Cómo: Agregar tablas y columnas al control DataGrid de Windows Forms](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [Cómo: Eliminar u ocultar columnas en el control DataGrid de Windows Forms](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [Cómo: Dé formato al Windows Forms control DataGrid](how-to-format-the-windows-forms-datagrid-control.md)
