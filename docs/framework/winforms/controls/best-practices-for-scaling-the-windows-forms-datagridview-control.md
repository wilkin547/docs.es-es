---
title: Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
ms.openlocfilehash: 76ac31e9082216d0024160c51a7495855eee5601
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59142149"
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control está diseñado para proporcionar la máxima escalabilidad. Si necesita mostrar grandes cantidades de datos, debe seguir las directrices descritas en este tema para evitar consumir grandes cantidades de memoria o degradar la capacidad de respuesta de la interfaz de usuario (UI). En este tema se trata los siguientes problemas:  
  
-   Usar de forma eficaz los estilos de celda  
  
-   Usar los menús contextuales de forma eficaz  
  
-   Uso de cambio de tamaño automático eficazmente  
  
-   Usar las recopilaciones de celdas, filas y columnas seleccionadas de forma eficaz  
  
-   Uso de las filas compartidas  
  
-   Impedir que las filas dejen de estar compartidas  
  
 Si tiene necesidades especiales de rendimiento, puede implementar el modo virtual y proporcionar sus propias operaciones de administración de datos. Para obtener más información, consulte [modos de presentación de datos en el DataGridView Control de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Usar de forma eficaz los estilos de celda  
 Cada celda, fila y columna pueden tener su propia información de estilo. Información de estilo se almacena en <xref:System.Windows.Forms.DataGridViewCellStyle> objetos. Crear objetos de estilo de celda para muchos individuo <xref:System.Windows.Forms.DataGridView> elementos pueden ser ineficaces, especialmente cuando se trabaja con grandes cantidades de datos. Para evitar un impacto en el rendimiento, utilice las siguientes directrices:  
  
-   Evite establecer propiedades de estilo de celda de la persona <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow> objetos. Esto incluye el objeto de fila especificado por el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad. Cada nueva fila que se clona de la plantilla de fila recibirá su propia copia del objeto de estilo de celda de la plantilla. Para conseguir la máxima escalabilidad, establezca las propiedades de estilo de celda en la <xref:System.Windows.Forms.DataGridView> nivel. Por ejemplo, establecer el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad en lugar de <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> propiedad.  
  
-   Si algunas celdas requieren un formato distinto del formato predeterminado, use el mismo <xref:System.Windows.Forms.DataGridViewCellStyle> instancia a través de grupos de celdas, filas o columnas. Evite establecer directamente propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle> en celdas individuales, filas y columnas. Para obtener un ejemplo de uso compartido de estilo de celda, vea [Cómo: Establecer estilos de celda predeterminados para los Windows Forms DataGridView Control](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). También puede evitar una reducción del rendimiento al establecer estilos de celda individualmente controlando el <xref:System.Windows.Forms.DataGridView.CellFormatting> controlador de eventos. Como ejemplo, vea [Cómo: Personalizar el formato de datos en el Control DataGridView de Windows Forms](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Al determinar un estilo de celda, utilice el <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> propiedad en lugar de <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> propiedad. Obtener acceso a la <xref:System.Windows.Forms.DataGridViewCell.Style%2A> propiedad crea una nueva instancia de la <xref:System.Windows.Forms.DataGridViewCellStyle> si ya no se ha utilizado la propiedad de clase. Además, este objeto no puede contener la información de estilo completa para la celda si algunos estilos se heredan de la fila, columna o control. Para obtener más información sobre la herencia de estilo de celda, vea [estilos de celda en el DataGridView Control de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Usar los menús contextuales de forma eficaz  
 Cada celda, fila y columna pueden tener su propio menú contextual. Menús contextuales en el <xref:System.Windows.Forms.DataGridView> control se representan mediante <xref:System.Windows.Forms.ContextMenuStrip> controles. Al igual que con los objetos de estilo de celda, crear menús contextuales para muchos individuo <xref:System.Windows.Forms.DataGridView> elementos afectará negativamente al rendimiento. Para evitar esta situación, utilice las siguientes directrices:  
  
-   Evite crear menús contextuales para celdas y filas individuales. Esto incluye la plantilla de fila, que se clona junto con su menú contextual cuando se agregan nuevas filas al control. Para conseguir la máxima escalabilidad, utilice sólo del control <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad para especificar un solo menú contextual para el control completo.  
  
-   Si necesita varios menús contextuales para varias filas o celdas, controlar la <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> eventos. Estos eventos le permiten administrar los objetos de menú contextual usted mismo, lo que le permite optimizar el rendimiento.  
  
## <a name="using-automatic-resizing-efficiently"></a>Uso de cambio de tamaño automático eficazmente  
 Encabezados, columnas y filas pueden cambiarse automáticamente como los cambios de contenido de celda para que todo el contenido de las celdas se muestra sin recortes. Cambiar los modos de ajuste de tamaño puede también cambiar el tamaño de filas, columnas y encabezados. Para determinar el tamaño correcto, el <xref:System.Windows.Forms.DataGridView> control debe examinar el valor de cada celda que se deben dar cabida a. Cuando se trabaja con grandes conjuntos de datos, este análisis pueden afecte negativamente el rendimiento del control cuando se produce de cambio de tamaño automático. Para evitar las penalizaciones de rendimiento, utilice las siguientes directrices:  
  
-   Evite el uso de ajuste de tamaño automático en un <xref:System.Windows.Forms.DataGridView> control con un gran conjunto de filas. Si usa el ajuste de tamaño automático, solo cambio de tamaño en función de las filas mostradas. Usar solo las filas mostradas en modo virtual también.  
  
    -   Para las filas y columnas, utilice el `DisplayedCells` o `DisplayedCellsExceptHeaders` campo de la <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, y <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> enumeraciones.  
  
    -   Para los encabezados de fila, utilice el <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> campo de la <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> enumeración.  
  
-   Para conseguir la máxima escalabilidad, desactivar el ajuste automático de tamaño y use el cambio de tamaño mediante programación.  
  
 Para obtener más información, consulte [opciones de ajuste de tamaño en el DataGridView Control de formularios de Windows](sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Usar de forma eficaz las celdas seleccionadas, filas y las colecciones de columnas  
 El <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección no se ejecuta eficazmente con grandes selecciones. El <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colecciones también pueden resultar ineficaces, aunque en menor grado porque hay muchas menos filas que las celdas de una típica <xref:System.Windows.Forms.DataGridView> control y muchas menos columnas de filas. Para evitar las penalizaciones de rendimiento cuando se trabaja con estas colecciones, use las siguientes directrices:  
  
-   Para determinar si todas las celdas de la <xref:System.Windows.Forms.DataGridView> se han seleccionado antes de acceder al contenido de la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección, compruebe el valor devuelto de la <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método. Sin embargo, tenga en cuenta que este método puede provocar que deje de estar compartida filas. Para obtener más información, vea la siguiente sección.  
  
-   Evite el uso de la <xref:System.Collections.ICollection.Count%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> para determinar el número de celdas seleccionadas. En su lugar, use el <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> método y pase la <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> valor. De forma similar, utilice el <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> métodos para determinar el número de elementos seleccionados, en lugar de tener acceso a las recopilaciones de filas y columnas seleccionadas.  
  
-   Evite los modos de selección basada en la celda. En su lugar, establezca el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Uso compartido de filas  
 Uso eficaz de la memoria se logra en el <xref:System.Windows.Forms.DataGridView> control a través de las filas compartidas. Las filas compartirán toda la información sobre su apariencia y comportamiento como sea posible mediante el uso compartido de las instancias de la <xref:System.Windows.Forms.DataGridViewRow> clase.  
  
 Aunque compartir instancias de fila ahorra memoria, las filas pueden estar compartidas fácilmente. Por ejemplo, cada vez que un usuario interactúa directamente con una celda, su fila deja de estar compartida. Dado que esto no se puede evitar, las directrices descritas en este tema son útiles solo cuando se trabaja con grandes cantidades de datos y solo cuando los usuarios interactúan con una parte relativamente pequeña de los datos cada vez que se ejecuta el programa.  
  
 No se puede compartir una fila en una independiente <xref:System.Windows.Forms.DataGridView> controlar si cualquiera de sus celdas contienen valores. Cuando el <xref:System.Windows.Forms.DataGridView> está enlazado a un origen de datos externos o al implementar el modo virtual y proporcionar su propio origen de datos, los valores de celda se almacenan fuera del control, en lugar de en los objetos cell, lo que permite a las filas que se va a compartirse.  
  
 Solo se puede compartir un objeto de fila si se puede determinar el estado de todas sus celdas desde el estado de la fila y los Estados de las columnas que contienen las celdas. Si cambia el estado de una celda para que ya no se puede deducir del estado de su fila y columna, no se puede compartir la fila.  
  
 Por ejemplo, una fila no se puede compartir en cualquiera de las situaciones siguientes:  
  
-   La fila contiene una sola celda seleccionada que no está en una columna seleccionada.  
  
-   La fila contiene una celda con su <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> conjunto de propiedades.  
  
-   La fila contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con su <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> conjunto de propiedades.  
  
 En el modo de enlace o en modo virtual, puede proporcionar información sobre herramientas y menús contextuales para celdas individuales controlando el <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> y <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> eventos.  
  
 El <xref:System.Windows.Forms.DataGridView> control intentará utilizar filas compartidas cada vez que se agregan filas a la <xref:System.Windows.Forms.DataGridViewRowCollection>. Use las directrices siguientes para asegurarse de que se comparten las filas:  
  
-   Evite llamar a la `Add(Object[])` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> método y el `Insert(Object[])` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección. Estas sobrecargas crean automáticamente filas no compartidas.  
  
-   Asegúrese de que la fila especificada en el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> propiedad se puede compartir en los casos siguientes:  
  
    -   Al llamar a la `Add()` o `Add(Int32)` las sobrecargas del <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> método o la `Insert(Int32,Int32)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección.  
  
    -   Al aumentar el valor de la <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> propiedad.  
  
    -   Al establecer el <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> propiedad.  
  
-   Asegúrese de que la fila indicada por el `indexSource` puede compartirse parámetro al llamar a la <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, y <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> métodos de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección.  
  
-   Asegúrese de que se pueden compartir la fila o filas especificadas cuando se llama a la `Add(DataGridViewRow)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> método, el <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> método, el `Insert(Int32,DataGridViewRow)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método y el <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>colección.  
  
 Para determinar si se comparte una fila, use el <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> método para recuperar el objeto de fila y, a continuación, compruebe el objeto <xref:System.Windows.Forms.DataGridViewBand.Index%2A> propiedad. Filas compartidas siempre tienen un <xref:System.Windows.Forms.DataGridViewBand.Index%2A> valor de propiedad de – 1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Impedir que las filas dejen de estar compartidas  
 Filas compartidas pueden estar compartidas como resultado de acción del usuario o el código. Para evitar un impacto en el rendimiento, debe evitar filas deje de estar compartida. Durante el desarrollo de aplicaciones, puede administrar el <xref:System.Windows.Forms.DataGridView.RowUnshared> evento para determinar cuándo las filas dejen de estar compartidas. Esto es útil al depurar problemas de uso compartido de fila.  
  
 Para evitar que las filas dejen de estar compartidas, utilice las siguientes directrices:  
  
-   Evite indizar el <xref:System.Windows.Forms.DataGridView.Rows%2A> colección o la iteración a través de él con un `foreach` bucle. No normalmente necesitará acceso directo a las filas. <xref:System.Windows.Forms.DataGridView> los métodos que operan en filas toman argumentos de índice de fila en lugar de las instancias de la fila. Además, los controladores de eventos relacionados con la fila reciben objetos de argumento de evento con propiedades de la fila que pueden usar para manipular filas sin provocar que deje de estar compartida.  
  
-   Si necesita acceso a un objeto de fila, use el <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> método y pase el índice real de la fila. Sin embargo, tenga en cuenta que la modificación de un objeto de fila compartido recuperado a través de este método va a modificar todas las filas que comparten este objeto. La fila para los nuevos registros no se comparte con otras filas, sin embargo, por lo que no se verán afectada cuando se modifica cualquier otra fila. Tenga en cuenta también que diferentes filas representadas por una fila compartida pueden tener distintos menús emergentes. Para recuperar el menú contextual correcto desde una instancia de fila compartida, use el <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> método y pase el índice real de la fila. Si tiene acceso a la fila compartida <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> propiedad en su lugar, usará el índice de fila compartida de -1 y no se recuperará el menú contextual correcto.  
  
-   Evite indizar el <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> colección. Tener acceso directamente a una celda hará que su fila primaria deje de estar compartida, instancias de un nuevo <xref:System.Windows.Forms.DataGridViewRow>. Controladores de eventos relacionados con la celda reciben objetos de argumento de evento con propiedades de celda que puede usar para manipular las celdas sin provocar que las filas dejen de estar compartidas. También puede usar el <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> propiedad para recuperar los índices de fila y columna de la celda actual sin tener acceso directamente a la celda.  
  
-   Evite los modos de selección basada en la celda. Estos modos de hacer que deje de estar compartida filas. En su lugar, establezca el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   No controla el <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> eventos. Estos eventos hacen que las filas dejen de estar compartidas. Además, no llame a la <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> métodos, que generan estos eventos.  
  
-   No tienen acceso a la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> colección cuando el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> es el valor de propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. Esto hace que todas las filas seleccionadas deje de estar compartida.  
  
-   No llame a la <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> método. Este método puede provocar que deje de estar compartida filas.  
  
-   No llame a la <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> método cuando el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> es el valor de propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. Esto hace que todas las filas que deje de estar compartida.  
  
-   No establezca la <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> propiedad de una celda a `false` cuando se establece la propiedad correspondiente en su columna en `true`. Esto hace que todas las filas que deje de estar compartida.  
  
-   No tienen acceso a la <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> propiedad. Esto hace que todas las filas que deje de estar compartida.  
  
-   No llame a la `Sort(IComparer)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método. Ordenación con un comparador personalizado hace que todas las filas que deje de estar compartida.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- [Ajuste del rendimiento del control DataGridView en Windows Forms](performance-tuning-in-the-windows-forms-datagridview-control.md)
- [Modo virtual del control DataGridView de Windows Forms](virtual-mode-in-the-windows-forms-datagridview-control.md)
- [Modos de presentación de datos en el control DataGridView de Windows Forms](data-display-modes-in-the-windows-forms-datagridview-control.md)
- [Estilos de celda en el control DataGridView de Windows Forms](cell-styles-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer estilos de celda predeterminados para el Control DataGridView de Windows Forms](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)
- [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](sizing-options-in-the-windows-forms-datagridview-control.md)
