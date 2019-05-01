---
title: Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: b8f6048946d367dd79b1ce0d23d84446ffdb1115
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956226"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView> las columnas tienen tres modos de ordenación. El modo de ordenación para cada columna se especifica a través de la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad de la columna, que se puede establecer en uno de los siguientes <xref:System.Windows.Forms.DataGridViewColumnSortMode> valores de enumeración.  
  
|Valor de`DataGridViewColumnSortMode` |Descripción|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Valor predeterminado para las columnas del cuadro de texto. A menos que se usan encabezados de columna para la selección, haga clic en el encabezado de columna automáticamente ordena la <xref:System.Windows.Forms.DataGridView> por esta columna y muestra un glifo que indica el criterio de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Para las columnas del cuadro de texto que no sean de: de forma predeterminada. Puede ordenar esta columna mediante programación; Sin embargo, no se diseñó para la ordenación, por lo que se reserva ningún espacio para el glifo de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Puede ordenar esta columna mediante programación y se reserva espacio para el glifo de ordenación.|  
  
 Es posible que desea cambiar el modo de ordenación para una columna cuyo valor predeterminado es <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> si contiene valores que se pueden ordenar. Por ejemplo, si tiene una columna de base de datos que contiene números que representan estados de elementos, puede mostrar estos números como iconos correspondientes al enlazar una columna de imagen a la columna de base de datos. A continuación, puede cambiar los valores de celda numéricos en los valores de presentación de imagen en un controlador para el <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> eventos. En este caso, establecer el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> permitirá a los usuarios ordenar la columna. La ordenación automática permitirá a los usuarios para agrupar elementos que tienen el mismo estado, incluso si los Estados correspondientes a los números no tienen una secuencia natural. Las columnas de casilla de verificación son otro ejemplo donde la ordenación automática resulta útil para agrupar elementos en el mismo estado.  
  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación, los valores de cualquier columna o en varias columnas, independientemente de la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> configuración. Ordenación mediante programación es útil cuando desea proporcionar su propia interfaz de usuario (UI) para la ordenación o cuando desea implementar una ordenación personalizada. Proporcionar su propia interfaz de usuario de ordenación es útil, por ejemplo, al establecer el <xref:System.Windows.Forms.DataGridView> modo de selección para habilitar la selección del encabezado de columna. En este caso, aunque no se puede usar los encabezados de columna para ordenar, aún desea que los encabezados para mostrar el glifo de ordenación adecuado, por lo que desea establecer el <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Las columnas establecido en modo de ordenación mediante programación no muestran automáticamente un glifo de ordenación. Para estas columnas, debe mostrar el glifo de por sí mismo estableciendo el <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> propiedad. Esto es necesario si desea flexibilidad en la ordenación personalizada. Por ejemplo, si se ordena la <xref:System.Windows.Forms.DataGridView> por varias columnas, es posible que desee mostrar varios glifos de ordenación o ningún glifo de ordenación.  
  
 Aunque se puede ordenar mediante programación un <xref:System.Windows.Forms.DataGridView> por cualquier columna, algunas columnas, como columnas de botones no pueden contener valores que se pueden ordenar. Para estas columnas, un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de configuración de la propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica que nunca se usará para la ordenación, por lo que no es necesario para reservar espacio en el encabezado para el glifo de ordenación.  
  
 Cuando un <xref:System.Windows.Forms.DataGridView> está ordenado, puede determinar la columna de ordenación y el criterio de ordenación comprobando los valores de la <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades. Estos valores no son significativos después de una operación de ordenación personalizada. Para obtener más información sobre la ordenación personalizada, vea la sección de ordenación personalizados más adelante en este tema.  
  
 Cuando un <xref:System.Windows.Forms.DataGridView> se ordena el control que contiene las columnas dependientes e independientes, no se puede mantener automáticamente los valores de las columnas sin enlazar. Para mantener estos valores, debe implementar el modo virtual mediante el establecimiento la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad `true` y controlar la <xref:System.Windows.Forms.DataGridView.CellValueNeeded> y <xref:System.Windows.Forms.DataGridView.CellValuePushed> eventos. Para obtener más información, vea [Cómo: Implementar el modo Virtual en el Windows Forms DataGridView Control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). No se admite la ordenación por columnas sin enlazar en modo de enlace.  
  
## <a name="programmatic-sorting"></a>Ordenación mediante programación  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación llamando a su <xref:System.Windows.Forms.DataGridView.Sort%2A> método.  
  
 El `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método toma un <xref:System.Windows.Forms.DataGridViewColumn> y un <xref:System.ComponentModel.ListSortDirection> valor de enumeración como parámetros. Esta sobrecarga es útil al ordenar por columnas con valores que se pueden ordenar, pero que no desea configurar para la ordenación automática. Cuando se llama a esta sobrecarga y se pasa en una columna con un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> el valor de propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades se establecen automáticamente y aparece el glifo de ordenación adecuado en el encabezado de columna.  
  
> [!NOTE]
>  Cuando el <xref:System.Windows.Forms.DataGridView> control se enlaza a un origen de datos externo estableciendo la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad, el `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga del método no funciona para las columnas sin enlazar. Además, cuando el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`, puede llamar a esta sobrecarga sólo para las columnas enlazadas. Para determinar si una columna está enlazado a datos, compruebe el <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> valor de propiedad. No se admite la ordenación de columnas sin enlazar en modo de enlace.  
  
## <a name="custom-sorting"></a>Ordenación personalizada  
 Puede personalizar <xref:System.Windows.Forms.DataGridView> utilizando el `Sort(IComparer)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método o controlando el <xref:System.Windows.Forms.DataGridView.SortCompare> eventos.  
  
 El `Sort(IComparer)` sobrecarga del método toma una instancia de una clase que implementa el <xref:System.Collections.IComparer> interfaz como parámetro. Esta sobrecarga es útil cuando desee proporcionar una ordenación personalizada; Por ejemplo, cuando los valores de una columna no tienen un criterio de ordenación natural o cuando el criterio de ordenación natural es inadecuado. En este caso, no se puede usar la ordenación automática, pero es posible que aún desea que los usuarios ordenar haciendo clic en los encabezados de columna. Puede llamar a esta sobrecarga en un controlador para el <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> si no usa encabezados de columna para la selección de eventos.  
  
> [!NOTE]
>  El `Sort(IComparer)` sobrecarga del método solo funciona cuando la <xref:System.Windows.Forms.DataGridView> control no está enlazado a un origen de datos externo y el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es el valor de propiedad `false`. Para personalizar la ordenación de las columnas enlazadas a un origen de datos externo, debe usar las operaciones de ordenación proporcionadas por el origen de datos. En modo virtual, debe proporcionar sus propias operaciones de ordenación para las columnas sin enlazar.  
  
 Para usar el `Sort(IComparer)` sobrecarga del método, debe crear su propia clase que implementa el <xref:System.Collections.IComparer> interfaz. Esta interfaz requiere que la clase para implementar el <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> método al que el <xref:System.Windows.Forms.DataGridView> pasa <xref:System.Windows.Forms.DataGridViewRow> objetos como entrada cuando el `Sort(IComparer)` se llama a la sobrecarga del método. Con esto, puede calcular el orden de fila correcta según los valores de cualquier columna.  
  
 El `Sort(IComparer)` sobrecarga del método no establece la <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades, por lo que siempre debe establecer el <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> propiedad para mostrar el glifo de ordenación.  
  
 Como alternativa a la `Sort(IComparer)` sobrecarga del método, puede proporcionar una ordenación personalizada mediante la implementación de un controlador para el <xref:System.Windows.Forms.DataGridView.SortCompare> eventos. Este evento se produce cuando los usuarios, haga clic en los encabezados de columnas configurado para la clasificación automática o cuando se llama a la `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga de la <xref:System.Windows.Forms.DataGridView.Sort%2A> método. El evento se produce para cada par de filas del control, lo que permite calcular su orden correcto.  
  
> [!NOTE]
>  El <xref:System.Windows.Forms.DataGridView.SortCompare> evento no se produce cuando el <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad está establecida o cuando el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es el valor de propiedad `true`.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Ordenar datos en el control DataGridView de Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer modos de ordenación de columnas en el Control DataGridView de Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Cómo: Personalizar la ordenación en el Control DataGridView de Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
