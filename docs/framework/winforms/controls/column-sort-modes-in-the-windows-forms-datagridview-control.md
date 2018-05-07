---
title: Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: 9ebcfc435fcc7d2b0dfbfe3004d958c73dd1347c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView> las columnas tienen tres modos de ordenación. El modo de ordenación para cada columna se especifica a través de la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad de la columna, que puede establecerse en uno de los siguientes <xref:System.Windows.Forms.DataGridViewColumnSortMode> valores de enumeración.  
  
|Valor de `DataGridViewColumnSortMode`|Descripción|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Valor predeterminado para las columnas del cuadro de texto. A menos que se utilizan encabezados de columna para la selección, haga clic en el encabezado de columna automáticamente ordena la <xref:System.Windows.Forms.DataGridView> por esta columna y muestra un glifo que indica el criterio de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Valor predeterminado para las columnas del cuadro no son de texto. Puede ordenar esta columna mediante programación; Sin embargo, no está diseñado para la ordenación, por lo que se reserva ningún espacio para el glifo de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Puede ordenar esta columna mediante programación y se reserva espacio para el glifo de ordenación.|  
  
 Es posible que desee cambiar el modo de ordenación para una columna cuyo valor predeterminado es <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> si contiene valores que se ordenen. Por ejemplo, si tiene una columna de base de datos que contiene números que representan estados de los elementos, puede mostrar estos números como iconos correspondientes enlazando una columna de imagen a la columna de base de datos. A continuación, puede cambiar los valores de celda numéricos en los valores de presentación de imagen en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos. En este caso, establecer el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> permitirá a los usuarios ordenar la columna. La ordenación automática permitirá a los usuarios para agrupar elementos que tienen el mismo estado, incluso si los Estados correspondientes a los números no tiene una secuencia natural. Columnas de casilla son otro ejemplo donde la ordenación automática resulta útil para agrupar elementos en el mismo estado.  
  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación por los valores de cualquier columna o de varias columnas, sin tener en cuenta el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> configuración. Ordenación mediante programación es útil cuando desea proporcionar su propia interfaz de usuario (UI) para ordenar o cuando desea implementar una ordenación personalizada. Al proporcionar su propia interfaz de ordenación es útil, por ejemplo, al establecer el <xref:System.Windows.Forms.DataGridView> modo de selección para habilitar la selección de encabezado de columna. En este caso, aunque no se puede usar los encabezados de columna para ordenar, todavía desea que los encabezados para mostrar el glifo de ordenación adecuado, por lo que debe establecer el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Las columnas establecido en modo de ordenación mediante programación no se muestra automáticamente un glifo de ordenación. Para estas columnas, debe mostrar el glifo usted mismo estableciendo el <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> propiedad. Esto es necesario si desea flexibilidad en la ordenación personalizada. Por ejemplo, si ordena los <xref:System.Windows.Forms.DataGridView> por varias columnas, puede mostrar varios glifos de ordenación o ningún glifo de ordenación.  
  
 Aunque se puede ordenar mediante programación un <xref:System.Windows.Forms.DataGridView> por cualquier columna, algunas columnas, como columnas de botón, no pueden contener valores que se ordenen. Para estas columnas, un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> configuración de la propiedad de <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica que nunca se usará para la ordenación, por lo que no es necesario para reservar espacio en el encabezado para el glifo de ordenación.  
  
 Cuando un <xref:System.Windows.Forms.DataGridView> está ordenada, puede determinar la columna de ordenación y el criterio de ordenación mediante la comprobación de los valores de la <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades. Estos valores no son significativos después de una operación de ordenación personalizada. Para obtener más información sobre la ordenación personalizada, vea la sección ordenación personalizada más adelante en este tema.  
  
 Cuando un <xref:System.Windows.Forms.DataGridView> se ordena el control que contiene las columnas dependientes e independientes, no se puede mantener automáticamente los valores de las columnas sin enlazar. Para mantener estos valores, debe implementar el modo virtual estableciendo la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y controlar la <xref:System.Windows.Forms.DataGridView.CellValueNeeded> y <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos. Para obtener más información, consulte [Cómo: implementar el modo Virtual en el DataGridView Control de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). No se admite la ordenación por columnas sin enlazar en modo de enlace.  
  
## <a name="programmatic-sorting"></a>Ordenación mediante programación  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación mediante una llamada a su <xref:System.Windows.Forms.DataGridView.Sort%2A> método.  
  
 El `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método toma un <xref:System.Windows.Forms.DataGridViewColumn> y un <xref:System.ComponentModel.ListSortDirection> valor de enumeración como parámetros. Esta sobrecarga es útil al ordenar por columnas con valores que se ordenen, pero que no desea configurar para la ordenación automática. Cuando se llama a esta sobrecarga y se pasa en una columna con un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de propiedad de <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades se establecen automáticamente y aparece el glifo de ordenación adecuado en el encabezado de columna.  
  
> [!NOTE]
>  Cuando el <xref:System.Windows.Forms.DataGridView> control se enlaza a un origen de datos externo estableciendo la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad, el `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga del método no funciona para las columnas sin enlazar. Además, cuando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`, puede llamar a esta sobrecarga solo para las columnas enlazadas. Para determinar si una columna está enlazada a datos, compruebe la <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> valor de propiedad. No se admite la ordenación de columnas sin enlazar en modo de enlace.  
  
## <a name="custom-sorting"></a>Ordenación personalizada  
 Puede personalizar <xref:System.Windows.Forms.DataGridView> mediante el uso de la `Sort(IComparer)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método o controlando el <xref:System.Windows.Forms.DataGridView.SortCompare> eventos.  
  
 El `Sort(IComparer)` sobrecarga del método toma una instancia de una clase que implementa el <xref:System.Collections.IComparer> interfaz como un parámetro. Esta sobrecarga es útil cuando desea proporcionar una ordenación personalizada; Por ejemplo, cuando los valores de una columna no tiene un criterio de ordenación natural o cuando el criterio de ordenación natural es inadecuado. En este caso, no puede utilizar la ordenación automática, pero todavía puede que los usuarios ordenar haciendo clic en los encabezados de columna. Puede llamar a esta sobrecarga en un controlador para el <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> evento si no utiliza encabezados de columna para la selección.  
  
> [!NOTE]
>  El `Sort(IComparer)` sobrecarga del método sólo funcionará cuando el <xref:System.Windows.Forms.DataGridView> control no está enlazado a un origen de datos externo y el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es el valor de la propiedad `false`. Para personalizar la ordenación de las columnas enlazadas a un origen de datos externo, debe usar las operaciones de ordenación proporcionadas por el origen de datos. En modo virtual, debe proporcionar sus propias operaciones de ordenación para columnas sin enlazar.  
  
 Para usar el `Sort(IComparer)` sobrecarga del método, debe crear su propia clase que implementa el <xref:System.Collections.IComparer> interfaz. Esta interfaz requiere que la clase para implementar el <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> método al que el <xref:System.Windows.Forms.DataGridView> pasa <xref:System.Windows.Forms.DataGridViewRow> objetos como entrada cuando el `Sort(IComparer)` sobrecarga del método se llama. Con esto, puede calcular la ordenación de las filas correcto en función de los valores de cualquier columna.  
  
 El `Sort(IComparer)` sobrecarga del método no establece la <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades, por lo que siempre se debe establecer el <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> propiedad para mostrar el glifo de ordenación.  
  
 Como alternativa a la `Sort(IComparer)` sobrecarga del método, puede proporcionar la ordenación personalizada mediante la implementación de un controlador para el <xref:System.Windows.Forms.DataGridView.SortCompare> eventos. Este evento se produce cuando los usuarios, haga clic en los encabezados de columnas configurados para la clasificación automática o cuando se llama a la `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método. El evento se produce para cada par de filas en el control, lo que le permite calcular su orden correcto.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.DataGridView.SortCompare> evento no se produce cuando el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad está establecida o cuando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es el valor de la propiedad `true`.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>  
 [Ordenar datos en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)  
 [Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms](../../../../docs/framework/winforms/controls/set-the-sort-modes-for-columns-wf-datagridview-control.md)  
 [Personalizar la ordenación en el control DataGridView de formularios Windows Forms](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
