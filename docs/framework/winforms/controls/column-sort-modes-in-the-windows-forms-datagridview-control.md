---
title: Modos de ordenación de columnas en el control DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], sort modes
- DataGridView control [Windows Forms], sort mode
ms.assetid: 43715887-2df9-4da7-bcf1-b9c7c842b2bf
ms.openlocfilehash: d1e2f582c9759332e0ed963cb7f88ee052616c45
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744195"
---
# <a name="column-sort-modes-in-the-windows-forms-datagridview-control"></a>Modos de ordenación de columnas del control DataGridView de formularios Windows Forms
<xref:System.Windows.Forms.DataGridView> columnas tienen tres modos de ordenación. El modo de ordenación de cada columna se especifica mediante la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de la columna, que se puede establecer en uno de los siguientes valores de enumeración de <xref:System.Windows.Forms.DataGridViewColumnSortMode>.  
  
|Valor de `DataGridViewColumnSortMode`|Descripción|  
|----------------------------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic>|Valor predeterminado para las columnas de cuadro de texto. A menos que se usen encabezados de columna para la selección, al hacer clic en el encabezado de columna, se ordena automáticamente el <xref:System.Windows.Forms.DataGridView> por esta columna y se muestra un glifo que indica el criterio de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable>|Valor predeterminado para las columnas que no son de cuadro de texto. Puede ordenar esta columna mediante programación; sin embargo, no está pensado para la ordenación, por lo que no se reserva espacio para el glifo de ordenación.|  
|<xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>|Puede ordenar esta columna mediante programación y se reserva espacio para el glifo de ordenación.|  
  
 Es posible que desee cambiar el modo de ordenación de una columna que tiene como valor predeterminado <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> si contiene valores que se pueden ordenar de forma significativa. Por ejemplo, si tiene una columna de base de datos que contiene números que representan los Estados de los elementos, puede mostrar estos números como iconos correspondientes enlazando una columna de imagen a la columna de base de datos. Después, puede cambiar los valores de celda numérica en valores de presentación de imagen en un controlador para el evento <xref:System.Windows.Forms.DataGridView.CellFormatting?displayProperty=nameWithType>. En este caso, el establecimiento de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> en <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic> permitirá a los usuarios ordenar la columna. La ordenación automática permitirá a los usuarios agrupar los elementos que tengan el mismo estado, incluso si los Estados correspondientes a los números no tienen una secuencia natural. Las columnas de casilla son otro ejemplo en el que la ordenación automática resulta útil para agrupar elementos en el mismo estado.  
  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación por los valores de cualquier columna o en varias columnas, independientemente de la configuración de <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A>. La ordenación mediante programación es útil cuando se desea proporcionar su propia interfaz de usuario (UI) para ordenar o cuando se desea implementar una ordenación personalizada. Proporcionar su propia interfaz de usuario de ordenación es útil, por ejemplo, al establecer el modo de selección de <xref:System.Windows.Forms.DataGridView> para habilitar la selección de encabezado de columna. En este caso, aunque los encabezados de columna no se pueden usar para la ordenación, todavía se desea que los encabezados muestren el glifo de ordenación adecuado, por lo que se establecerá la propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> en <xref:System.Windows.Forms.DataGridViewColumnSortMode.Programmatic>.  
  
 Las columnas establecidas en el modo de ordenación mediante programación no muestran automáticamente un glifo de ordenación. Para estas columnas, debe mostrar el glifo mediante el establecimiento de la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>. Esto es necesario si desea flexibilidad en la ordenación personalizada. Por ejemplo, si ordena el <xref:System.Windows.Forms.DataGridView> por varias columnas, puede que desee mostrar varios glifos de ordenación o ningún glifo de ordenación.  
  
 Aunque puede ordenar mediante programación un <xref:System.Windows.Forms.DataGridView> por cualquier columna, algunas columnas, como las columnas de botón, podrían no contener valores que se puedan ordenar de forma significativa. Para estas columnas, un valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de <xref:System.Windows.Forms.DataGridViewColumnSortMode.NotSortable> indica que nunca se usará para la ordenación, por lo que no es necesario reservar espacio en el encabezado para el glifo de ordenación.  
  
 Cuando se ordena un <xref:System.Windows.Forms.DataGridView>, puede determinar la columna de ordenación y el criterio de ordenación comprobando los valores de las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A>. Estos valores no son significativos después de una operación de ordenación personalizada. Para obtener más información acerca de la ordenación personalizada, vea la sección ordenación personalizada más adelante en este tema.  
  
 Cuando se ordena un <xref:System.Windows.Forms.DataGridView> control que contiene columnas enlazadas y sin enlazar, los valores de las columnas sin enlazar no se pueden mantener automáticamente. Para mantener estos valores, debe implementar el modo virtual estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> en `true` y controlando los eventos <xref:System.Windows.Forms.DataGridView.CellValueNeeded> y <xref:System.Windows.Forms.DataGridView.CellValuePushed>. Para obtener más información, vea [Cómo: implementar el modo virtual en el control DataGridView de Windows Forms](how-to-implement-virtual-mode-in-the-windows-forms-datagridview-control.md). No se admite la ordenación por columnas sin enlazar en modo enlazado.  
  
## <a name="programmatic-sorting"></a>Ordenación mediante programación  
 Puede ordenar un <xref:System.Windows.Forms.DataGridView> mediante programación llamando a su método <xref:System.Windows.Forms.DataGridView.Sort%2A>.  
  
 La sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> toma un <xref:System.Windows.Forms.DataGridViewColumn> y un valor de enumeración <xref:System.ComponentModel.ListSortDirection> como parámetros. Esta sobrecarga es útil al ordenar por columnas con valores que se pueden ordenar de forma significativa, pero que no desea configurar para la ordenación automática. Cuando se llama a esta sobrecarga y se pasa una columna con un valor de propiedad <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> de <xref:System.Windows.Forms.DataGridViewColumnSortMode.Automatic?displayProperty=nameWithType>, las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A> se establecen automáticamente y aparece el glifo de ordenación adecuado en el encabezado de columna.  
  
> [!NOTE]
> Cuando el control de <xref:System.Windows.Forms.DataGridView> se enlaza a un origen de datos externo estableciendo la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A>, la sobrecarga del método `Sort(DataGridViewColumn,ListSortDirection)` no funciona para las columnas sin enlazar. Además, cuando se `true`la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>, solo puede llamar a esta sobrecarga para las columnas enlazadas. Para determinar si una columna está enlazada a datos, compruebe el valor de la propiedad <xref:System.Windows.Forms.DataGridViewColumn.IsDataBound%2A>. No se admite la ordenación de columnas no enlazadas en modo enlazado.  
  
## <a name="custom-sorting"></a>Ordenación personalizada  
 Puede personalizar <xref:System.Windows.Forms.DataGridView> mediante la sobrecarga de `Sort(IComparer)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A> o controlando el evento de <xref:System.Windows.Forms.DataGridView.SortCompare>.  
  
 La sobrecarga del método `Sort(IComparer)` toma una instancia de una clase que implementa la interfaz de <xref:System.Collections.IComparer> como parámetro. Esta sobrecarga es útil cuando se desea proporcionar una ordenación personalizada; por ejemplo, cuando los valores de una columna no tienen un criterio de ordenación natural o el criterio de ordenación natural no es apropiado. En este caso, no puede usar la ordenación automática, pero puede que desee que los usuarios realicen la ordenación haciendo clic en los encabezados de columna. Puede llamar a esta sobrecarga en un controlador para el evento <xref:System.Windows.Forms.DataGridView.ColumnHeaderMouseClick> si no utiliza encabezados de columna para la selección.  
  
> [!NOTE]
> La sobrecarga del método `Sort(IComparer)` solo funciona cuando el control <xref:System.Windows.Forms.DataGridView> no está enlazado a un origen de datos externo y el valor de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A> es `false`. Para personalizar la ordenación de las columnas enlazadas a un origen de datos externo, debe utilizar las operaciones de ordenación proporcionadas por el origen de datos. En el modo virtual, debe proporcionar sus propias operaciones de ordenación para las columnas sin enlazar.  
  
 Para usar la sobrecarga del método `Sort(IComparer)`, debe crear su propia clase que implementa la interfaz <xref:System.Collections.IComparer>. Esta interfaz requiere que la clase implemente el método <xref:System.Collections.IComparer.Compare%2A?displayProperty=nameWithType>, en el que la <xref:System.Windows.Forms.DataGridView> pasa <xref:System.Windows.Forms.DataGridViewRow> objetos como entrada cuando se llama a la sobrecarga del método `Sort(IComparer)`. Con esto, puede calcular el orden correcto de las filas en función de los valores de cualquier columna.  
  
 La sobrecarga del método `Sort(IComparer)` no establece las propiedades <xref:System.Windows.Forms.DataGridView.SortedColumn%2A> y <xref:System.Windows.Forms.DataGridView.SortOrder%2A>, por lo que siempre debe establecer la propiedad <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType> para mostrar el glifo de ordenación.  
  
 Como alternativa a la sobrecarga del método `Sort(IComparer)`, puede proporcionar una ordenación personalizada implementando un controlador para el evento <xref:System.Windows.Forms.DataGridView.SortCompare>. Este evento se produce cuando los usuarios hacen clic en los encabezados de las columnas configuradas para la ordenación automática o cuando se llama a la sobrecarga `Sort(DataGridViewColumn,ListSortDirection)` del método <xref:System.Windows.Forms.DataGridView.Sort%2A>. El evento se produce para cada par de filas del control, lo que le permite calcular su orden correcto.  
  
> [!NOTE]
> El evento <xref:System.Windows.Forms.DataGridView.SortCompare> no se produce cuando se establece la propiedad <xref:System.Windows.Forms.DataGridView.DataSource%2A> o cuando se `true`el valor de la propiedad <xref:System.Windows.Forms.DataGridView.VirtualMode%2A>.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.Sort%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortedColumn%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.SortOrder%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell.SortGlyphDirection%2A?displayProperty=nameWithType>
- [Ordenar datos en el control DataGridView de Windows Forms](sorting-data-in-the-windows-forms-datagridview-control.md)
- [Cómo: Establecer modos de ordenación de columnas en el control DataGridView de Windows Forms](set-the-sort-modes-for-columns-wf-datagridview-control.md)
- [Personalizar la ordenación en el control DataGridView de formularios Windows Forms](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
