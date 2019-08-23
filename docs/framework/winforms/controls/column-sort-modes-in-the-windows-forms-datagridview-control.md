---
title: Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d0d743ccae38d101eda5bb9780b33ae18dfb608a
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918447"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView>las columnas tienen tres modos de ordenación. El modo de ordenación de cada columna se especifica <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> mediante la propiedad de la columna, que se puede establecer en uno de <xref:System.Windows.Forms.DataGridViewColumnSortMode> los siguientes valores de enumeración.  
  
|Valor de`DataGridViewColumnSortMode`|DESCRIPCIÓN|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Valor predeterminado para las columnas de cuadro de texto. A menos que se usen encabezados de columna para la selección, al hacer clic en <xref:System.Windows.Forms.DataGridView> el encabezado de columna, se ordena automáticamente por esta columna y se muestra un glifo que indica el criterio de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Valor predeterminado para las columnas que no son de cuadro de texto. Puede ordenar esta columna mediante programación; sin embargo, no está pensado para la ordenación, por lo que no se reserva espacio para el glifo de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Puede ordenar esta columna mediante programación y se reserva espacio para el glifo de ordenación.|  
  
 Es posible que desee cambiar el modo de ordenación de una columna que tiene <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> como valor predeterminado si contiene valores que se pueden ordenar de forma significativa. Por ejemplo, si tiene una columna de base de datos que contiene números que representan los Estados de los elementos, puede mostrar estos números como iconos correspondientes enlazando una columna de imagen a la columna de base de datos. Después, puede cambiar los valores de celda numérica en valores de presentación de imagen en un <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType> controlador para el evento. En este caso, el establecimiento <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de la <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> propiedad en permitirá a los usuarios ordenar la columna. La ordenación automática permitirá a los usuarios agrupar los elementos que tengan el mismo estado, incluso si los Estados correspondientes a los números no tienen una secuencia natural. Las columnas de casilla son otro ejemplo en el que la ordenación automática resulta útil para agrupar elementos en el mismo estado.  
  
 Puede ordenar <xref:System.Windows.Forms.DataGridView> mediante programación los valores de cualquier columna o de varias columnas, independientemente de la <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> configuración. La ordenación mediante programación es útil cuando se desea proporcionar su propia interfaz de usuario (UI) para ordenar o cuando se desea implementar una ordenación personalizada. Proporcionar su propia interfaz de usuario de ordenación resulta útil, por ejemplo, al <xref:System.Windows.Forms.DataGridView> establecer el modo de selección para habilitar la selección de encabezado de columna. En este caso, aunque los encabezados de columna no se pueden usar para la ordenación, todavía se desea que los encabezados muestren el glifo de ordenación adecuado, por lo <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> que se <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>establecerá la propiedad en.  
  
 Las columnas establecidas en el modo de ordenación mediante programación no muestran automáticamente un glifo de ordenación. Para estas columnas, debe mostrar el glifo mediante el establecimiento de la <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> propiedad. Esto es necesario si desea flexibilidad en la ordenación personalizada. Por ejemplo, si ordena <xref:System.Windows.Forms.DataGridView> por varias columnas, puede que desee mostrar varios glifos de ordenación o ningún glifo de ordenación.  
  
 Aunque puede ordenar una por una <xref:System.Windows.Forms.DataGridView> columna mediante programación, algunas columnas, como las columnas de botón, no pueden contener valores que se puedan ordenar de forma significativa. Para estas columnas, un <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valor de propiedad <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> de indica que nunca se usará para la ordenación, por lo que no es necesario reservar espacio en el encabezado para el glifo de ordenación.  
  
 Cuando se <xref:System.Windows.Forms.DataGridView> ordena una, puede determinar la columna de ordenación y el criterio de ordenación comprobando los valores de <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> las <xref:System.Windows.Forms.DataGridView.SortOrder%2A> propiedades y. Estos valores no son significativos después de una operación de ordenación personalizada. Para obtener más información acerca de la ordenación personalizada, vea la sección ordenación personalizada más adelante en este tema.  
  
 Cuando se <xref:System.Windows.Forms.DataGridView> ordena un control que contiene columnas enlazadas y sin enlazar, los valores de las columnas sin enlazar no se pueden mantener automáticamente. Para mantener estos valores, debe implementar el modo <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> virtual estableciendo la propiedad en `true` y controlando los <xref:System.Windows.Forms.DataGridView.CellValueNeeded> eventos <xref:System.Windows.Forms.DataGridView.CellValuePushed> y. Para obtener más información, vea [Cómo: Implemente el modo virtual en el control](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md)DataGridView Windows Forms. No se admite la ordenación por columnas sin enlazar en modo enlazado.  
  
## <a name="programmatic-sorting"></a>Ordenación mediante programación  
 Puede ordenar <xref:System.Windows.Forms.DataGridView> mediante programación llamando a su <xref:System.Windows.Forms.DataGridView.Sort%2A> método.  
  
 La `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga <xref:System.Windows.Forms.DataGridViewColumn> <xref:System.ComponentModel.ListSortDirection> del método toma y un valor de enumeración como parámetros. <xref:System.Windows.Forms.DataGridView.Sort%2A> Esta sobrecarga es útil al ordenar por columnas con valores que se pueden ordenar de forma significativa, pero que no desea configurar para la ordenación automática. Cuando se llama a esta sobrecarga y se pasa una columna con <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> un valor de <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>propiedad de <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> , <xref:System.Windows.Forms.DataGridView.SortOrder%2A> las propiedades y se establecen automáticamente y aparece el glifo de ordenación adecuado en el encabezado de columna.  
  
> [!NOTE]
> Cuando el <xref:System.Windows.Forms.DataGridView> control se enlaza a un origen de datos externo estableciendo la <xref:System.Windows.Forms.DataGridView.DataSource%2A> propiedad, la `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga del método no funciona para las columnas sin enlazar. Además, cuando la <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> propiedad es `true`, puede llamar a esta sobrecarga solo para columnas enlazadas. Para determinar si una columna está enlazada a datos, compruebe <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A> el valor de la propiedad. No se admite la ordenación de columnas no enlazadas en modo enlazado.  
  
## <a name="custom-sorting"></a>Ordenación personalizada  
 Puede personalizar <xref:System.Windows.Forms.DataGridView> mediante la `Sort(IComparer)` sobrecarga del <xref:System.Windows.Forms.DataGridView.Sort%2A> método o controlando el <xref:System.Windows.Forms.DataGridView.SortCompare> evento.  
  
 La `Sort(IComparer)` sobrecarga del método toma una instancia de una clase que implementa la <xref:System.Collections.IComparer> interfaz como un parámetro. Esta sobrecarga es útil cuando se desea proporcionar una ordenación personalizada; por ejemplo, cuando los valores de una columna no tienen un criterio de ordenación natural o el criterio de ordenación natural no es apropiado. En este caso, no puede usar la ordenación automática, pero puede que desee que los usuarios realicen la ordenación haciendo clic en los encabezados de columna. Puede llamar a esta sobrecarga en un controlador para el <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> evento si no utiliza encabezados de columna para la selección.  
  
> [!NOTE]
> La `Sort(IComparer)` sobrecarga del método solo funciona cuando <xref:System.Windows.Forms.DataGridView> el control no está enlazado a un origen de datos <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> externo y el `false`valor de la propiedad es. Para personalizar la ordenación de las columnas enlazadas a un origen de datos externo, debe utilizar las operaciones de ordenación proporcionadas por el origen de datos. En el modo virtual, debe proporcionar sus propias operaciones de ordenación para las columnas sin enlazar.  
  
 Para usar la `Sort(IComparer)` sobrecarga del método, debe crear su propia clase que implementa la <xref:System.Collections.IComparer> interfaz. Esta interfaz requiere que la clase implemente <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType> el método, en el <xref:System.Windows.Forms.DataGridView> que <xref:System.Windows.Forms.DataGridViewRow> el pasa objetos como entrada `Sort(IComparer)` cuando se llama a la sobrecarga del método. Con esto, puede calcular el orden correcto de las filas en función de los valores de cualquier columna.  
  
 La `Sort(IComparer)` sobrecarga del método no establece las <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> propiedades <xref:System.Windows.Forms.DataGridView.SortOrder%2A> y, por lo que siempre debe establecer <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> la propiedad para mostrar el glifo de ordenación.  
  
 Como alternativa a la sobrecarga `Sort(IComparer)` del método, puede proporcionar una ordenación personalizada implementando un controlador para el <xref:System.Windows.Forms.DataGridView.SortCompare> evento. Este evento se produce cuando los usuarios hacen clic en los encabezados de las columnas configuradas para la ordenación automática o <xref:System.Windows.Forms.DataGridView.Sort%2A> cuando se llama a la `Sort(DataGridViewColumn,ListSortDirection)` sobrecarga del método. El evento se produce para cada par de filas del control, lo que le permite calcular su orden correcto.  
  
> [!NOTE]
> El <xref:System.Windows.Forms.DataGridView.SortCompare> evento no se produce cuando se <xref:System.Windows.Forms.DataGridView.DataSource%2A> establece la propiedad o cuando el <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> valor de la `true`propiedad es.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Ordenar datos en el control DataGridView de Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer los modos de ordenación de las columnas en el control DataGridView Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Cómo: Personalizar la ordenación en el control DataGridView Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
