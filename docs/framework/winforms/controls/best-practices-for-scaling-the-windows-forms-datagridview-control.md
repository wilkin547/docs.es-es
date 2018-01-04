---
title: Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- DataGridView control [Windows Forms], row sharing
- data grids [Windows Forms], best practices
- DataGridView control [Windows Forms], shared rows
- DataGridView control [Windows Forms], best practices
- best practices [Windows Forms], dataGridView control
- DataGridView control [Windows Forms], scaling
ms.assetid: 8321a8a6-6340-4fd1-b475-fa090b905aaf
caps.latest.revision: "31"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ecd629bd38e08c8d6909ee4ad771f17b1554fc80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="best-practices-for-scaling-the-windows-forms-datagridview-control"></a>Procedimientos recomendados para ajustar la escala del control DataGridView en formularios Windows Forms
El <xref:System.Windows.Forms.DataGridView> control está diseñado para ofrecer la máxima escalabilidad. Si tiene que mostrar grandes cantidades de datos, debe seguir las directrices descritas en este tema para evitar consumir grandes cantidades de memoria o la disminución de la capacidad de respuesta de la interfaz de usuario (UI). En este tema se describe los siguientes problemas:  
  
-   Usar de forma eficaz los estilos de celda  
  
-   Utilizar menús contextuales eficazmente  
  
-   Uso de cambio de tamaño automático eficazmente  
  
-   Usar las recopilaciones de celdas, filas y columnas seleccionadas de forma eficaz  
  
-   Utilizar filas compartidas  
  
-   Impedir que las filas dejen de estar compartidas  
  
 Si tiene necesidades de rendimiento especiales, puede implementar el modo virtual y proporcionar sus propias operaciones de administración de datos. Para obtener más información, consulte [modos de presentación de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-cell-styles-efficiently"></a>Usar de forma eficaz los estilos de celda  
 Cada celda, fila y columna pueden tener su propia información de estilo. Información de estilo se almacena en <xref:System.Windows.Forms.DataGridViewCellStyle> objetos. Creación de objetos de estilo de celda para muchos individuales <xref:System.Windows.Forms.DataGridView> elementos pueden ser ineficaces, especialmente cuando se trabaja con grandes cantidades de datos. Para evitar un impacto en el rendimiento, utilice las siguientes directrices:  
  
-   No es necesario establecer propiedades de estilo de celda de individuales <xref:System.Windows.Forms.DataGridViewCell> o <xref:System.Windows.Forms.DataGridViewRow> objetos. Esto incluye el objeto de fila especificado por el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> propiedad. Cada nueva fila que se clona de la plantilla de fila recibirá su propia copia del objeto de estilo de celda de la plantilla. Para conseguir la máxima escalabilidad, establecer las propiedades de estilo de celda en el <xref:System.Windows.Forms.DataGridView> nivel. Por ejemplo, establecer el <xref:System.Windows.Forms.DataGridView.DefaultCellStyle%2A?displayProperty=nameWithType> propiedad en lugar del <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> propiedad.  
  
-   Si algunas celdas requieren un formato distinto del formato predeterminado, use el mismo <xref:System.Windows.Forms.DataGridViewCellStyle> instancia a través de grupos de celdas, filas o columnas. Evite establecer directamente propiedades de tipo <xref:System.Windows.Forms.DataGridViewCellStyle> en celdas individuales, filas y columnas. Para obtener un ejemplo de uso compartido de estilo de celda, vea [Cómo: establecer estilos de celda predeterminados para el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md). También puede evitar una reducción del rendimiento al establecer estilos de celda individualmente controlando el <xref:System.Windows.Forms.DataGridView.CellFormatting> controlador de eventos. Para obtener un ejemplo, vea [Cómo: personalizar el formato de datos en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).  
  
-   Al determinar un estilo de celda, use la <xref:System.Windows.Forms.DataGridViewCell.InheritedStyle%2A?displayProperty=nameWithType> propiedad en lugar del <xref:System.Windows.Forms.DataGridViewCell.Style%2A?displayProperty=nameWithType> propiedad. Obtener acceso a la <xref:System.Windows.Forms.DataGridViewCell.Style%2A> propiedad crea una nueva instancia de la <xref:System.Windows.Forms.DataGridViewCellStyle> si ya no se ha utilizado la propiedad de clase. Además, este objeto no puede contener la información de estilo completa para la celda si algunos estilos se heredan de la fila, columna o control. Para obtener más información acerca de la herencia de estilo de celda, vea [estilos de celda en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-shortcut-menus-efficiently"></a>Utilizar menús contextuales eficazmente  
 Cada celda, fila y columna pueden tener su propio menú contextual. Los menús contextuales de la <xref:System.Windows.Forms.DataGridView> control se representan mediante <xref:System.Windows.Forms.ContextMenuStrip> controles. Al igual que con objetos de estilo de celda, crear menús contextuales para muchos individuales <xref:System.Windows.Forms.DataGridView> elementos afectará negativamente al rendimiento. Para evitar esta situación, utilice las siguientes directrices:  
  
-   Evite crear menús contextuales para celdas y filas individuales. Esto incluye la plantilla de fila, que se clona junto con su menú contextual cuando se agregan nuevas filas al control. Para conseguir la máxima escalabilidad, use sólo el control <xref:System.Windows.Forms.Control.ContextMenuStrip%2A> propiedad para especificar un menú contextual único para todo el control.  
  
-   Si requiere varios menús contextuales para varias filas o celdas, controle el <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> o <xref:System.Windows.Forms.DataGridView.RowContextMenuStripNeeded> eventos. Estos eventos le permiten administrar los objetos de menú contextual usted mismo, lo que le permite optimizar el rendimiento.  
  
## <a name="using-automatic-resizing-efficiently"></a>Uso de cambio de tamaño automático eficazmente  
 Filas, columnas y encabezados pueden cambiarse automáticamente como cambios de contenido de la celda para que todo el contenido de las celdas se muestra sin recortes. Cambiar los modos de ajuste de tamaño puede también cambiar el tamaño de filas, columnas y encabezados. Para determinar el tamaño correcto, el <xref:System.Windows.Forms.DataGridView> control debe examinar el valor de cada celda que debe tenerla en cuenta. Cuando se trabaja con grandes conjuntos de datos, este análisis pueden afecte negativamente el rendimiento del control cuando se produce de cambio de tamaño automático. Para evitar las penalizaciones del rendimiento, utilice las siguientes directrices:  
  
-   Evite el uso de ajuste automático de tamaño en un <xref:System.Windows.Forms.DataGridView> control con un gran conjunto de filas. Si utiliza el tamaño automático, sólo cambie el tamaño en función de las filas mostradas. Usar solo las filas mostradas en modo virtual también.  
  
    -   Para las filas y columnas, utilice el `DisplayedCells` o `DisplayedCellsExceptHeaders` campo de la <xref:System.Windows.Forms.DataGridViewAutoSizeRowsMode>, <xref:System.Windows.Forms.DataGridViewAutoSizeColumnsMode>, y <xref:System.Windows.Forms.DataGridViewAutoSizeColumnMode> enumeraciones.  
  
    -   Para los encabezados de fila, utilice la <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToDisplayedHeaders> o <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode.AutoSizeToFirstHeader> campo de la <xref:System.Windows.Forms.DataGridViewRowHeadersWidthSizeMode> enumeración.  
  
-   Para conseguir la máxima escalabilidad, desactivar el ajuste automático de tamaño y use el cambio de tamaño mediante programación.  
  
 Para obtener más información, consulte [opciones de ajuste de tamaño en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md).  
  
## <a name="using-the-selected-cells-rows-and-columns-collections-efficiently"></a>Utilizar eficazmente las celdas seleccionadas, filas y las colecciones de columnas  
 El <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección no se ejecuta eficazmente con grandes selecciones. El <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> y <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> colecciones también pueden resultar ineficaces, aunque en menor grado porque hay muchas menos filas de las celdas de una típica <xref:System.Windows.Forms.DataGridView> control y muchas menos columnas que filas. Para evitar las penalizaciones del rendimiento cuando se trabaja con estas colecciones, utilice las siguientes directrices:  
  
-   Para determinar si todas las celdas de la <xref:System.Windows.Forms.DataGridView> se han seleccionado antes de acceder al contenido de la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> colección, compruebe el valor devuelto de la <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A> método. Sin embargo, tenga en cuenta que este método puede provocar que deje de estar compartida filas. Para obtener más información, vea la siguiente sección.  
  
-   Evite el uso de la <xref:System.Collections.ICollection.Count%2A> propiedad de la <xref:System.Windows.Forms.DataGridViewSelectedCellCollection?displayProperty=nameWithType> para determinar el número de celdas seleccionadas. En su lugar, use la <xref:System.Windows.Forms.DataGridView.GetCellCount%2A?displayProperty=nameWithType> método y pase la <xref:System.Windows.Forms.DataGridViewElementStates.Selected?displayProperty=nameWithType> valor. De igual forma, utilizar el <xref:System.Windows.Forms.DataGridViewRowCollection.GetRowCount%2A?displayProperty=nameWithType> y <xref:System.Windows.Forms.DataGridViewColumnCollection.GetColumnCount%2A?displayProperty=nameWithType> métodos para determinar el número de elementos seleccionados, en lugar de tener acceso a las recopilaciones de filas y columnas seleccionadas.  
  
-   Evite los modos de selección basada en la celda. En su lugar, establezca el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
## <a name="using-shared-rows"></a>Uso compartido de filas  
 Uso eficaz de la memoria se consigue en el <xref:System.Windows.Forms.DataGridView> control a través de filas compartidas. Las filas compartirán toda la información como sea posible sobre su apariencia y comportamiento compartiendo instancias de la <xref:System.Windows.Forms.DataGridViewRow> clase.  
  
 Aunque compartir instancias de fila ahorra memoria, filas pueden estar compartidas fácilmente. Por ejemplo, cada vez que un usuario interactúa directamente con una celda, su fila deja de estar compartida. Dado que no se puede evitar esto, las directrices descritas en este tema son útiles solo cuando se trabaja con grandes cantidades de datos y solo cuando los usuarios interactúan con una parte relativamente pequeña de los datos cada vez que se ejecuta el programa.  
  
 No se puede compartir una fila en una independiente <xref:System.Windows.Forms.DataGridView> controlar si cualquiera de sus celdas contienen valores. Cuando el <xref:System.Windows.Forms.DataGridView> control se enlaza a un origen de datos externo o al implementar el modo virtual y proporciona su propio origen de datos, los valores de celda se almacenan fuera del control, en lugar de en objetos de celda, lo que las filas que se va a compartirse.  
  
 Solo se puede compartir un objeto de fila si no se puede determinar el estado de todas sus celdas, desde el estado de la fila y los Estados de las columnas que contienen las celdas. Si cambia el estado de una celda para que ya no se puede deducir del estado de su fila y columna, la fila no se puede compartir.  
  
 Por ejemplo, una fila no se puede compartir en cualquiera de las situaciones siguientes:  
  
-   La fila contiene una celda seleccionada única que no está en una columna seleccionada.  
  
-   La fila contiene una celda con su <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> o <xref:System.Windows.Forms.DataGridViewCell.ContextMenuStrip%2A> propiedades establecidas.  
  
-   La fila contiene un <xref:System.Windows.Forms.DataGridViewComboBoxCell> con su <xref:System.Windows.Forms.DataGridViewComboBoxCell.Items%2A> conjunto de propiedades.  
  
 En el modo de enlace o el modo virtual, puede proporcionar información sobre herramientas y menús contextuales para celdas individuales controlando el <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> y <xref:System.Windows.Forms.DataGridView.CellContextMenuStripNeeded> eventos.  
  
 El <xref:System.Windows.Forms.DataGridView> control intentará utilizar filas compartidas cada vez que se agregan filas a la <xref:System.Windows.Forms.DataGridViewRowCollection>. Utilice las instrucciones siguientes para asegurarse de que se comparten filas:  
  
-   Evite llamar a la `Add(Object[])` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> método y el `Insert(Object[])` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección. Estas sobrecargas crean automáticamente filas no compartidas.  
  
-   Asegúrese de que la fila especificada en el <xref:System.Windows.Forms.DataGridView.RowTemplate%2A?displayProperty=nameWithType> propiedad se pueden compartir en los casos siguientes:  
  
    -   Al llamar a la `Add()` o `Add(Int32)` sobrecargas de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> (método) o la `Insert(Int32,Int32)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección.  
  
    -   Al aumentar el valor de la <xref:System.Windows.Forms.DataGridView.RowCount%2A?displayProperty=nameWithType> propiedad.  
  
    -   Al establecer el <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType> propiedad.  
  
-   Asegúrese de que la fila indicada por la `indexSource` puede compartirse de parámetro al llamar a la <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopy%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.AddCopies%2A>, <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopy%2A>, y <xref:System.Windows.Forms.DataGridViewRowCollection.InsertCopies%2A> métodos de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType> colección.  
  
-   Asegúrese de que la fila o filas especificadas pueden compartir cuando se llama a la `Add(DataGridViewRow)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Add%2A> método, el <xref:System.Windows.Forms.DataGridViewRowCollection.AddRange%2A> método, el `Insert(Int32,DataGridViewRow)` sobrecarga de la <xref:System.Windows.Forms.DataGridViewRowCollection.Insert%2A> método y el <xref:System.Windows.Forms.DataGridViewRowCollection.InsertRange%2A> método de la <xref:System.Windows.Forms.DataGridView.Rows%2A?displayProperty=nameWithType>colección.  
  
 Para determinar si se comparte una fila, use el <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> método para recuperar el objeto de fila y, a continuación, compruebe el objeto <xref:System.Windows.Forms.DataGridViewBand.Index%2A> propiedad. Las filas compartidas siempre tienen un <xref:System.Windows.Forms.DataGridViewBand.Index%2A> valor de la propiedad de – 1.  
  
## <a name="preventing-rows-from-becoming-unshared"></a>Impedir que las filas dejen de estar compartidas  
 Filas compartidas pueden deje de estar compartidas como resultado de acción de usuario o de código. Para evitar un impacto en el rendimiento, no debe provocar que las filas dejen de estar compartidas. Durante el desarrollo de aplicaciones, puede controlar la <xref:System.Windows.Forms.DataGridView.RowUnshared> evento para determinar cuándo filas dejen de estar compartidas. Esto es útil al depurar problemas de uso compartido de filas.  
  
 Para evitar filas dejen de estar compartidas, utilice las siguientes directrices:  
  
-   Evite la indización de la <xref:System.Windows.Forms.DataGridView.Rows%2A> colección o recorrer en iteración mediante un `foreach` bucle. No normalmente debe tener acceso directamente a filas. <xref:System.Windows.Forms.DataGridView>los métodos que operan en filas toman argumentos de índice de fila en lugar de instancias de fila. Además, los controladores de eventos relacionados con la fila reciben objetos de argumento de evento con propiedades de fila que pueden utilizar para manipular filas sin provocar que deje de estar compartida.  
  
-   Si necesita tener acceso a un objeto de fila, use el <xref:System.Windows.Forms.DataGridViewRowCollection.SharedRow%2A?displayProperty=nameWithType> método y pase el índice real de la fila. Sin embargo, tenga en cuenta que la modificación de un objeto de fila compartido recuperado a través de este método va a modificar todas las filas que comparten este objeto. La fila para los nuevos registros no se comparte con otras filas, sin embargo, por lo que no se verán afectado cuando se modifica ninguna otra fila. Tenga en cuenta también que filas distintas representadas por una fila compartida pueden tener menús contextuales distintos. Para recuperar el menú contextual correcto de una instancia de fila compartida, utilice el <xref:System.Windows.Forms.DataGridViewRow.GetContextMenuStrip%2A> método y pase el índice real de la fila. Si tiene acceso a la fila compartida <xref:System.Windows.Forms.DataGridViewRow.ContextMenuStrip%2A> propiedad en su lugar, se utilizará el índice de fila compartida de -1 y no se recuperará el menú contextual correcto.  
  
-   Evite la indización de la <xref:System.Windows.Forms.DataGridViewRow.Cells%2A?displayProperty=nameWithType> colección. Tener acceso directamente a una celda hará que su fila primaria deje de estar compartida, instancias de un nuevo <xref:System.Windows.Forms.DataGridViewRow>. Controladores de eventos relacionados con celda reciben objetos de argumento de evento con propiedades de celda que pueden utilizar para manipular las celdas sin provocar que las filas dejen de estar compartidas. También puede usar el <xref:System.Windows.Forms.DataGridView.CurrentCellAddress%2A> propiedad que recupere los índices de fila y columna de la celda actual sin tener acceso directamente a la celda.  
  
-   Evite los modos de selección basada en la celda. Estos modos de hacer que deje de estar compartida filas. En su lugar, establezca el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect?displayProperty=nameWithType>.  
  
-   No controla el <xref:System.Windows.Forms.DataGridViewRowCollection.CollectionChanged?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.RowStateChanged?displayProperty=nameWithType> eventos. Estos eventos provocar que deje de estar compartida filas. Además, no llame a la <xref:System.Windows.Forms.DataGridViewRowCollection.OnCollectionChanged%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.DataGridView.OnRowStateChanged%2A?displayProperty=nameWithType> métodos, que generan estos eventos.  
  
-   No puedan acceder a la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A?displayProperty=nameWithType> colección cuando la <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> es el valor de la propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.FullColumnSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.ColumnHeaderSelect>, <xref:System.Windows.Forms.DataGridViewSelectionMode.FullRowSelect>, o <xref:System.Windows.Forms.DataGridViewSelectionMode.RowHeaderSelect>. Esto hace que todas las filas seleccionadas dejen de estar compartidas.  
  
-   No llame a la <xref:System.Windows.Forms.DataGridView.AreAllCellsSelected%2A?displayProperty=nameWithType> método. Este método puede provocar que deje de estar compartida filas.  
  
-   No llame a la <xref:System.Windows.Forms.DataGridView.SelectAll%2A?displayProperty=nameWithType> método cuando el <xref:System.Windows.Forms.DataGridView.SelectionMode%2A?displayProperty=nameWithType> es el valor de la propiedad <xref:System.Windows.Forms.DataGridViewSelectionMode.CellSelect>. Esto hace que todas las filas dejen de estar compartidas.  
  
-   No establezca la <xref:System.Windows.Forms.DataGridViewCell.ReadOnly%2A> o <xref:System.Windows.Forms.DataGridViewCell.Selected%2A> propiedad de una celda a `false` cuando la propiedad correspondiente en la columna se establece en `true`. Esto hace que todas las filas dejen de estar compartidas.  
  
-   No puedan acceder a la <xref:System.Windows.Forms.DataGridViewRowCollection.List%2A?displayProperty=nameWithType> propiedad. Esto hace que todas las filas dejen de estar compartidas.  
  
-   No llame a la `Sort(IComparer)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método. Ordenación con un comparador personalizado hace que todas las filas dejen de estar compartidas.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 [Ajuste del rendimiento del control DataGridView en Windows Forms](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 [Modo virtual del control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/virtual-mode-in-the-windows-forms-datagridview-control.md)  
 [Modos de presentación de datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)  
 [Estilos de celda en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/cell-styles-in-the-windows-forms-datagridview-control.md)  
 [Establecer estilos de celda predeterminados para el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 [Opciones de ajuste de tamaño en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/sizing-options-in-the-windows-forms-datagridview-control.md)
