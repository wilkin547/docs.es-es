---
title: Prácticas recomendadas para escalar el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 63500a79def89510b4bc7a436abc4620a7265a79
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744126"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms

El control de <xref:System.Windows.Forms.DataGridView> está diseñado para proporcionar la máxima escalabilidad. Si necesita mostrar grandes cantidades de datos, debe seguir las instrucciones descritas en este tema para evitar el consumo de grandes cantidades de memoria o la degradación de la capacidad de respuesta de la interfaz de usuario (UI). En este tema se describen los siguientes problemas:

- Usar estilos de celda eficazmente

- Uso eficaz de los menús contextuales

- Usar el cambio de tamaño automático eficazmente

- Usar las colecciones de celdas, filas y columnas seleccionadas de forma eficaz

- Usar filas compartidas

- Impedir que las filas se conviertan en no compartidas

Si tiene necesidades de rendimiento especiales, puede implementar el modo virtual y proporcionar sus propias operaciones de administración de datos. Para obtener más información, vea [modos de presentación de datos en el control DataGridView Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).

## <a name="using-cell-styles-efficiently"></a>Usar estilos de celda eficazmente

Cada celda, fila y columna puede tener su propia información de estilo. La información de estilo se almacena en objetos de <xref:System.Windows.Forms.DataGridViewCellStyle>. Crear objetos de estilo de celda para muchos elementos de <xref:System.Windows.Forms.DataGridView> individuales puede ser ineficaz, especialmente cuando se trabaja con grandes cantidades de datos. Para evitar un impacto en el rendimiento, utilice las siguientes directrices:

- Evite establecer propiedades de estilo de celda para objetos individuales de <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow>. Esto incluye el objeto de fila especificado por la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>. Cada fila nueva clonada de la plantilla de fila recibirá su propia copia del objeto de estilo de celda de la plantilla. Para obtener la máxima escalabilidad, establezca las propiedades de estilo de celda en el nivel de <xref:System.Windows.Forms.DataGridView>. Por ejemplo, establezca la propiedad <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> en lugar de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>.

- Si algunas celdas requieren un formato que no sea el predeterminado, utilice la misma instancia de <xref:System.Windows.Forms.DataGridViewCellStyle> entre grupos de celdas, filas o columnas. Evite establecer directamente las propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle> en celdas, filas y columnas individuales. Para obtener un ejemplo de uso compartido de estilos de celda, vea [Cómo: establecer estilos de celda predeterminados para el control DataGridView Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). También puede evitar una reducción del rendimiento al establecer los estilos de celda individualmente mediante el control del controlador de eventos de <xref:System.Windows.Forms.DataGridView.CellFormatting>. Para obtener un ejemplo, vea [Cómo: personalizar el formato de datos en el control DataGridView Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).

- Al determinar el estilo de una celda, utilice la propiedad <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> en lugar de la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType>. Al tener acceso a la propiedad <xref:System.Windows.Forms.DataGridViewCell.Style%2A>, se crea una nueva instancia de la clase <xref:System.Windows.Forms.DataGridViewCellStyle> si aún no se ha utilizado la propiedad. Además, este objeto podría no contener la información de estilo completa de la celda si algunos estilos se heredan de la fila, la columna o el control. Para obtener más información sobre la herencia del estilo de celda, vea [estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).

## <a name="using-shortcut-menus-efficiently"></a>Uso eficaz de los menús contextuales

Cada celda, fila y columna puede tener su propio menú contextual. Los menús contextuales del control <xref:System.Windows.Forms.DataGridView> se representan mediante controles de <xref:System.Windows.Forms.ContextMenuStrip>. Al igual que con los objetos de estilo de celda, la creación de menús contextuales para muchos elementos de <xref:System.Windows.Forms.DataGridView> individuales afectará negativamente al rendimiento. Para evitar esta penalización, utilice las siguientes directrices:

- Evite crear menús contextuales para celdas y filas individuales. Esto incluye la plantilla de fila, que se clona junto con el menú contextual cuando se agregan nuevas filas al control. Para obtener la máxima escalabilidad, use solo la propiedad <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> del control para especificar un solo menú contextual para todo el control.

- Si necesita varios menús contextuales para varias filas o celdas, controle los eventos <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded>. Estos eventos le permiten administrar los objetos de menú contextual usted mismo, lo que le permite ajustar el rendimiento.

## <a name="using-automatic-resizing-efficiently"></a>Usar el cambio de tamaño automático eficazmente

Se puede cambiar automáticamente el tamaño de las filas, columnas y encabezados según los cambios de contenido de celda para que todo el contenido de las celdas se muestre sin recortes. Cambiar los modos de cambio de tamaño también puede cambiar el tamaño de filas, columnas y encabezados. Para determinar el tamaño correcto, el control <xref:System.Windows.Forms.DataGridView> debe examinar el valor de cada celda que debe adaptarse. Cuando se trabaja con grandes conjuntos de datos, este análisis puede afectar negativamente al rendimiento del control cuando se produce un cambio de tamaño automático. Para evitar penalizaciones de rendimiento, utilice las siguientes directrices:

- Evite usar el ajuste de tamaño automático en un control de <xref:System.Windows.Forms.DataGridView> con un conjunto grande de filas. Si utiliza el ajuste automático de tamaño, solo tiene que cambiar el tamaño en función de las filas mostradas. Use solo las filas mostradas en modo virtual.

  - En el caso de las filas y las columnas, utilice el campo `DisplayedCells` o `DisplayedCellsExceptHeaders` de las enumeraciones <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>y <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode>.

  - En el caso de los encabezados de fila, utilice el campo <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> de la enumeración <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode>.

- Para obtener la máxima escalabilidad, desactive el ajuste de tamaño automático y use el cambio de tamaño mediante programación.

Para obtener más información, consulte [Opciones de ajuste de tamaño en el control DataGridView Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md).

## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Usar las colecciones de celdas, filas y columnas seleccionadas de forma eficaz

La colección de <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> no funciona de forma eficaz con selecciones grandes. Las colecciones <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> también pueden ser ineficaces, aunque a un menor grado, ya que hay muchas menos filas que las celdas de un control <xref:System.Windows.Forms.DataGridView> típico y muchas menos columnas que filas. Para evitar las penalizaciones de rendimiento al trabajar con estas colecciones, use las siguientes directrices:

- Para determinar si se han seleccionado todas las celdas de la <xref:System.Windows.Forms.DataGridView> antes de tener acceso al contenido de la colección <xref:System.Windows.Forms.DataGridView.SelectedCells%2A>, compruebe el valor devuelto del método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A>. Sin embargo, tenga en cuenta que este método puede hacer que las filas dejen de estar compartidas. Para obtener más información, vea la siguiente sección.

- Evite utilizar la propiedad <xref:System.Collections.ICollection.Count%2A> del <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> para determinar el número de celdas seleccionadas. En su lugar, use el método <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> y pase el valor <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType>. Del mismo modo, use los métodos <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> para determinar el número de elementos seleccionados, en lugar de tener acceso a las colecciones de filas y columnas seleccionadas.

- Evite los modos de selección basados en celdas. En su lugar, establezca la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

## <a name="using-shared-rows"></a>Usar filas compartidas

El uso eficaz de la memoria se logra en el control <xref:System.Windows.Forms.DataGridView> a través de filas compartidas. Las filas compartirán tanta información como sea posible en la apariencia y el comportamiento compartiendo las instancias de la clase <xref:System.Windows.Forms.DataGridViewRow>.

Aunque compartir instancias de fila ahorra memoria, las filas pueden dejar de estar compartidas fácilmente. Por ejemplo, cada vez que un usuario interactúa directamente con una celda, su fila deja de estar compartida. Dado que esto no se puede evitar, las instrucciones de este tema solo son útiles cuando se trabaja con grandes cantidades de datos y solo cuando los usuarios interactúan con una parte relativamente pequeña de los datos cada vez que se ejecuta el programa.

No se puede compartir una fila en un control de <xref:System.Windows.Forms.DataGridView> independiente si alguna de sus celdas contiene valores. Cuando el control de <xref:System.Windows.Forms.DataGridView> se enlaza a un origen de datos externo o al implementar el modo virtual y proporcionar su propio origen de datos, los valores de celda se almacenan fuera del control en lugar de en los objetos de celda, lo que permite compartir las filas.

Un objeto Row solo puede compartirse Si el estado de todas sus celdas se puede determinar a partir del estado de la fila y de los Estados de las columnas que contienen las celdas. Si cambia el estado de una celda para que ya no se pueda deducir del estado de su fila y columna, no se puede compartir la fila.

Por ejemplo, una fila no se puede compartir en ninguna de las situaciones siguientes:

- La fila contiene una sola celda seleccionada que no está en la columna seleccionada.

- La fila contiene una celda con sus propiedades <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> establecidas.

- La fila contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con su conjunto de propiedades <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A>.

En modo enlazado o en modo virtual, puede proporcionar información sobre herramientas y menús contextuales para celdas individuales mediante el control de los eventos <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> y <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded>.

El control <xref:System.Windows.Forms.DataGridView> intentará usar automáticamente las filas compartidas cada vez que se agreguen filas a la <xref:System.Windows.Forms.DataGridViewRowCollection>. Utilice las siguientes directrices para asegurarse de que las filas se comparten:

- Evite llamar a la sobrecarga `Add(Object[])` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> y la sobrecarga `Insert(Object[])` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>. Estas sobrecargas crean automáticamente filas no compartidas.

- Asegúrese de que la fila especificada en la propiedad <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> se puede compartir en los casos siguientes:

  - Al llamar a las sobrecargas `Add()` o `Add(Int32)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> o la sobrecarga `Insert(Int32,Int32)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

  - Al aumentar el valor de la propiedad <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType>.

  - Al establecer la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>.

- Asegúrese de que la fila indicada por el parámetro `indexSource` se puede compartir al llamar a los métodos <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>y <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

- Asegúrese de que se pueden compartir las filas especificadas al llamar a la sobrecarga `Add(DataGridViewRow)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A>, el método <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A>, la sobrecarga `Insert(Int32,DataGridViewRow)` del método <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> y el método <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> de la colección <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>.

Para determinar si una fila está compartida, utilice el método <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> para recuperar el objeto Row y, a continuación, Compruebe la propiedad <xref:System.Windows.Forms.DataGridViewBand.Index%2A> del objeto. Las filas compartidas siempre tienen un valor de propiedad <xref:System.Windows.Forms.DataGridViewBand.Index%2A> de – 1.

## <a name="preventing-rows-from-becoming-unshared"></a>Impedir que las filas se conviertan en no compartidas

Las filas compartidas pueden dejar de estar compartidas como resultado del código o de la acción del usuario. Para evitar un impacto en el rendimiento, debe evitar que las filas dejen de estar compartidas. Durante el desarrollo de la aplicación, puede controlar el evento <xref:System.Windows.Forms.DataGridView.RowUnshared> para determinar cuándo dejan de estar compartidas las filas. Esto resulta útil al depurar problemas de uso compartido de filas.

Para evitar que las filas deje de estar compartidas, utilice las siguientes directrices:

- Evite indizar la colección de <xref:System.Windows.Forms.DataGridView.Rows%2A> o recorrer en iteración con un bucle `foreach`. Normalmente, no necesitará tener acceso a las filas directamente. <xref:System.Windows.Forms.DataGridView> métodos que operan en filas toman argumentos de índice de fila en lugar de instancias de fila. Además, los controladores de los eventos relacionados con filas reciben objetos de argumento de evento con propiedades de fila que se pueden usar para manipular las filas sin provocar que dejen de estar compartidas.

- Si necesita tener acceso a un objeto de fila, use el método <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> y pase el índice real de la fila. Tenga en cuenta, sin embargo, que la modificación de un objeto de fila compartido recuperado a través de este método modificará todas las filas que comparten este objeto. Sin embargo, la fila de los nuevos registros no se comparte con otras filas, por lo que no se verá afectada cuando modifique cualquier otra fila. Tenga en cuenta también que las distintas filas representadas por una fila compartida pueden tener menús contextuales diferentes. Para recuperar el menú contextual correcto de una instancia de fila compartida, utilice el método <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> y pase el índice real de la fila. Si tiene acceso a la propiedad <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> de la fila compartida, utilizará el índice de fila compartido de-1 y no recuperará el menú contextual correcto.

- Evite indizar la colección de <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType>. El acceso a una celda directamente hará que su fila primaria deje de estar compartida, creando una instancia de una nueva <xref:System.Windows.Forms.DataGridViewRow>. Los controladores de los eventos relacionados con las celdas reciben objetos de argumento de evento con propiedades de celda que se pueden usar para manipular celdas sin hacer que las filas dejen de estar compartidas. También puede utilizar la propiedad <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> para recuperar los índices de fila y columna de la celda actual sin tener acceso directamente a la celda.

- Evite los modos de selección basados en celdas. Estos modos hacen que las filas dejen de estar compartidas. En su lugar, establezca la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> en <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.

- No controle los eventos <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType>. Estos eventos hacen que las filas dejen de estar compartidas. Además, no llame a los métodos <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType>, que provocan estos eventos.

- No tener acceso a la colección de <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> cuando el valor de la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> es <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. Esto hace que todas las filas seleccionadas dejen de estar compartidas.

- No llame al método <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType>. Este método puede hacer que las filas dejen de estar compartidas.

- No llame al método <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> cuando se <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>el valor de la propiedad <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType>. Esto hace que todas las filas dejen de estar compartidas.

- No establezca la propiedad <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> de una celda en `false` cuando la propiedad correspondiente de su columna esté establecida en `true`. Esto hace que todas las filas dejen de estar compartidas.

- No tener acceso a la propiedad <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType>. Esto hace que todas las filas dejen de estar compartidas.

- No llame a la sobrecarga `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>. La ordenación con un comparador personalizado hace que todas las filas dejen de estar compartidas.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
